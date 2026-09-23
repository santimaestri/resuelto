# Resuelto

Sitio web de **Resuelto** — IA y automatización para vendedores de Mercado Libre,
medios y redacciones, pymes y equipos que adoptan Claude.

🌐 **En vivo:** [santimaestri.github.io/resuelto](https://santimaestri.github.io/resuelto/)

> **Nota sobre el dominio:** el sitio se publica en la dirección de GitHub Pages
> porque el dominio anterior (`reviu.com.ar`, del nombre viejo REVIU) no se renovó.
> Si más adelante hay dominio propio, se agrega un archivo `CNAME` con el dominio
> y se configura en *Settings → Pages*.

## Qué hay en este repo

| Archivo / carpeta  | Qué es                                                              |
| ------------------ | ------------------------------------------------------------------- |
| `index.html`       | La página principal completa (navegación, hero, qué hacemos, método, pruebas, contacto) |
| `legal/index.html` | Política de Privacidad y Términos del Servicio                       |
| `.gitattributes`   | Configuración de Git para el manejo de archivos de texto             |

## Cómo está hecho

Es un sitio **estático**: no necesita servidor, base de datos ni proceso de build.
Todo el HTML, los estilos y el poco JavaScript que usa viven dentro de `index.html`.

Las herramientas se cargan directamente desde internet (CDN), así que no hay
`npm install` ni dependencias que instalar:

- **[Tailwind CSS](https://tailwindcss.com/)** — los estilos y el diseño responsive
- **[Lucide](https://lucide.dev/)** — los íconos
- **[Google Fonts](https://fonts.google.com/specimen/Inter)** — la tipografía Inter

### Colores de marca

Definidos en el bloque `tailwind.config` dentro de `index.html`:

| Nombre        | Color     | Uso                          |
| ------------- | --------- | ---------------------------- |
| `dark`        | `#0B1120` | Fondo principal              |
| `card`        | `#1E293B` | Fondo de tarjetas            |
| `accent`      | `#D4AF37` | Dorado — botones y destacados |
| `accentHover` | `#B3932E` | Dorado al pasar el mouse     |

## Cómo verlo en tu computadora

No hace falta instalar nada: alcanza con abrir `index.html` con doble clic en el navegador.

Si preferís levantarlo en un servidor local (recomendado para que las rutas
funcionen igual que en producción):

```bash
python3 -m http.server 8000
```

Y después entrá a <http://localhost:8000>.

> Los links internos son relativos (`legal/`, `../`) para que funcionen tanto en
> GitHub Pages, que sirve el sitio bajo `/resuelto/`, como con un dominio propio.
> No usar rutas que empiecen con `/`.

## Contacto

El formulario no usa servidor: abre el correo del visitante con la consulta armada,
dirigida a `santiago.maestri@gmail.com` (se cambia en el script al final de `index.html`).

## Cómo publicar cambios

El sitio se publica solo con **GitHub Pages**: cada cambio que llega a la rama
principal (`main`) queda online en un par de minutos.

```bash
git add .
git commit -m "Descripción del cambio"
git push
```
