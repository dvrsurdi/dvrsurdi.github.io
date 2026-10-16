# CLAUDE.md

Páginas públicas de desarrollador de la cuenta de GitHub `dvrsurdi`: lo que
piden Google, Meta y demás plataformas al dar de alta una aplicación (página de
inicio, política de privacidad, condiciones, borrado de datos…). Se irán
añadiendo según se pidan.

**Antes de crear, cambiar o dar por buena una página, se usa la skill
`paginas-desarrollador`** (`.claude/skills/`): tiene lo que exige cada
plataforma y cómo revisarlo.

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
google2f72974913814721.html  verificación en Search Console: no se borra
<aplicación>/
├── index.html      qué es y qué datos usa (página de inicio para la plataforma)
├── privacidad.html política de privacidad
└── borrado-de-datos.html  cómo pedir el borrado (solo si la plataforma lo pide)
```

Una aplicación nueva = una carpeta con su nombre + su entrada en `index.html`.
Cada página lleva `<nav>` de vuelta al índice y enlaza `../estilo.css`.

**Las direcciones son públicas y están dadas de alta en consolas externas**:
renombrar o mover una página rompe la aplicación que la cita. Si hay que
moverla, se deja la antigua redirigiendo hasta que se cambie en la consola.

## Aplicaciones

| Carpeta | Plataforma | Dónde están dadas de alta las direcciones |
|---|---|---|
| `seo-tools/` | Google (Search Console, Business Profile); en Google se llama **G_Analyzer** | Google Cloud → Google Auth Platform → Branding |
| `meta/` | Meta (WhatsApp y demás): una página común para todas las aplicaciones de Meta | Meta for Developers → cada aplicación → Configuración → Básica |

## Contenido

El `<title>` y el `<h1>` de cada página llevan **el nombre exacto con que la
aplicación está dada de alta** en la plataforma: Google rechaza la verificación
de marca si no coinciden (2026-10-16). La propiedad `https://dvrsurdi.github.io/`
tiene que estar verificada en Search Console con la cuenta del proyecto de Cloud.

En castellano. Ninguna página lleva el correo personal del desarrollador: el
contacto remite al correo de asistencia que se da en cada plataforma.

**Las de `meta/` son la excepción al nombre exacto**: no llevan el nombre de
ninguna aplicación (son provisionales y cambian), ni el del desarrollador, ni
dónde están las copias de seguridad. Lo mínimo que piden la ley y Meta; la
responsable es el negocio, y el contacto y las peticiones de borrado van a él,
por correo.
