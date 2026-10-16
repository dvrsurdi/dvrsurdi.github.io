# Google — requisitos de las páginas de una app OAuth

## Fuentes

1. App Homepage — Google Cloud Help — https://support.google.com/cloud/answer/13807376?hl=en — leída el 2026-10-16
2. App Privacy Policy — Google Cloud Help — https://support.google.com/cloud/answer/13806988?hl=en — leída el 2026-10-16
3. Google API Services User Data Policy — https://developers.google.com/terms/api-services-user-data-policy — leída el 2026-10-16
4. Submit for brand verification — https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification — leída el 2026-10-16
5. Domain Verification — Google Cloud Help — https://support.google.com/cloud/answer/13804266?hl=en — leída el 2026-10-16
6. OAuth 2.0 Scopes for Google APIs — https://developers.google.com/identity/protocols/oauth2/scopes — leída el 2026-10-16 (tabla de scopes leída en parcial, ver Dudas)
7. Restricted scope verification — https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification — leída el 2026-10-16
8. Sensitive scope verification — https://developers.google.com/identity/protocols/oauth2/production-readiness/sensitive-scope-verification — leída el 2026-10-16

## Página principal

- [ ] La URL de la homepage responde sin iniciar sesión (no solo a usuarios logueados) (obligatoria) [1][8]
- [ ] La homepage está en un dominio que es tuyo y puedes verificar (obligatoria) [1]
- [ ] La homepage no está alojada en Google Sites, Facebook, Instagram ni Twitter/X (obligatoria) [1]
- [ ] La homepage identifica la app o marca tal como aparece en la pantalla de consentimiento (obligatoria) [1]
- [ ] La homepage describe qué hace la app y sus funciones (obligatoria) [1][8]
- [ ] La homepage explica por qué pide datos de usuario de Google (obligatoria) [1]
- [ ] La homepage enlaza la política de privacidad (obligatoria) [1][8]
- [ ] El enlace a la política de la homepage coincide con el de la pantalla de consentimiento (recomendada) [1]
- [ ] La homepage es responsive y accesible; una URL que no responde se marca (obligatoria) [1]
- [ ] La URL es estática: no redirige a otra URL ni a otro dominio (obligatoria) [1]
- [ ] La URL no está acortada (por ejemplo, g.co no vale; sí la URL completa de google.com) (obligatoria) [1]
- [ ] El dominio de la homepage es el mismo que el de la pantalla de consentimiento (obligatoria) [1]
- [ ] La homepage es fácil de acceder, fácil de entender y relevante (obligatoria) [1]

## Política de privacidad

- [ ] Es una página HTML dedicada, no un PDF, documento ni iframe (obligatoria) [2]
- [ ] Está enlazada desde la homepage (obligatoria) [1][2][8]
- [ ] Está visible y destacada dentro de la interfaz de la app (obligatoria) [2][8]
- [ ] Está en un dominio tuyo verificado (obligatoria) [2]
- [ ] Está en el mismo dominio que la homepage, o en un dominio verificado tuyo, o en el de tu organización matriz nombrando explícitamente la app (obligatoria; basta una de las tres) [2][8]
- [ ] La URL de la política es distinta de la URL de la homepage (obligatoria) [2]
- [ ] La URL está en el campo de política de privacidad de la pantalla de consentimiento (obligatoria) [2][8]
- [ ] Si cambia la URL de la política, se actualiza también la pantalla de consentimiento (obligatoria) [2]
- [ ] Declara qué datos de Google accede la app (obligatoria) [2][8]
- [ ] Declara cómo usa esos datos (obligatoria) [2][8]
- [ ] Declara con quién los comparte, transfiere o divulga (obligatoria) [2]
- [ ] Describe las protecciones de los datos, como seguridad o cifrado (obligatoria) [2]
- [ ] Indica los plazos de conservación y de borrado, y cómo pedir el borrado (obligatoria) [2]
- [ ] Documenta cómo se accede, usa, almacena y comparte el dato, de forma completa (obligatoria) [2][8]
- [ ] No es una plantilla ni un ejemplo; es propia de la app enviada, vigente y relevante (obligatoria) [2]
- [ ] Es responsive, fácil de acceder y fácil de entender (obligatoria) [2]
- [ ] El uso de los datos se limita a lo que la política describe explícitamente (obligatoria) [3][8]
- [ ] Antes de usar los datos de una forma nueva, se actualiza la política y se pide consentimiento al usuario (obligatoria) [3]
- [ ] La política y los avisos dentro de la app son exactos, completos y fáciles de encontrar (obligatoria) [3]
- [ ] Los datos de usuario de Google se usan solo para funciones visibles y destacadas de la app (uso limitado) (obligatoria) [3][7]
- [ ] No hay publicidad personalizada, retargeting ni publicidad por intereses con datos de usuario (prohibido) [2][3]
- [ ] No se venden ni transfieren datos a intermediarios, brokers o revendedores de información (prohibido) [2][3]
- [ ] No se usan datos para decidir solvencia crediticia ni para préstamos (prohibido) [2][3]
- [ ] No se crean bases de datos a partir de datos de usuario (prohibido) [2]
- [ ] Si se usan datos para IA/ML, la política lo declara explícitamente y no se usan para entrenar modelos no personalizados ni generales (obligatoria) [2]

## Dominio y propiedad

- [ ] Se verifica el dominio de nivel superior privado (por ejemplo, example.com para sub.example.com) (obligatoria) [4]
- [ ] La verificación se hace en Search Console con propiedad de tipo **Dominio** (registro DNS TXT en el registrador); [5] dice expresamente que no vale «Prefijo de la URL» (obligatoria; comprobado releyendo [5] el 2026-10-16) [5][8]
- [ ] La cuenta que verifica es Project Owner del proyecto de Cloud (obligatoria) [5]
- [ ] Los dominios autorizados cubren los de la homepage, la política y los términos (obligatoria) [4]
- [ ] Los dominios autorizados cubren las redirect URIs o los orígenes JavaScript de los clientes de tipo "Aplicación web" (obligatoria) [4]
- [ ] Como máximo 10 dominios autorizados por solicitud (obligatoria) [5]
- [ ] El resultado de la verificación vale 7 días; el branding se publica dentro de ese plazo o hay que reverificar (obligatoria) [4]
- [ ] No se cambia el branding mientras la verificación está en curso; antes hay que cancelarla (obligatoria) [4]
- [ ] Se borran las redirect URIs y orígenes que ya no se usan, y los dominios sin uso de la pantalla de consentimiento (recomendada) [5]
- [ ] Los datos de contacto de propietario, editor y soporte están al día (recomendada) [4][7][8]

## Verificación de marca y de scopes

- [ ] La verificación de marca se completa antes de pedir la verificación de acceso a datos (obligatoria) [7]
- [ ] Todos los scopes usados están declarados en la consola de Cloud (página de acceso a datos) (obligatoria) [7][8]
- [ ] Se pide el scope más restringido que sirva a cada función (obligatoria) [7][8]
- [ ] Hay una justificación detallada de cada scope sensible (obligatoria) [8]
- [ ] Hay un vídeo de demostración del flujo de concesión y del uso de cada scope, subido a YouTube como no listado (obligatoria) [8][7]
- [ ] Se explica por qué un scope más limitado no basta (obligatoria) [7][8]
- [ ] Se confirma que la app no encaja en ninguna excepción de la verificación (obligatoria) [7][8]
- [ ] Se borran los clientes OAuth que no están listos para producción antes de enviar (recomendada) [7][8]
- [ ] La revisión de un scope sensible puede tardar unos 3-5 días hábiles (recomendada, como plazo de planificación) [8]
- [ ] Para un scope restringido, si la app guarda o transmite esos datos en servidores, hace falta una evaluación de seguridad por un tercero aprobado por Google (CASA) (obligatoria) [7]
- [ ] Para un scope restringido, la app se reverifica y se reevalúa al menos cada 12 meses (obligatoria) [7]
- [ ] Para un scope restringido, el plan de lanzamiento deja varias semanas para la verificación (recomendada) [7]

## Dudas

- **Clasificación de los scopes.** No he podido confirmar si `webmasters.readonly` es sensible, restringido o ninguno. La tabla de scopes [6] muestra su fila sin marca de sensible ni de restringido, pero la lectura fue parcial. `business.manage` no apareció en las partes leídas de la tabla. Comprobarlo en la consola (Google Auth Platform > Acceso a datos, donde se marca lo sensible). La fuente [8] define «sensible» como un scope que Google debe revisar antes de conceder acceso; la fuente [6] no define «restringido».
- **Dominio `github.io`.** Resuelta: [5] exige propiedad de tipo Dominio con registro DNS TXT, y en `github.io` el DNS es de GitHub, así que `dvrsurdi.github.io` no se puede verificar así. Hace falta un dominio propio (ver «Lo que nos han rechazado» en `SKILL.md`).
- **Declaración de cumplimiento de uso limitado.** Un resultado de búsqueda indicaba que debe haber una declaración pública y afirmativa de que el uso cumple los requisitos de uso limitado, pero la página de la política de datos leída [3] no fija texto ni ubicación. No la incluyo como regla obligatoria.
- **Términos de servicio.** La fuente [1] los dice opcionales. No los he puesto como regla.
- **Propietario frente a editor.** La página de verificación de dominio [5] en un paso dice «Owner/Editor» y en la regla dice «Project Owner». He puesto Project Owner; conviene confirmarlo en la consola de verificación.
- **Plazo de los 7 días.** Viene de [4]; no he comprobado si la consola aplica el mismo plazo.
- **Fuentes no leídas enteras.** La tabla de scopes [6] tiene más de 150.000 caracteres y solo se leyeron por partes. La página «Verification requirements» (support.google.com/cloud/answer/13464321) y la de preguntas frecuentes no se han leído.
