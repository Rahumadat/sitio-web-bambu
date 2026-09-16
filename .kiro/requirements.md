# Especificación de Requisitos — Sitio Web Escuela de Lenguaje Bambú

## 1. Objetivo
Crear el sitio web oficial de la **Escuela de Lenguaje Bambú**: un sitio de una sola página (One-Page), 100% responsivo (mobile-first), con navegación suave (smooth scroll).

## 2. Stack Técnico
- HTML5 semántico
- CSS3 personalizado
- Bootstrap 5 (vía CDN)
- Bootstrap Icons (vía CDN) para iconografía y redes sociales
- Scroll suave nativo (`scroll-behavior: smooth`) con `scroll-margin-top` para compensar el navbar fijo

## 3. Identidad Visual
- **Tono:** cálido, confiable, limpio y amigable.
- **Paleta de colores:**
  - Verde suave (color primario / marca / botón WhatsApp)
  - Azul suave (color secundario / acentos)
  - Blanco y grises muy claros (fondos)
- Tipografía legible y redondeada, adecuada para educación inicial.

## 4. Estructura de Secciones

### 4.1 Navbar (fijo, colapsable en móvil)
- Logo con texto "Bambú".
- Enlaces: Inicio, Nosotros, Niveles, Admisión, Extranjeros, Contacto.
- Botón destacado verde de **WhatsApp**.

### 4.2 Hero (Inicio)
- Título impactante sobre educación inicial y desarrollo del lenguaje.
- Mención a **"15 años de trayectoria (Desde 2009)"**.
- Botón CTA que hace scroll a la sección **Admisión**.

### 4.3 Sobre Nosotros
- Reseña: fundada por **3 educadoras diferenciales especialistas**.
- Enfoque en atención pedagógica especializada.
- Apoyo fonoaudiológico **100% gratuito** (financiamiento Mineduc).

### 4.4 Jornadas y Niveles
- **Jornada Mañana:** 09:00 a 13:00 hrs.
- **Jornada Tarde:** 14:00 a 17:00 hrs.
- Cuadrícula de niveles:
  - Medio Mayor (3 años)
  - Pre-Kínder (4 años)
  - Kínder (5 años)

### 4.5 Proceso de Admisión (Paso a Paso)
- **Paso 1:** Agendar Evaluación Fonoaudiológica Gratuita para diagnóstico de TEL.
- **Paso 2:** Presentar Certificado de Nacimiento e Informe Fonoaudiológico anterior (si posee).
- **Paso 3:** Acreditación de residencia y formalización de matrícula.

### 4.6 Admisión para Extranjeros (bloque destacado)
- Explicar requisitos de regularización.
- Obtención del **Identificador Provisorio Escolar (IPE)** si no tienen RUN.
- Validación de documentos para incorporación al sistema escolar chileno.
- Tono claro y acogedor.

### 4.7 Contacto y Pie de Página
- **Dirección:** Calle Chagüal 719, Sector Larapinta, Comuna de Lampa, Región Metropolitana.
- **Correo:** escuelabambu@gmail.com (enlace `mailto:`)
- **Teléfono:** +56 44 319 3236 (enlace `tel:`)
- Botón flotante / destacado de **WhatsApp** con el número de contacto.
- Redes sociales: iconos de **Facebook** e **Instagram**.
- **Mapa interactivo:** contenedor `iframe` (placeholder) para Larapinta.

## 5. Requisitos No Funcionales
- Responsivo en móvil, tablet y escritorio.
- Accesibilidad básica: contraste adecuado, `alt` en imágenes, roles/labels ARIA donde corresponda.
- Botón flotante de WhatsApp visible en todo el scroll.
- Código organizado y comentado.

## 6. Estructura de Archivos
```
Sitio_Web_Bambu/
├── index.html
├── css/
│   └── styles.css
└── assets/
    └── (imágenes / logo)
```

## 7. Datos de Contacto (reales)
| Campo      | Valor                                                                    |
|------------|--------------------------------------------------------------------------|
| Dirección  | Calle Chagüal 719, Sector Larapinta, Comuna de Lampa, Región Metropolitana |
| Correo     | escuelabambu@gmail.com                                                   |
| Teléfono   | +56 44 319 3236                                                          |
| WhatsApp   | +56 44 319 3236                                                          |
| Trayectoria| 15 años (desde 2009)                                                     |
