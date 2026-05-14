# Propeller Pro 3D — Catálogo Web

Web institucional y catálogo de productos para Propeller Pro 3D.
Hosteado gratis en GitHub Pages.

---

## 📁 Estructura

```
/
├── index.html          ← El sitio entero (HTML + CSS + JS en un solo archivo)
├── img/                ← Carpeta con todas las fotos y videos
│   ├── logo-propeller-pro.png
│   ├── protector-aspersor-t50-1.jpg
│   ├── protector-aspersor-t50-2.jpg
│   ├── protector-aspersor-t50-3.jpg
│   └── protector-aspersor-t50-video.mp4
└── README.md           ← Este archivo
```

---

## ✏️ Cómo agregar un producto nuevo

### Paso 1 — Subir las fotos a la carpeta `/img`

Antes de subirlas, **comprimilas** para que pesen poco (la web va a ir más rápida):
- Fotos: usá [tinypng.com](https://tinypng.com) — gratis, online, sin instalar nada. Que pesen menos de 500 KB cada una.
- Video: máximo 5 MB. Si pesa más, recortalo o bajale calidad.

Subí los archivos a la carpeta `img/` con nombres claros, sin espacios ni acentos. Ejemplo:
- ✅ `protector-helice-t40-1.jpg`
- ❌ `Protector hélice T40.JPG`

### Paso 2 — Editar `index.html`

Abrí `index.html` con cualquier editor de texto (recomiendo [VS Code](https://code.visualstudio.com), gratis). Buscá esta sección (está cerca del final del archivo, dentro de `<script>`):

```javascript
const PRODUCTOS = [
{
  id: "tapa-carga-rapida-agras",
  visible: true,
  nombre: "Tapa de Carga Rápida para Líquidos",
  linea: "AGRAS",
  modelos: ["DJI T40", "DJI T50", "DJI T25P"],
  proximamente: [],
  descripcion: "Tapa de carga rápida para líquidos compatible con tu DJI Agras. Fabricada en PETG de alta resistencia, se adapta perfectamente a la tapa original del dron.",
  caracteristicas: [
    "Compatible con DJI T40, T50 y T25P",
    "Material PETG de alta resistencia",
    "Se adapta a la tapa original del dron",
    "Hecho en Argentina"
  ],
  material: ["PETG"],
  colores: ["Negro"],
  presentacion: "Unidad",
  precio: null,
  moneda: "ARS",
  fotos: [
    "img/tapa-carga-rapida-1.jpeg",
    "img/tapa-carga-rapida-2.jpeg",
    "img/tapa-carga-rapida-3.jpeg",
    "img/tapa-carga-rapida-4.jpeg"
  ],
  video: "",
  badge: "NUEVO"
},
  {
    id: "protector-aspersor-t50",
    ...
  }
];
```

Para **agregar** un producto: copiá el bloque entero `{ ... }` (incluyendo la coma del final si hay otro después), pegalo abajo del último, y cambiá los datos.

Hay una **plantilla comentada** al final del array, lista para copiar. Solo descomentá las líneas (sacá los `//` del principio) y rellená los datos.

### Paso 3 — Campos de cada producto

| Campo | Qué poner | Ejemplo |
|---|---|---|
| `id` | Identificador único, sin espacios | `"protector-helice-t40"` |
| `visible` | `true` para mostrar, `false` para ocultar sin borrar | `true` |
| `nombre` | Cómo se llama el producto | `"Protector de hélices"` |
| `linea` | Línea de drones | `"AGRAS"` o `"MAVIC"` o `"UNIVERSAL"` |
| `modelos` | Modelos compatibles HOY | `["DJI T40", "DJI T50"]` |
| `proximamente` | Modelos que vienen pronto (opcional) | `["T70"]` o `[]` si no aplica |
| `descripcion` | Texto corto que vende el producto | `"Protege las hélices..."` |
| `caracteristicas` | Lista de bullets (opcional) | `["Material PETG", "Tornillos incluidos"]` |
| `material` | Materiales disponibles | `["PLA", "PETG"]` |
| `colores` | Colores disponibles | `["Negro", "Blanco"]` |
| `presentacion` | Cómo se vende | `"Unidad"` o `"Juego (par)"` o `"Set de 4"` |
| `precio` | Número en ARS, o `null` si es a consultar | `25000` o `null` |
| `moneda` | Moneda | `"ARS"` |
| `fotos` | Lista de rutas a las fotos | `["img/foto1.jpg", "img/foto2.jpg"]` |
| `video` | Ruta al video, o `""` si no hay | `"img/video.mp4"` o `""` |
| `badge` | Etiqueta arriba a la izquierda | `"NUEVO"`, `"DESTACADO"` o `""` |

### Paso 4 — Subir los cambios a GitHub

Si usás **GitHub Desktop** (recomendado, no requiere terminal):
1. Abrí GitHub Desktop
2. Vas a ver los archivos modificados a la izquierda
3. Escribí un mensaje breve abajo (ej: *"Agregué protector de hélices T40"*)
4. Clic en **Commit to main**
5. Clic en **Push origin**
6. Esperá ~1 minuto y los cambios aparecen en la web

Si usás la web de GitHub:
1. Andá al repo
2. Clic en `index.html` → ícono lápiz (editar)
3. Hacé los cambios
4. Abajo, **Commit changes**

---

## 🎨 Cambiar colores, datos de contacto, textos

Todo está en `index.html`.

- **Colores de la marca**: arriba del archivo, dentro de `:root { ... }`. Cambiá los valores hexadecimales.
- **WhatsApp / email / Instagram**: buscá `const CONFIG = {` (cerca del fin del archivo) y editá los valores.
- **Textos de la web** (hero, secciones, etc.): editá directamente el HTML, son fáciles de identificar porque están en español.

---

## 🌐 Activar GitHub Pages (solo se hace 1 vez al crear el repo)

1. Andá al repositorio en GitHub
2. **Settings** → **Pages** (en el menú izquierdo)
3. En **Source** elegí: **Deploy from a branch**
4. **Branch**: `main` / `(root)` → **Save**
5. Esperá 1-2 minutos. La URL va a ser: `https://propellerpro3d.github.io/[nombre-del-repo]/`

---

## 💬 Mensajes pre-armados de WhatsApp

Cuando un cliente hace clic en "Consultar" desde un producto, se abre WhatsApp con un mensaje listo para enviar, mencionando el producto. No hay que hacer nada para que esto funcione, está todo automático.

---

## 🆘 ¿Algo no funciona?

- Si después de editar la web se ve rota → revisá que no hayas borrado ninguna llave `{}` o coma `,`
- Si una foto no aparece → revisá que el nombre del archivo en `fotos: [...]` coincida exactamente (mayúsculas, guiones, extensión) con el archivo en `/img`
- Para volver atrás: en GitHub Desktop, clic derecho en un commit anterior → **Revert**

---

Hecho con ❤️ en Córdoba, AR.
