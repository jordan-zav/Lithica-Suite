# Modelo de licencias y monetización de Lithica Suite

## 1. Decisión principal

Lithica Suite puede mantenerse como una sola aplicación gratuita para descargar desde Google Play. No es necesario publicar una segunda versión ni distribuir un APK por separado.

La descarga gratuita no significa que todos los usuarios deban recibir acceso completo. El acceso se controla después del inicio de sesión mediante Firebase Authentication y el estado de licencia almacenado en Firestore.

El modelo tendrá tres categorías:

1. Licencia educativa o de investigación gratuita, previa verificación.
2. Licencia personal comercial, pagada mediante Google Play Billing.
3. Licencia empresarial, pagada mediante contrato y factura fuera de la aplicación.

## 2. Regla general de acceso

Toda cuenta nueva debe crearse con estado pending. Iniciar sesión no debe habilitar automáticamente las funciones protegidas.

Estados recomendados:

- pending: solicitud creada y todavía no revisada o pagada.
- enabled: licencia válida y acceso habilitado.
- expired: licencia vencida.
- disabled: acceso retirado manualmente por incumplimiento, cancelación u otra causa.

La aplicación debe consultar el estado al iniciar sesión y también actualizarlo periódicamente durante el uso. Solo el estado enabled permite entrar a las funciones sujetas a licencia.

## 3. Licencia educativa o de investigación

Esta licencia será gratuita, pero no automática.

Flujo recomendado:

1. El usuario crea su cuenta y queda en estado pending.
2. Declara que utilizará Lithica Suite exclusivamente con fines educativos o de investigación no comercial.
3. Presenta una prueba razonable, como correo institucional, carné vigente, constancia de estudios, vínculo con un centro de investigación u otro documento aceptado.
4. Se revisa la solicitud.
5. Si se aprueba, se asigna el tipo educational o research, el estado enabled y una fecha de vencimiento.
6. Al vencimiento, el usuario debe volver a acreditar su condición.

La verificación debe solicitar la menor cantidad posible de datos personales. Los documentos no deben conservarse indefinidamente si ya no son necesarios. Es preferible guardar el resultado de la verificación, la fecha y quién la aprobó.

La licencia debe indicar claramente que no permite prestar servicios pagados, producir entregables comerciales, operar para una empresa, revender resultados ni utilizar la herramienta como parte de una actividad económica. Estas definiciones deben aparecer en los términos de licencia para evitar ambigüedades.

## 4. Licencia personal comercial

Está dirigida a una persona que utiliza Lithica Suite profesionalmente y paga por su propio acceso.

Como la aplicación se distribuye mediante Google Play y la licencia habilita funcionalidad digital, la compra dentro de la aplicación debe realizarse mediante Google Play Billing, salvo que exista un programa o excepción regional aplicable.

Flujo recomendado:

1. El usuario inicia sesión y aparece como pending o sin licencia comercial.
2. Selecciona el plan personal comercial dentro de la aplicación.
3. Google Play procesa la suscripción o compra.
4. El servidor valida la compra con Google Play.
5. Después de validar, Firestore se actualiza con el tipo personal_commercial, estado enabled y fecha de vigencia.
6. Si la suscripción vence, se cancela o se reembolsa, el servidor actualiza el estado a expired o disabled.

La aplicación no debe confiar únicamente en la respuesta recibida en el teléfono. La validación y la actualización definitiva de la licencia deben realizarse desde un entorno seguro de servidor.

Si el servicio ofrece valor continuo, actualizaciones o acceso recurrente, una suscripción mensual o anual es el modelo más natural. Si se desea conceder acceso permanente, puede utilizarse una compra única no consumible.

## 5. Licencia empresarial

Está dirigida a compañías, universidades, laboratorios, consultoras u otras organizaciones que requieren varias cuentas, condiciones negociadas, soporte o facturación formal.

Google Play Billing no es una herramienta adecuada para administrar contratos empresariales, órdenes de compra, facturas, descuentos por volumen o múltiples puestos. Estas licencias se contratan fuera de la aplicación.

Flujo recomendado:

1. La organización solicita una cotización por un canal comercial externo.
2. Se acuerdan cantidad de usuarios, duración, precio, soporte, usos permitidos y condiciones de renovación.
3. Se firma el contrato y se emite la factura correspondiente.
4. Se crea o activa un registro de empresa en Firestore.
5. Se asignan los usuarios autorizados mediante companyId.
6. Mientras el contrato esté vigente, la empresa y sus usuarios permanecen en estado enabled.
7. Si el contrato vence y no se renueva, se cambia el estado de la empresa a expired o disabled y se retira el acceso de sus miembros.

La aplicación de Google Play funciona en este caso como una aplicación de acceso o consumo: el usuario descarga la misma app, inicia sesión y utiliza una licencia que ya fue contratada por su organización.

No se deben incluir dentro de la aplicación botones, enlaces o recorridos que lleven al usuario a pagar externamente por funciones digitales, salvo que Lithica Suite se inscriba y cumpla los requisitos de un programa de facturación alternativa aplicable. La negociación empresarial puede realizarse por correo, web, reunión o venta directa fuera de la aplicación.

## 6. Estructura recomendada en Firestore

Cada usuario debería contar, como mínimo, con los siguientes datos de autorización:

- uid: identificador de Firebase Authentication.
- accountType: educational, research, personal_commercial o company.
- status: pending, enabled, expired o disabled.
- companyId: identificador de la organización cuando corresponda.
- expiresAt: fecha de vencimiento de la licencia.
- verifiedAt: fecha de aprobación o validación.
- verificationMethod: método empleado para verificar al usuario.
- termsVersion: versión de los términos aceptados.
- termsAcceptedAt: fecha de aceptación.
- updatedAt: última actualización del registro.

Para las empresas conviene mantener una colección separada con:

- companyId.
- nombre legal.
- estado del contrato.
- fecha de inicio y vencimiento.
- cantidad máxima de usuarios.
- plan contratado.
- contacto administrativo.

La autorización efectiva debe considerar tanto el estado del usuario como el de su empresa. Un usuario empresarial no debe conservar acceso si el contrato de la empresa está vencido, aunque su registro individual todavía diga enabled.

## 7. Seguridad necesaria

Los campos accountType, status, companyId y expiresAt nunca deben poder modificarse desde la aplicación cliente.

Solo deben actualizarlos:

- Firebase Admin SDK desde un backend seguro.
- Una función de servidor que valide compras de Google Play.
- Un panel administrativo protegido y operado por personal autorizado.

Las reglas de seguridad de Firestore deben impedir que un usuario se habilite a sí mismo, cambie de plan, altere el vencimiento o se asigne a una empresa.

El cliente tampoco debe ser la única barrera. Las operaciones sensibles y el acceso a datos protegidos deben comprobar la licencia en el servidor o mediante reglas de Firestore. Ocultar una pantalla en la interfaz no constituye una protección suficiente.

## 8. Términos y evidencia

El aviso de que el uso gratuito es solo educativo o de investigación ayuda, pero no basta por sí solo. El usuario debe aceptar expresamente los términos antes de recibir acceso.

Debe guardarse evidencia mínima de aceptación:

- identificador del usuario.
- versión exacta de los términos.
- fecha y hora.
- tipo de licencia solicitada.
- resultado de la verificación.

Los términos deben definir los usos permitidos, los usos prohibidos, la duración, la revocación, la responsabilidad del usuario y las consecuencias del uso comercial sin licencia.

Para contratos empresariales se deben precisar número de usuarios, entidades autorizadas, sedes o filiales incluidas, vigencia, soporte, propiedad intelectual, confidencialidad y terminación. Antes de operar comercialmente a escala, estos documentos deberían ser revisados por un abogado de la jurisdicción correspondiente.

## 9. Migración desde el sistema actual

Actualmente, si todo usuario que inicia sesión queda habilitado automáticamente, debe cambiarse el flujo de creación para que las cuentas nuevas nazcan como pending.

Para usuarios existentes:

1. Clasificar las cuentas que ya tengan una licencia o autorización conocida.
2. Asignarles el tipo de cuenta y vencimiento correctos.
3. Notificar a quienes deban acreditar condición educativa o adquirir una licencia.
4. Conceder, si se desea, un periodo razonable para completar la regularización.
5. Al finalizar el periodo, pasar a pending o expired las cuentas no verificadas.

No conviene deshabilitar masivamente cuentas existentes sin aviso si se les había prometido acceso, especialmente si ya pagaron o asumieron condiciones anteriores.

## 10. Experiencia dentro de la aplicación

Después del inicio de sesión, la interfaz debe mostrar un resultado claro:

- pending: solicitud en revisión y pasos para completar la verificación permitida.
- enabled: tipo de licencia y fecha de vigencia.
- expired: licencia vencida y forma válida de renovarla.
- disabled: acceso suspendido y canal de soporte.

Para la licencia personal comercial, la aplicación puede presentar la compra mediante Google Play Billing.

Para una cuenta empresarial, la aplicación solo debe reconocer que la organización ya concedió una licencia. La contratación y el pago se gestionan externamente con la empresa.

## 11. Resultado final

Lithica Suite continuará siendo una sola aplicación gratuita en Google Play. Firebase Authentication identificará al usuario y Firestore determinará si tiene permiso.

El modelo final será:

- Estudiante o investigador verificado: acceso gratuito y temporal.
- Profesional individual: licencia comercial mediante Google Play Billing.
- Empresa: licencia por contrato y factura, con usuarios vinculados mediante companyId.
- Usuario no verificado o sin licencia: estado pending y sin acceso a funciones protegidas.

Este diseño aprovecha la infraestructura existente, evita mantener versiones separadas y permite cobrar de forma distinta según el tipo de cliente.

## 12. Referencias oficiales

- Política de pagos de Google Play: https://support.google.com/googleplay/android-developer/answer/9858738
- Explicación de la política de pagos y aplicaciones de solo consumo: https://support.google.com/googleplay/android-developer/answer/10281818
- Información de Indecopi sobre licenciamiento y uso legal de software: https://www.gob.pe/institucion/indecopi/campa%C3%B1as/1516-software-legal/

