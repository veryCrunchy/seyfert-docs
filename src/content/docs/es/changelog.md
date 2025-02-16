---
title: Registro de cambios
description: Cambios en Seyfert
---

## Cambios en la versión 2.2.0

**Cambios importantes:**
- Los threads ya no forman parte de la caché principal; ahora se fusionan con los canales.
- `WorkerAdapter` ya no es el adaptador de caché predeterminado del `WorkerClient`.
- Se cambiaron las funciones `Context.guild`, `Context.channel` y `Context.me` para usar el modo `flow` por defecto.
- Se eliminaron las ubicaciones `output` y `templates` del archivo de configuración.
- Se eliminó el parámetro `updateOnly` del metodo `patch` en el adaptador de caché.

**Correcciones:**
- Se solucionaron problemas con las conexiones zombie.
- Se corrigió la implementación de `workerProxy` en el `WorkerClient`.
- Se corrigió el método `edit` en `GuildRole`.
- Se corrigió que `ModalInteraction.member.roles` no devolvía los datos correctos.
- Se corrigió el callback `refresh` del collector.
- Se corrigió `guildMemberRemove` para obtener el objeto correcto de `GuildMember` anterior.

**Adiciones:**
- Se añadió `Client.latency` para obtener la latencia de todos los shards.
- `cache.disabledCache` ahora puede ser una función que devuelva dinámicamente `true`/`false` según el parámetro `cacheType`.
- Se añadieron los métodos `addRole` y `removeRole` a `BaseGuildMember`.
- Se mejoró el mensaje de error para "archivo de configuración no encontrado".
- Los escuchadores de componentes ahora incluyen una función `onPass`.
- Se añadió soporte para la API de Soundboard con funcionalidades para `get`, `upload`, `list` y `delete`.
- Se añadió un acortador de soundboard en el `Client`.
- Se añadieron eventos personalizados en el `WorkerClient`.
- Se introdujo el resharding, habilitando la creación y eliminación automática de shards según sea necesario en el `WorkerClient`.
- Los objetos `attachment` ahora soportan `ArrayBuffer`, `Uint8ClampedArray` y `Uint8Array` (tipos actualizados).
- `option.value` infiere automáticamente las `option.choices` especificadas, si están disponibles.
- `options.value` ahora devuelve el mismo tipo que se especifica en `option.channel_types`.
- Se introdujeron `Guild...Context` y `Context.inGuild()` para garantizar los datos del gremio para comandos no utilizables en mensajes directos.
- Se añadió un método `deferUpdate` para `ComponentContext`.
- Los métodos setter de Embed (por ejemplo, `addField`, `setDescription`) ahora soportan `undefined` como parámetro válido.
- La configuración de Seyfert ahora es extendible utilizando `ExtendedRC` para tipos y `ExtendedRCLocations` para `config.locations`.
- Se añadió una utilidad `generateOAuth2URL` en los formateadores.
- Se añadió soporte para Deno y Bun.
- Se introdujo una forma más corta para `voiceStates`, accesible a través de `client.voiceStates`.
- Se mejoraron los mensajes de error de la API de Discord.
- Se añadió un callback `onRatelimit` en `ApiHandler` (rest).
- Se añadieron tipos de evento de webhook para `applicationAuthorized`, `entitlementCreated` y `questUserEnrollment`.
- `HttpServerAdapter` ahora soporta cualquier tipo de `Client` (`HttpClient`, `Client` o `WorkerClient`).
- Se añadió `channel.messages.list()` para obtener todos los mensajes de un canal.