# MAGNA Abogados — Landing Web

Landing estática single-page para el estudio MAGNA Abogados (Mendoza, Argentina).

## Estructura

```
landing/
├── index.html          # Página completa (HTML + CSS embebido, sin build)
├── assets/
│   ├── logo-magna.jpeg
│   ├── logo-horizontal.png
│   └── favicon.svg
└── README.md
```

Sin dependencias, sin build step. Es un único HTML que se abre directo en cualquier navegador.

---

## 1. Configurar el formulario de contacto (5 minutos)

El formulario usa [Web3Forms](https://web3forms.com) (gratis, sin cuenta, 250 envíos/mes).

1. Ir a [web3forms.com](https://web3forms.com) y pegar el email `magna.legales@gmail.com` en el formulario de la home.
2. Recibirás una **Access Key** por email (un código largo tipo `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`).
3. Abrir `index.html` y buscar la línea:
   ```html
   <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY_HERE">
   ```
4. Reemplazar `YOUR_ACCESS_KEY_HERE` por la access key real.
5. Listo — los envíos del formulario llegarán al email de la firma.

> **Nota:** si no se configura, el formulario seguirá enviando pero Web3Forms devolverá error. Los botones "WhatsApp directo" y "Enviar un email" funcionan siempre sin configuración.

---

## 2. Probar localmente

Abrir `index.html` haciendo doble clic, o desde terminal:

```bash
open index.html
```

No requiere servidor. Funciona vía `file://`.

---

## 3. Desplegar a la web (gratis)

### Opción A — Netlify Drop (recomendado, 30 segundos)

1. Ir a [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arrastrar la carpeta `landing/` completa al recuadro
3. Se genera una URL pública inmediata tipo `https://random-name-123.netlify.app`
4. Opcional: conectar un dominio propio desde el dashboard de Netlify

### Opción B — Vercel

1. Ir a [vercel.com](https://vercel.com) e iniciar sesión
2. "Add New → Project" → subir la carpeta o conectar repo
3. Deploy automático

### Opción C — GitHub Pages

1. Subir la carpeta a un repositorio público
2. Settings → Pages → Source: `main` branch / root
3. La URL será `https://usuario.github.io/repo/`

---

## 4. Dominio propio (opcional)

Registrar el dominio en [nic.ar](https://nic.ar) (para `.com.ar`) o [namecheap.com](https://namecheap.com) (para `.com`). Luego apuntarlo al hosting elegido (Netlify/Vercel tienen guías de configuración DNS paso a paso).

Sugerencias de dominio:
- `magnaabogados.com.ar`
- `estudiomagna.com.ar`
- `magnalegales.com.ar`

---

## 5. Mantenimiento

Todo el contenido (textos, teléfonos, áreas) está en `index.html`. Para editar:

- **Cambiar teléfonos/email:** buscar `magna.legales@gmail.com` y los números `+5492616935000`, `+5492615192084`.
- **Agregar/editar áreas:** buscar el bloque `<!-- AREAS DE PRACTICA -->` y editar los `<div class="servicio">`.
- **Cambiar tagline del hero:** buscar `<h1 class="hero-tagline">`.
- **Mapa:** el iframe apunta a `Av. España 512, Mendoza`. Cambiar la query en el `src=` si se muda el estudio.

---

## 6. Checklist de verificación

- [ ] Nav fijo visible al hacer scroll
- [ ] Hero muestra panel MA · G · NA correctamente
- [ ] Las 11 áreas se ven en grid (3 columnas desktop, 2 tablet, 1 mobile)
- [ ] Mapa de Google carga en la sección contacto
- [ ] Botón flotante WhatsApp abajo a la derecha funciona
- [ ] Links `wa.me/` abren WhatsApp con el mensaje prellenado
- [ ] Link `mailto:` abre cliente de email
- [ ] Formulario envía correctamente (tras configurar Web3Forms)
- [ ] Responsive correcto en 375px, 768px y 1280px
