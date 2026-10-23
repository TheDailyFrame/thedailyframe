<div align="center">

# The Daily Frame

**Un periódico digital en blanco y negro para contarlo todo:**
cine, videojuegos, informática, análisis, reviews, deportes y actualidad.

[![Ver la web](https://img.shields.io/badge/Ver_la_web-000000?style=for-the-badge&logo=safari&logoColor=white)](https://thedailyframe.github.io/thedailyframe/)
[![Panel de redacción](https://img.shields.io/badge/Panel_de_redacci%C3%B3n-ffffff?style=for-the-badge&logo=githubpages&logoColor=black)](https://thedailyframe.github.io/thedailyframe/admin.html)

![GitHub Pages](https://img.shields.io/badge/hosting-GitHub_Pages-000000?style=flat-square&logo=github)
![HTML5](https://img.shields.io/badge/HTML5-000000?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-000000?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-000000?style=flat-square&logo=javascript&logoColor=white)
![Sin dependencias](https://img.shields.io/badge/dependencias-0-000000?style=flat-square)
![Responsive](https://img.shields.io/badge/dise%C3%B1o-responsive-000000?style=flat-square)

</div>

---

## De qué va

**The Daily Frame** es una web de noticias con la apariencia de un periódico impreso: todo en blanco y negro, titulares enormes, tipografía limpia sin remates (estilo Apple) y una maquetación que en ordenador se lee como un libro abierto y en móvil se apila, una noticia debajo de otra.

No usa servidor ni base de datos. Las noticias se guardan en un archivo del propio repositorio (`data/noticias.json`) y el panel de redacción las publica directamente con la API de GitHub.

## Características

- **Portada principal** con titular grande y fotografía panorámica ancha.
- **Páginas interiores** a doble hoja, con numeración y navegación con flechas del teclado. Todas las imágenes tienen la misma proporción para que nada se descuadre.
- **Todas las fotografías en blanco y negro** automáticamente, sin editarlas.
- **Página de lectura** de cada noticia con texto a dos columnas, letra capital y tiempo de lectura.
- **Exportación a PDF** en formato horizontal, empezando a dos páginas como un libro abierto.
- **Responsive**: en móvil, una sola columna.
- **Editor visual (WYSIWYG)** en el panel: negrita, cursiva, subrayado, subtítulos, citas, listas, enlaces, fotos, separadores y vista previa.
- **Publicación en un clic** desde el navegador, sin tocar el código.

## Estructura

```
thedailyframe/
├── index.html        Portada y páginas interiores
├── noticias.html     Lectura de una noticia (?id=...)
├── admin.html        Panel de redacción con editor
├── data/
│   └── noticias.json Noticias (se crea al publicar la primera)
└── README.md
```

## Puesta en marcha

1. **Sube** `index.html`, `noticias.html` y `admin.html` a este repositorio.
2. **Activa GitHub Pages**: *Settings → Pages → Deploy from a branch →* rama `main`, carpeta `/ (root)`.
3. **Crea un token** en GitHub: *Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token*.
   - *Repository access*: **Only select repositories** y elige este repositorio.
   - *Repository permissions → Contents*: **Read and write**.
4. **Abre el panel** en `https://thedailyframe.github.io/thedailyframe/admin.html`, pega el token y pulsa **Entrar**. El repositorio se detecta solo y el token se guarda únicamente en tu navegador.

> Los cambios tardan uno o dos minutos en verse en la web, que es lo que tarda GitHub Pages en actualizarse.

## Escribir una noticia

1. Pulsa **Nueva noticia** en el panel.
2. Rellena titular, subtítulo, sección, autor, fecha y la URL de la fotografía principal.
3. Escribe el cuerpo con el editor visual y revisa el resultado con **Vista previa**.
4. Elige si es **Noticia de portada** o **Página interior**.
5. Pulsa **Publicar** (o `Ctrl + S`).

Atajos: `Ctrl + B` negrita, `Ctrl + I` cursiva, `Ctrl + U` subrayado, `Ctrl + K` enlace.

### Dónde aparece cada noticia

| Tipo | Dónde sale |
| --- | --- |
| **Noticia de portada** | Arriba del todo, con titular grande y foto panorámica. Solo puede haber una: al marcar otra, la anterior pasa a las páginas interiores. Si no marcas ninguna, la portada es la más reciente. |
| **Página interior** | Debajo de la portada, a razón de tres noticias por página y ordenadas de la más nueva a la más antigua. Las páginas se muestran de dos en dos, como un libro abierto. |
| **Cualquier noticia** | Al hacer clic se abre su página de lectura completa. |

## Exportar a PDF

Pulsa **Exportar PDF** en la portada o en una noticia. En el cuadro de impresión elige *Guardar como PDF* y activa **Gráficos de fondo**. El resultado sale en horizontal, con dos páginas por hoja.

## Personalizar

- **Nombre del periódico**: constante `NAME` al inicio del script de `index.html` y `noticias.html`.
- **Colores y tipografía**: variables CSS en `:root` al inicio de cada archivo. La fuente es [Inter](https://fonts.google.com/specimen/Inter), con tipografía del sistema como respaldo.
- **Noticias por página**: en `index.html`, el salto de `i+=3` al crear las páginas.

## Seguridad

- El token **nunca se guarda en el repositorio**, solo en el navegador de quien inicia sesión. Cierra sesión con el botón del panel en equipos compartidos.
- `admin.html` es una página pública, pero sin un token válido nadie puede publicar ni borrar nada. Usa un token limitado a este repositorio y renuévalo de vez en cuando.

## Tecnologías

HTML, CSS y JavaScript puros, sin frameworks ni dependencias. API de contenidos de GitHub para guardar las noticias y GitHub Pages para alojar la web.

---

<div align="center">

**The Daily Frame** · hecho para contarlo todo en blanco y negro

</div>
