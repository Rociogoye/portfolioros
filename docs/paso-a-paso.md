# Cómo construir y mantener el portfolio

## 1. Preparar el entorno

Este proyecto utiliza Hugo y el tema Hugo Profile. Para comprobar que Hugo está instalado:

```bash
hugo version
```

El tema se encuentra en `themes/hugo-profile` y la configuración principal está en `hugo.yaml`.

## 2. Ejecutar el portfolio en local

Desde la carpeta del proyecto:

```bash
hugo server -D
```

Después, abrir `http://localhost:1313` en el navegador. La opción `-D` también muestra los contenidos marcados como borrador.

## 3. Editar la portada

Los textos de presentación, la formación, las tecnologías, el contacto, los colores y el modo nocturno se modifican en `hugo.yaml`.

Las secciones que todavía no tienen contenido, como experiencia y logros, están desactivadas. Se pueden activar cambiando su propiedad `enable` a `true`.

## 4. Editar los proyectos

Cada proyecto tiene su propio archivo dentro de `content/projects`:

- `la-emmapp.md`
- `escuela-de-verano.md`
- `elita-tarot.md`

La información situada entre los separadores `---` controla la tarjeta: título, resumen, imagen, etiquetas y enlaces. El texto restante forma la página de detalle.

## 5. Añadir un proyecto nuevo

Crear un archivo con este formato:

```markdown
---
title: "Nombre del proyecto"
date: 2026-07-14
description: "Descripción para buscadores."
summary: "Resumen corto para la tarjeta."
image: "/images/projects/imagen.jpg"
badges: ["HTML", "CSS"]
tags: ["HTML", "CSS"]
weight: 4
---

## El proyecto

Explicación del proyecto, el problema, el proceso y el resultado.
```

Guardar la imagen correspondiente en `static/images/projects`.

## 6. Cambiar la estética

La paleta principal está declarada en `hugo.yaml`, dentro de `params.color`. Hay una paleta clara y otra específica para el modo oscuro.

Los ajustes visuales adicionales se encuentran en `static/css/custom.css`. El archivo `layouts/partials/head/extensions.html` carga esos estilos sin modificar directamente el tema, lo que facilita actualizarlo en el futuro.

## 7. Modo nocturno

El portfolio comienza en modo oscuro porque `defaultTheme` tiene el valor `dark`. El botón de la navegación permite alternar entre modo claro y oscuro, y el navegador recuerda la elección.

Para iniciar en modo claro, cambiar:

```yaml
defaultTheme: "light"
```

## 8. Generar la versión para publicar

Antes de publicar, cambiar `baseURL` en `hugo.yaml` por el dominio definitivo. Después ejecutar:

```bash
hugo --minify
```

Hugo generará el sitio terminado dentro de la carpeta `public`.

## 9. Información que falta completar

- Fotografía o retrato definitivo de Rocío.
- Correo profesional o enlace de LinkedIn.
- Enlace y capturas reales de Escuela de Verano.
- Diseño y desarrollo final de Elita Tarot.
- Capturas actualizadas de La EmmApp cuando cambie su interfaz pública, o una ilustración de sustitución si no hay una captura reciente disponible.
