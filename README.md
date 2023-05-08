![image](/assets/logo.svg) 

# Página Uptime de Asimov

A continuación se detallan las instrucciones para poder crear un status page, como por ejemplo el que Asimov brinda a la Universidad Católica de Chile: https://status.uc.asimov.cl. 

## Instrucciones 

1. Clonar repositorio desde la opción template en github https://github.com/Asimovers/cl-asimov-uc-status
   1. Se sugiere crear un nombre descriptivo a la url que tendrá. 
   3. Al momento de crear el repositorio debe ser publico (para usar github pages) y se deben incluir todas ramas (Include All Branches).
   4. Luego se debe crear un Personal Access Token para que el repositorio pueda operar las acciones de Github Actions. Y setearlos con la variable GH_PAT. Más detalles en https://upptime.js.org/docs/get-started
   5. Se debe editar el archivo `.upptimerc.yml` donde esta toda la configuración. 


## Primeros pasos

**☝️ TODAS LAS CONFIGURURACIONES SOBRE EL ARCHIVO `.upptimerc.yml`**

Primero se deben cambiar los siguientes datos de configuración.

```yml
# .upptimerc.yml
owner: Asimovers # corresponde al usuario u organización, debería ser siempre Asimovers
repo: cl-asimov-uc-status # nombre del repositorio
```

Acá se configuran todo los sitios que se desean monitorear.

```yml
# .upptimerc.yml
sites:
  - name: Portal UC
    url: https://uc.cl
  - name: Sitio Kit Digital 
    url: https://kitdigital.uc.cl
  - name: Api Agenda UC
    url: https://api.agenda.uc.asimov.cl/
  - name: Sitio Agenda UC
    url: https://cl-uc-agenda-front.netlify.app/
```

Usuario o usuarios a los cuales se les asignara un issue al momento de detectarse una caida de alguno de los sitios.

```yml
# .upptimerc.yml
assignees: # Users to assign downtime issues (optional)
  - githubUsername
```

A continuación se detalla la configuración de dominio y contenido del sitio 


```yml
# .upptimerc.yml
status-website:
  # Add your custom domain name, or remove the `cname` line if you don't have a domain
  # Uncomment the `baseUrl` line if you don't have a custom domain and add your repo name there
  cname: status.uc.asimov.cl
  # baseUrl: /
  
  # NO EDITAR
  favicon: https://asimovers.github.io/status-page-guide/assets/favicon.png 
  # NO EDITAR
  logoUrl: https://asimovers.github.io/status-page-guide/assets/logo.svg
  # NO EDITAR
  themeUrl: https://asimovers.github.io/status-page-guide/theme/asimov-dark.css
  
  name: Status UC por Asimov
  introTitle: "**Status UC** es un servicio que monitorea los sistemas que ha desarrollado Asimov para la Universidad Católica de Chile."
  introMessage: Si tiene dudas sobre este sitio, por favor ponerse en contacto a [direcciondigital@uc.cl](mailto:direcciondigital@uc.cl). o [incidencias-uc@asimov.cl](mailto:incidencias-uc@asimov.cl).
  
  # NO EDITAR
  navbar:
    - title: Status
      href: /
    - title: Repo
      href: https://github.com/$OWNER/$REPO
    - title: Asimov
      href: https://asimov.cl/
```

Se recomienda hacer los cambios directamente en el editor del repositorio, dado que cada vez que se hacen cambios las acciones automáticas generar nuevos commits en el repositorio.


Más opciones de configuración en https://upptime.js.org/docs/configuration
