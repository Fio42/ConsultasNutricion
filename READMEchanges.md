# 📁 Consultas Nutrición — Documentación Completa del Proyecto

**Sitio:** Landing Page de L.N. Francisco Plesky  
**Tecnología:** HTML5 + Tailwind CSS + JavaScript ES6 puro  
**Hosting:** GitHub Pages (100% estático, sin backend)

---

## 🗂️ Estructura de archivos

```
frankplesky/
├── index.html          ← ARCHIVO PRINCIPAL (toda la landing page)
├── README.md           ← Este archivo de documentación
└── docs/               ← Documentación adicional (opcional)
```

> **Nota:** Todo el sitio vive en un solo archivo `index.html`.  
> Tailwind CSS se carga desde CDN. No hay dependencias locales.

---

## 🚀 Cómo subir a GitHub Pages — Paso a paso

### 1. Requisitos previos
- Tener [Git](https://git-scm.com/) instalado
- Tener una cuenta en [GitHub](https://github.com/)

---

### 2. Crear el repositorio en GitHub

1. Ve a https://github.com/new
2. Nombre del repositorio: `consultasnutricion` (o el que prefieras)
3. Visibilidad: **Public** (requerido para GitHub Pages gratis)
4. NO marques "Initialize with README"
5. Clic en **Create repository**

---

### 3. Comandos Git para subir el proyecto

Abre tu terminal (o Git Bash en Windows) y ejecuta estos comandos **en orden**:

```bash
# 1. Entra a la carpeta del proyecto
cd /ruta/donde/guardaste/frankplesky

# 2. Inicializa el repositorio Git
git init

# 3. Agrega todos los archivos
git add .

# 4. Primer commit
git commit -m "feat: landing page inicial - L.N. Francisco Plesky"

# 5. Cambia la rama a 'main' (estándar de GitHub)
git branch -M main

# 6. Conecta con tu repositorio de GitHub
#    (reemplaza TU_USUARIO con tu nombre de usuario de GitHub)
git remote add origin https://github.com/TU_USUARIO/consultasnutricion.git

# 7. Sube el código
git push -u origin main
```

---

### 4. Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Clic en **Settings** (pestaña superior derecha)
3. En el menú lateral izquierdo: **Pages**
4. En "Source" selecciona: **Deploy from a branch**
5. Branch: **main** / carpeta: **/ (root)**
6. Clic en **Save**

✅ En 1-3 minutos tu sitio estará disponible en:  
`https://TU_USUARIO.github.io/consultasnutricion/`

---

### 5. Cómo actualizar el sitio después de cambios

Cada vez que modifiques `index.html` y quieras publicar los cambios:

```bash
git add .
git commit -m "fix: descripción de lo que cambiaste"
git push
```

GitHub Pages se actualiza automáticamente en ~1-2 minutos.

---

## ✏️ Guía de modificaciones

### 📝 Cambiar textos del Hero

Busca en `index.html` la sección `<!-- HERO -->` y edita:

```html
<!-- Título principal -->
<h1 class="font-display ...">
  Tu mejor<br/>
  <span class="text-gradient">versión</span><br/>
  empieza hoy
</h1>

<!-- Subtítulo -->
<p class="text-white/70 ...">
  Programas de 28 días con planes nutricionales personalizados...
</p>
```

---

### 💰 Cambiar o agregar planes

Los planes están en la sección `<!-- PLANES -->`.

**Para modificar un plan existente:**
```html
<!-- Cambia el título del plan -->
<h3 class="font-display text-2xl font-bold ...">Plan para Bajar de Peso</h3>

<!-- Cambia los beneficios (lista <ul>) -->
<li>Baja % de grasa corporal</li>
<li>Control de peso efectivo</li>
<!-- Agrega o elimina <li> según necesites -->

<!-- Cambia el link de compra -->
<a href="https://consultasnutricion.com.mx/product/TU-PRODUCTO/" ...>
```

**Para agregar un tercer plan:**
Copia un bloque `<div class="bg-white rounded-3xl p-8 ...">` completo y pégalo en la grilla. Cambia `grid-cols-2` a `grid-cols-3` en el contenedor padre.

---

### 🤖 Modificar el Quiz

El quiz vive en la sección `<!-- QUIZ -->` y en el JavaScript al final.

**Cambiar preguntas del quiz:**
```html
<!-- Pregunta 1 -->
<p class="text-charcoal text-sm">¿Cuál es tu <strong>objetivo principal</strong>?</p>

<!-- Opciones -->
<button class="quiz-option ..." data-q="1" data-val="perder-peso">
  <span class="text-xl block mb-1">🔥</span>
  <span class="font-medium text-charcoal">Perder peso</span>
</button>
```

**Cambiar recomendación del quiz:**
Busca en el JavaScript el objeto `var plans = { ... }` y modifica:

```javascript
var plans = {
  'perder-peso': {
    title:    'Plan para Bajar de Peso',      // Nombre del plan
    emoji:    '🔥',                           // Ícono
    features: ['Beneficio 1', 'Beneficio 2'], // Lista de beneficios
    link:     'https://TU-LINK-DE-COMPRA/',   // URL del plan
    bg:       '#f4f7f4',                      // Color de fondo de la tarjeta
    color:    '#2d452d'                       // Color del texto
  },
  // Agrega más keys para otras respuestas del quiz
};
```

La clave del objeto debe coincidir con el atributo `data-val` del botón correspondiente.

---

### 📱 Actualizar WhatsApp

Busca todas las ocurrencias de `wa.me/5219841984819` y reemplaza con tu número:

```html
<!-- Formato: wa.me/52[CÓDIGO_PAÍS][NÚMERO_SIN_ESPACIOS] -->
<a href="https://wa.me/5219841984819?text=...">
```

El número actual es: **+52 1 984 198 4819**

**Para cambiar el mensaje pre-escrito:**
```html
<!-- Edita el texto después de ?text= (URL encoded) -->
href="https://wa.me/5219841984819?text=Hola%20Francisco%2C%20me%20interesa..."
```

Usa [urlencoder.org](https://www.urlencoder.org/) para codificar tu mensaje personalizado.

---

### 📸 Actualizar Instagram

Busca todas las ocurrencias de `instagram.com/consultasnutricion/` y reemplaza:

```html
<a href="https://www.instagram.com/TU_USUARIO/" target="_blank" ...>
```

---

### 🔗 Actualizar redes sociales

Busca los links en la sección `<!-- FOOTER -->` y en el HTML de contacto:

```html
<!-- Facebook -->
href="https://www.facebook.com/NutriologoFranciscoPlesky"

<!-- Twitter/X -->
href="https://twitter.com/ConsultasNut"

<!-- LinkedIn -->
href="https://www.linkedin.com/in/ln-francisco-plesky-0a3565145/"

<!-- YouTube -->
href="https://www.youtube.com/channel/UC2BS7zZnHeWZKBsSorpdQHA"
```

---

### 🖼️ Modificar imágenes

Las imágenes actuales apuntan al sitio original:

```html
<!-- Imagen del Hero -->
<img src="https://consultasnutricion.com.mx/wp-content/uploads/2024/12/..." />

<!-- Imagen de Sobre mí -->
<img src="https://consultasnutricion.com.mx/wp-content/uploads/2021/07/..." />
```

**Para usar imágenes propias:**
1. Sube tus imágenes a la carpeta `images/` del proyecto
2. Cambia el `src`:
```html
<img src="images/tu-foto.jpg" alt="Descripción" />
```

---

### 📰 Agregar artículos al Blog

Busca la sección `<!-- BLOG -->` y copia el bloque de un artículo:

```html
<article class="bg-white rounded-3xl overflow-hidden card-hover shadow-sm reveal delay-X">
  <!-- Cambia el emoji o pon una imagen real -->
  <div class="h-48 bg-gradient-to-br from-sage-100 to-sage-200 flex items-center justify-center text-6xl">🥗</div>
  
  <div class="p-6">
    <!-- Etiqueta de categoría -->
    <span class="pill text-xs mb-3 inline-flex">Categoría</span>
    
    <!-- Título del artículo (SEO: usa palabras clave) -->
    <h3 class="font-display text-xl font-bold ...">Tu Título del Artículo</h3>
    
    <!-- Extracto -->
    <p class="text-charcoal/55 text-sm ...">Tu extracto de 2-3 líneas aquí.</p>
    
    <!-- Link al artículo completo -->
    <a href="https://consultasnutricion.com.mx/blog/tu-articulo/" ...>Leer más →</a>
  </div>
</article>
```

Cambia `delay-X` (delay-1, delay-2, delay-3...) para la animación escalonada.

---

### 🙋 Modificar FAQ

Las preguntas frecuentes se generan dinámicamente desde JavaScript.

Busca en el `<script>` el array `var faqData = [...]`:

```javascript
var faqData = [
  {
    q: '¿Tu pregunta aquí?',
    a: 'Tu respuesta aquí.'
  },
  // Agrega más objetos { q: '...', a: '...' }
];
```

---

### 🎨 Cambiar colores del sitio

Los colores principales están en la configuración de Tailwind en el `<head>`:

```javascript
tailwind.config = {
  theme: {
    extend: {
      colors: {
        sage: { ... },   // Verde principal
        sand: { ... },   // Dorado/arena (acentos)
        cream: '#fdf8f0' // Fondo crema
      }
    }
  }
};
```

Y en el CSS personalizado (`:root` variables visuales del hero, gradientes, etc.)

---

### 📧 Configurar el formulario de contacto

El formulario actualmente **redirige a WhatsApp** con el mensaje pre-llenado.

Si quieres conectar un servicio de email real, puedes usar **Formspree** (gratis):

1. Regístrate en [formspree.io](https://formspree.io/)
2. Crea un nuevo formulario y copia tu `form ID`
3. En el JavaScript, reemplaza la función del botón:

```javascript
contactSubmit.addEventListener('click', function() {
  // Reemplaza con tu Formspree endpoint:
  // fetch('https://formspree.io/f/TU_ID', { method: 'POST', body: formData })
});
```

---

## 🔍 Optimización SEO

Las meta tags están en el `<head>`:

```html
<title>L.N. Francisco Plesky – Nutriólogo en Playa del Carmen y Cancún</title>
<meta name="description" content="Tu descripción aquí (150-160 caracteres)" />
<meta name="keywords" content="nutriólogo playa del carmen, ..." />
<meta property="og:title" content="Para redes sociales" />
<meta property="og:description" content="Para redes sociales" />
```

**Para cambiar el dominio en la canonical:**
```html
<link rel="canonical" href="https://TU-DOMINIO.com/" />
```

---

## 📊 Agregar Google Analytics (opcional)

Agrega antes del cierre de `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Reemplaza `G-XXXXXXXXXX` con tu ID de medición de Google Analytics 4.

---

## 🌐 Usar dominio personalizado en GitHub Pages

1. En tu proveedor de dominio, agrega un registro **CNAME**:
   - Host: `www`
   - Value: `TU_USUARIO.github.io`

2. En GitHub Pages (Settings → Pages), en "Custom domain" escribe:  
   `www.consultasnutricion.com.mx`

3. Activa **"Enforce HTTPS"** (aparece cuando el DNS se propague)

4. Crea un archivo `CNAME` en la raíz del proyecto con el contenido:
```
www.consultasnutricion.com.mx
```

---

## 🛠️ Solución de problemas comunes

| Problema | Solución |
|---|---|
| Las imágenes no cargan | Verifica que las URLs sean correctas. Si son locales, que el archivo exista en `images/` |
| El sitio en GitHub Pages no actualiza | Espera 2-3 min. Fuerza refresh con Ctrl+Shift+R |
| Tailwind no carga estilos | Verifica conexión a internet (usa CDN). Para producción, considera build local |
| El quiz no muestra recomendación | Verifica que `data-val` de cada botón coincida con una clave en el objeto `plans` |
| WhatsApp no abre | Asegúrate de que el número tenga código de país (52 para México) sin espacios ni guiones |

---

## 📋 Checklist antes de publicar

- [ ] Actualizar número de WhatsApp
- [ ] Verificar links de Instagram y redes sociales
- [ ] Confirmar links de planes (URLs de compra)
- [ ] Actualizar meta tags SEO con tu dominio real
- [ ] Subir fotos propias en alta resolución
- [ ] Probar el quiz completo
- [ ] Probar formulario de contacto
- [ ] Verificar que no hay errores en la consola del navegador (F12)
- [ ] Probar en móvil

---

## 📞 Información de contacto original

- **Profesional:** L.N. Francisco Plesky
- **Teléfono:** +52 1 984 198 4819
- **Ubicación:** Playa del Carmen, Quintana Roo
- **Horario:** Lun – Sab 8:00 – 18:00
- **Sitio original:** https://consultasnutricion.com.mx/
- **Facebook:** https://www.facebook.com/NutriologoFranciscoPlesky
- **Twitter:** https://twitter.com/ConsultasNut
- **LinkedIn:** https://www.linkedin.com/in/ln-francisco-plesky-0a3565145/
- **YouTube:** https://www.youtube.com/channel/UC2BS7zZnHeWZKBsSorpdQHA
