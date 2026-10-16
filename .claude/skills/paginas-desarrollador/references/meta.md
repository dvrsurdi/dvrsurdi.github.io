# Meta — requisitos de las páginas de una app

## Fuentes

1. Meta Platform Terms (sección 3 y 4; la fuente indica «Última actualización: 3 de febrero de 2026») — https://developers.facebook.com/terms — leída el 2026-10-16.
2. Developer Policies — https://developers.facebook.com/policy/ — leída el 2026-10-16 (la página devolvió el texto de las Platform Terms; ver Dudas).
3. Configuración básica de la app (Basic settings) — https://developers.facebook.com/docs/development/create-an-app/app-dashboard/basic-settings/ — leída el 2026-10-16.
4. Data Deletion Callback — https://developers.facebook.com/docs/development/create-an-app/app-dashboard/data-deletion-callback/ — leída el 2026-10-16.
5. WhatsApp Business Messaging Policy (última actualización indicada: 23 de septiembre de 2026) — https://whatsappbusiness.com/es-la/policy/ — leída el 2026-10-16. Llegó por redirección desde https://business.whatsapp.com/policy (ver Dudas).
6. Get opt-in (WhatsApp Business Platform) — https://developers.facebook.com/documentation/business-messaging/whatsapp/getting-opt-in — leída el 2026-10-16.
7. WhatsApp app review (solution providers) — https://developers.facebook.com/documentation/business-messaging/whatsapp/solution-providers/app-review — leída el 2026-10-16.
8. App Review, guía de envío — https://developers.facebook.com/docs/resp-plat-initiatives/individual-processes/app-review/submission-guide — leída el 2026-10-16.

## Política de privacidad

- [ ] Está publicada en una URL pública, de fácil acceso, sin bloqueos geográficos y accesible para los rastreadores de Meta (**obligatoria**) [1]
- [ ] Esa misma URL está en Settings → Basic → Privacy Policy URL del panel de la app (**obligatoria**) [1]
- [ ] Explica qué datos trata la app (**obligatoria**) [1]
- [ ] Explica cómo los trata y para qué fines (**obligatoria**) [1]
- [ ] Explica cómo puede el usuario pedir la eliminación de sus datos (**obligatoria**) [1]
- [ ] Ofrece un método claro y de fácil acceso para pedir la modificación o eliminación de los datos (**obligatoria**) [1]
- [ ] Describe solo tratamientos que la app realmente hace (**obligatoria**) [1]
- [ ] No contradice las Platform Terms ni otras políticas aplicables (**obligatoria**) [1]
- [ ] Mantiene una política de privacidad publicada como parte de sus avisos de cumplimiento legal (**obligatoria**) [5]

## Borrado de datos

- [ ] Hay una URL de instrucciones de borrado o una URL de callback configurada en Settings → Basic → User Data Deletion (**obligatoria**, según la FAQ citada en [4]; ver Dudas) [3][4]
- [ ] Las instrucciones explican al usuario cómo solicitar el borrado de sus datos (**obligatoria**) [1][4]
- [ ] Si hay callback: el endpoint recibe POST con `signed_request` y usa HTTPS (**obligatoria**) [4]
- [ ] Si hay callback: la URL del callback está registrada en el campo Data Deletion Request URL (**obligatoria**) [4]
- [ ] Si hay callback: responde JSON con `url` (estado de la solicitud) y `confirmation_code` (**obligatoria**) [4]
- [ ] Si hay callback: inicia el borrado de cualquier dato de la app sobre ese usuario (**obligatoria**) [4]
- [ ] Si hay callback: la página de estado explica en lenguaje legible la situación de la solicitud (**obligatoria**) [4]
- [ ] Si hay callback y se rechaza el borrado, se da una justificación legítima (**obligatoria**) [4]
- [ ] Si hay callback: verifica la firma de `signed_request` (HMAC-SHA256 con el secreto de la app) antes de actuar (**recomendada**; la fuente lo muestra en su ejemplo y no lo marca como obligatorio) [4]
- [ ] Si hay callback: la URL de estado incluye un identificador de la solicitud (**recomendada**; ejemplo de la fuente) [4]

## Configuración de la app (campos y páginas que pide)

- [ ] Privacy Policy URL rellena en Settings → Basic (**obligatoria** para App Review, según la guía de envío; ver Dudas) [6][8]
- [ ] Terms of Service URL rellena en Settings → Basic (**obligatoria** para pasar a Live) [3]
- [ ] App Icon subido en Settings → Basic (**obligatoria** para pasar a Live) [3]
- [ ] El icono no lleva logos, marcas ni iconos de Meta, ni las palabras «Facebook» o «FB» (**obligatoria**) [3][8]
- [ ] El icono tiene 1024×1024 píxeles (**obligatoria** para App Review, según la tabla de la guía de envío) [8]
- [ ] Category rellena en Settings → Basic (**obligatoria** para pasar a Live) [3]
- [ ] User Data Deletion rellena en Settings → Basic (ver borrado de datos y Dudas) [3][4]
- [ ] La app está disponible públicamente o se dan instrucciones de acceso para los revisores de Meta (**obligatoria**) [8]
- [ ] Las instrucciones de prueba no incluyen credenciales personales de la cuenta de Meta; se usan cuentas de prueba (**obligatoria**) [8]
- [ ] La app está lista para probarse antes de enviar la solicitud (**obligatoria**) [8]
- [ ] Solo se piden los permisos que la app necesita; pedir permisos innecesarios es causa habitual de rechazo (**obligatoria**, como regla de envío) [7][8]

## WhatsApp Business Platform

- [ ] Antes del primer mensaje, la persona dio su número y aceptó expresamente recibir mensajes o llamadas de ese negocio (**obligatoria**) [5][6]
- [ ] El texto de consentimiento dice claramente que la persona acepta recibir comunicaciones del negocio y muestra el nombre del negocio (**obligatoria**) [6]
- [ ] El consentimiento cumple la legislación aplicable, incluidos los avisos y permisos que exija la ley local (**obligatoria**) [5][6]
- [ ] Los datos que Meta da sobre una persona (distintos del contenido de los chats) solo se usan para intercambiar mensajes con ella, salvo lo razonablemente necesario (**obligatoria**) [5]
- [ ] No se piden ni comparten números completos de tarjetas de pago, cuentas bancarias, documentos de identidad u otros identificadores confidenciales (**obligatoria**) [5]
- [ ] No se reenvía a un cliente información del chat de otro cliente (**obligatoria**) [5]
- [ ] Se respetan todas las solicitudes de bloqueo, baja o interrupción, y la persona se elimina de la lista de contactos (**obligatoria**) [5]
- [ ] El consentimiento se pide por categoría de mensaje (p. ej. pedidos, ofertas) y las llamadas tienen consentimiento aparte (**recomendada**) [5][6]
- [ ] Hay instrucciones claras para dejar de recibir cada categoría de mensajes, y los flujos de alta y baja son claros e intuitivos (**recomendada**) [5][6]

## Dudas

- **Privacy Policy URL:** la guía de envío [8] la marca como obligatoria para App Review, pero la página de Basic settings [3] solo marca como obligatorias para Live la Terms of Service URL, el icono y la categoría. No he podido confirmar en el panel cuál aplica.
- **User Data Deletion:** la FAQ citada en [4] exige una URL de instrucciones o de callback, pero [3] no la marca como obligatoria para Live. Sin confirmar en el panel.
- **Página sin login:** la fuente pide que la política sea accesible para los rastreadores y sin bloqueo geográfico. No dice expresamente que no pueda estar detrás de login; la regla de no-login no la he puesto por no estar en la fuente.
- **Idioma de la política:** ninguna fuente leída fija un idioma.
- **Motivos de rechazo específicos de la política de privacidad:** no he encontrado en la documentación de Meta una lista de rechazos propia de la URL de privacidad o de la página de login. Solo hay motivos generales (permisos innecesarios, revisores sin acceso, icono con marcas de Meta, falta de llamadas API por permiso avanzado, descripciones copiadas).
- **Dominio de la fuente 5:** `business.whatsapp.com/policy` redirige a `whatsappbusiness.com/es-la/policy/`, fuera de la lista de dominios permitidos. Conviene verificar el texto en `business.whatsapp.com` antes de dar la regla por firme.
- **Fecha de las Developer Policies:** no he hallado fecha de la política de desarrollador; la fuente 2 devolvió el texto de las Platform Terms.
- **Login de Facebook:** en la búsqueda apareció https://developers.facebook.com/docs/facebook-login/review/requirements, pero no se leyó; no se usa en este documento.
- **Registro del consentimiento:** [6] no exige guardar un registro del opt-in; no se ha puesto como regla.
- **Plantillas de WhatsApp y ventana de 24 horas:** fuera del alcance de las páginas públicas; no se han revisado.
