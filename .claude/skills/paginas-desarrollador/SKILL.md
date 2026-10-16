---
name: paginas-desarrollador
description: Requisitos de Google, Meta y demás plataformas para las páginas públicas de una aplicación (página principal, política de privacidad, borrado de datos) y cómo revisar que las de este repositorio los cumplen. Úsala al crear o cambiar una página de una aplicación, al revisar si cumple, antes de pedir una verificación o una revisión de la aplicación y cuando una plataforma rechace algo.
---

# Páginas de desarrollador: requisitos y revisión

Las normas de cada plataforma están en `references/`, una por archivo. Lee
**solo** la de la plataforma de la página que tocas:

| Plataforma | Archivo | Carpeta de este repo |
|---|---|---|
| Google (apps OAuth de Google Cloud) | `references/google.md` | `seo-tools/` |
| Meta (WhatsApp y demás) | `references/meta.md` | `meta/` |

## Revisar una página

1. Lee el archivo de normas de su plataforma y «Lo que nos han rechazado» (abajo).
2. Si la fecha de lectura de las fuentes tiene más de 6 meses, o la plataforma
   acaba de rechazar algo que la lista no recoge, vuelve a leer la fuente y
   pon la lista al día (fecha nueva) antes de revisar.
3. Comprueba cada regla contra el HTML publicado y lo que diga el usuario de
   la consola. Lo que solo se ve en la consola (dominio verificado, nombre de
   la app…) se le pregunta; no se da por cumplido.
4. Entrega una tabla: regla · cumple / no cumple / no se puede saber · qué
   falta. Las obligatorias que no se cumplen, primero.
5. Corrige lo que se arregla en el HTML; lo de la consola, se le explica paso
   a paso. Publica (ver `CLAUDE.md`) y comprueba la dirección en vivo.

Un texto de política describe lo que la aplicación **hace de verdad**: si no
sabes qué datos usa, se pregunta, no se inventa.

## Lo que nos han rechazado

Va aquí lo que una plataforma rechazó y la documentación no dejaba claro, con
fecha. Es lo que más vale de esta skill: anótalo cada vez.

**Meta, publicar la app (2026-10-16):** se publicó sin icono y sin URL de
borrado de datos y Meta no los exigió, aunque `meta.md` [3] marca el icono
como obligatorio para Live. En modo desarrollo, los webhooks de mensajes con
el número real llegaban sin problema durante días: Meta solo dice que
«algunos» no se envían en desarrollo.

**Google, verificación de marca (2026-10-16):**
- **Decisión: G_Analyzer no se verifica.** Es de uso propio; sin verificar
  funciona igual (solo sale el aviso de app no verificada). Lo de abajo queda
  por si alguna vez hiciera falta.
- «El nombre de la app no coincide con el de tu página principal»: el `<title>`
  y el `<h1>` de la página principal decían `seo-tools` y la app se llama
  `G_Analyzer` en la pantalla de consentimiento. Tienen que coincidir.
- «El sitio web de la URL de tu página principal no está registrado a tu
  nombre»: `https://dvrsurdi.github.io/` tiene que estar verificada en Search
  Console (propiedad «Prefijo de la URL»; `github.io` no admite «Dominio») con
  la cuenta del proyecto de Cloud. Para eso está el archivo
  `google2f72974913814721.html` en la raíz, que **no se borra**. Tras verificar,
  esperar 24 h antes de reintentar la verificación de marca.
  **Pero** la ayuda de Google ([5] de `google.md`) exige propiedad de tipo
  «Dominio» (DNS TXT), que en `github.io` no se puede hacer: es probable que
  vuelva a fallar y haga falta un dominio propio apuntando a GitHub Pages.
  Anotar aquí lo que pase al reintentar.
