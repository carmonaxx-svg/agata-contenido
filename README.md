# Contenido de «Los mundos de Ágata»

Lo que hay en esta carpeta llega a la app sin publicar una versión nueva.
Se sirve con GitHub Pages en https://carmonaxx-svg.github.io/agata-contenido/

| Archivo | Qué es |
|---|---|
| `library.json` | Las secciones de inicio («Pinta y colorea», «Juega y aprende»), los libros, si están disponibles o en preparación, portadas y enlaces de Amazon |
| `worlds.json` | Las láminas para colorear de cada mundo, con su fecha de publicación y si son gratis o de suscripción |
| `plates/` | Láminas nuevas que no van dentro de la app |
| `actividades/<libro>/` | Cada libro de juegos: `manifest.json` (misiones, fechas, acceso, datos del juego) y las imágenes de cada misión |
| `portadas/` | Portadas de libros que no van dentro de la app |

**No se edita a mano.** Se genera desde el repositorio de la app
(`los-mundos-de-agata-app`, ver `docs/CONTENT_OPERATIONS.md`):

```bash
python tool/content/build_activities.py <libro> <interior.pdf> ../agata-contenido
python tool/content/publish_content.py ../agata-contenido
```

y después se hace commit y push de esta carpeta. La app comprueba la huella
(SHA-256) de cada imagen antes de mostrarla; si algo falla, sigue con el
último contenido bueno.

Todo lo que se publica aquí es descargable por cualquiera que conozca la
dirección. El acceso de pago lo controla la app (Google Play), no esta carpeta.
