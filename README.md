# Cumpleaños de Shadu ♡

Página de cumpleaños estática (HTML + imágenes + música). No necesita servidor, base de datos ni build.

```
cumple-shadu/
├── render.yaml      ← configuración para Render
├── README.md
└── public/          ← todo lo que se publica
    ├── index.html
    ├── music/       ← canciones y el audio del gatito
    ├── img/         ← portada y discos del reproductor
    ├── pc/ pc2/ pc3/ pc4/   ← photocards
    ├── gal2/ gal3/  ← galería de polaroids
    └── stk/         ← stickers PNG
```

## Probar en tu computadora

```bash
cd public
python -m http.server 8000
```

Abre http://localhost:8000. (Si abres `index.html` con doble clic, la música puede no cargar; usa el servidor.)

## Subir a Render

### 1. Subir a GitHub

1. Crea un repositorio nuevo en GitHub (puede ser privado), por ejemplo `cumple-shadu`.
2. Dentro de esta carpeta:

```bash
git init
git add .
git commit -m "Pagina de cumpleaños de Shadu"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/cumple-shadu.git
git push -u origin main
```

### 2. Crear el sitio en Render

**Opción A, con el `render.yaml` (Blueprint):**

1. En Render: **New → Blueprint**.
2. Conecta el repositorio `cumple-shadu`.
3. Render detecta `render.yaml` y crea el sitio estático. Pulsa **Apply**.

**Opción B, a mano (Static Site):**

1. En Render: **New → Static Site**.
2. Conecta el repositorio.
3. Configura:
   - **Build Command:** `echo "sin build"`
   - **Publish Directory:** `public`
4. Pulsa **Create Static Site**.

En un par de minutos tendrás una URL del tipo `https://cumple-shadu.onrender.com`.

### 3. Actualizar

Cada `git push` a `main` vuelve a publicar la página automáticamente.

## Notas

- La página tiene `noindex` para que no aparezca en Google; solo entra quien tenga el enlace.
- Las canciones tienen derechos de autor: comparte el enlace solo con Shadu y no lo publiques en redes.
- La música empieza al tocar **Abrir el álbum**, porque los navegadores no dejan sonar audio sin un toque previo.
- Para cambiar la carta final, edita en `public/index.html` el texto dentro de `<p class="quote" id="lt">`.
