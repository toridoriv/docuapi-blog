[](https://app.netlify.com/sites/docuapi/deploys)![Estado de Netlify](https://api.netlify.com/api/v1/badges/49111249-0a1a-4b5a-a3ab-45d00732fdb3/deploy-status)

**DocuAPI** es un hermoso tema de documentación API multilingüe para [Hugo](http://gohugo.io/) . Este tema se basa en el hermoso trabajo de [Robert Lord](https://github.com/lord) y otros en el proyecto [Slate](https://github.com/slatedocs/slate) ( [licencia Apache 2](https://github.com/slatedocs/slate/blob/master/LICENSE) ).

<br>

> Visite el [sitio de demostración](https://docuapi.netlify.com/) .

<br>

![Captura de pantalla Sitio de ejemplo de DocuAPI](https://raw.githubusercontent.com/bep/docuapi/master/images/screenshot.png)

## Use

The client library used to build the ToC does not handle Unicode very well. To get around this in Hugo &gt;= 0.62.2, put this in your site config:

```toml
[markup]
  [markup.goldmark]
    [markup.goldmark.parser]
      autoHeadingIDType = "github-ascii"
```

**Nota:** este tema requiere Hugo &gt;= 0.56.0 para funcionar. Si desea editar los estilos SCSS, necesita:

- La versión extendida de Hugo.
- PostCSS CLI (ejecute `npm install` para instalar los requisitos)

Vea el sitio de [ejemplo](https://github.com/bep/docuapi/tree/master/exampleSite) y más específicamente su [configuración](https://github.com/bep/docuapi/blob/master/exampleSite/config.toml) de sitio para las opciones disponibles.

**Lo más notable:** este tema utilizará todas las páginas (que no sean borradores) del sitio y creará una documentación API de una sola página. Usar el `weight` en el frente de la página es la forma más fácil de controlar el orden de las páginas.

Si desea una selección de página diferente, proporcione su propia plantilla `layouts/index.html` .

Puede personalizar la apariencia agregando sus propias variables CSS en `assets/scss/docuapi_overrides.scss` . Consulte la carpeta exampleSite para ver un ejemplo.

## Manos

Puede anular los diseños proporcionando algunos parciales personalizados:

- `partials/hook_head_end.html` se inserta justo antes de la etiqueta de `head` . Útil para estilos adicionales, etc.
- `partials/hook_body_end.html` que debe quedar claro por su nombre.
- `partials/hook_left_sidebar_start.html` el inicio de la barra lateral izquierda
- `partials/hook_left_sidebar_end.html` el final de la barra lateral izquierda
- `partials/hook_left_sidebar_logo.html` la fuente de registro `img`

Los estilos y la importación de Javascript también se colocan en cada parcial y, como tal, se pueden anular si realmente es necesario:

- `partials/styles.html`
- `partials/js.html`
