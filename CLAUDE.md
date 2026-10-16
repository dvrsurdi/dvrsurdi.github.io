# CLAUDE.md

Páginas públicas de desarrollador de la cuenta de GitHub `dvrsurdi`: lo que
piden Google, Meta y demás plataformas al dar de alta una aplicación (página de
inicio, política de privacidad, condiciones, borrado de datos…). Se irán
añadiendo según se pidan.

## Cómo se publica

GitHub Pages sirve la rama `main` desde la raíz en `https://dvrsurdi.github.io/`.
Un `git push` publica en un par de minutos. Es HTML estático, sin compilación.

El repositorio es de la cuenta `dvrsurdi`, no de `RitaLee79`: el remoto usa el
alias SSH `github-dvrs` y el autor está fijado en el `.git/config` local. No
cambiarlo al clonar en otro equipo sin rehacer las dos cosas.

## Estructura

```
index.html          índice: una entrada por aplicación
estilo.css          estilo común
privacidad.html     redirección de la dirección antigua de seo-tools (ver abajo)
<aplicación>/
├── index.html      qué es y qué datos usa (página de inicio para la plataforma)
└── privacidad.html política de privacidad
```

Una aplicación nueva = una carpeta con su nombre + su entrada en `index.html`.
Cada página lleva `<nav>` de vuelta al índice y enlaza `../estilo.css`.

**Las direcciones son públicas y están dadas de alta en consolas externas**:
renombrar o mover una página rompe la aplicación que la cita. Si hay que
moverla, se deja la antigua redirigiendo hasta que se cambie en la consola.

## Aplicaciones

| Carpeta | Plataforma | Dónde están dadas de alta las direcciones |
|---|---|---|
| `seo-tools/` | Google (Search Console, Business Profile) | Google Cloud → Google Auth Platform → Branding |

`privacidad.html` de la raíz es la dirección que tenía seo-tools hasta el
2026-10-16; se borra cuando Google Cloud apunte ya a `seo-tools/privacidad.html`.

## Contenido

En castellano. Ninguna página lleva el correo personal del desarrollador: el
contacto remite al correo de asistencia que se da en cada plataforma.
