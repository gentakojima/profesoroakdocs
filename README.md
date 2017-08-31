# Documentación de Profesor Oak

Este es un esfuerzo para intentar documentar el uso del bot del Profesor Oak para Telegram. La documentación aún está muy incompleta.

## Índice

1. [Configuración del grupo](#section1)
    1. [Ver configuración actual](#secion11)
    2. [Configuración rápida](#section12)
    3. [Configuración avanzada](#section13)
    4. [Lista negra de usuarios](#section14)
    5. [Saludo y normas del grupo](#section15)
2. [Grupos relacionados](#section2)
    1. [Grupos exclusivos de color](#section21)
    2. [Grupo de administración](#section22)
3. [Organización de incursiones](#section3)
4. [Lista de nidos](#section4)

## Configuración del grupo<a name="section1">

### Ver configuración actual<a name="section11">

Hay dos comandos básicos para ver la configuración actual de Oak en el canal. Generalmente, hace falta usar ambos para conocer el estado actual.

| Comando |   |
|---------|---|
| `Oak, Configuración actual` | Muestra la configuración en un formato dirigido a usuarios, con iconos |
| `Oak, qué tienes activado?` | Muestra la configuración en un formato dirigido a admins |

### Configuración rápida<a name="section12">

Hay diversos tipos de configuraciones rápidas que se pueden aplicar a un canal. Para aplicarlas, hay que usar el comando `Oak, configuración <TIPO>`. Por ejemplo, `Oak, configuración divertida`.

| Tipo de configuración rápida | Descripción |
|------------------------------|-------------|
| `inicial`    | La configuración por defecto. Saluda a los nuevos usuarios, está en modo silencioso, permite bromas, pole y Pokégram, pero no permite juegos. No permite entrar a algunos usuarios problemáticos. |
| `divertida`  | Como la inicial, pero permite juegos y permite entrar a todos los usuarios. |
| `silenciosa` | Como la inicial, pero no permite bromas, ni pole, ni Pokégram. |
| `exclusiva` | Como la silenciosa, pero no permite entrar a ningún tipo de usuario problemático, ni usuarios sin registrar ni validar. |

### Configuración avanzada<a name="section13">

Una vez establecido un modo de partida, puedes cambiar las opciones una a una para dejarlo a tu gusto. Todos estos comandos que aceptan el parámetro `on`, tienen el efecto contrario con el parámetro `off`.

| Comando | Descripción |
|---------|-------------|
| `/set play_games on` | Activa los juegos |
| `/set pole on`     | Activa la pole |
| `/set jokes on` | Activa las bromas |
| `/set pokegram on` | Activa el Pokégram |
| `/set announce_welcome on` | Activa el mensaje de bienvenida |
| `/set require_verified on` | Activa el aviso de que es obligatorio estar validado |
| `/set require_verified_kick on` | Activa la expulsión automática a quien no esté validado |
| `/set shutup on` | Activa el modo silencioso |

Oak no contesta nada cuando pones estos comandos. Tras ponerlos, vuelve a [comprobar la configuración actual](#secion11) para asegurarte de que se han aplicado los cambios.

### Lista negra de usuarios<a name="section14">

Los usuarios pueden estar marcados con distintos _flags_ que aparecerán al preguntar a Oak quién es un usuario. Los flags existentes son los siguientes:

| Flag | Emoji | Descripción | Restringido en configuraciones rápidas |
|---------|-------------|----|-------------------------|
| `spam` | 📨 | Spammer por poner enlaces sin hablar antes en un canal | `inicial` `silenciosa` `exclusiva` |
| `rager` | 🔥 | Violento | `inicial` `silenciosa` `exclusiva` |
| `troll` | ? | Troll | `inicial` `silenciosa` `exclusiva` |
| `gps` | ? | ? | `exclusiva` |
| `hacks` | ? | Utiliza hacks o trampas en el juego | `exclusiva` |
| `fly` | ? | Utiliza fly en el juego | `exclusiva` |
| `bot` | 🤖 | Utiliza bots en el juego | `exclusiva` |

Se puede establecer una lista negra personalizada con el comando `/blacklist`, por ejemplo:

| Comando | Descripción |
|---------|-------------|
| `/set blacklist fly,hacks,rager` | Impide entrar a violentos, usuarios de fly y hacks |
| `/set blacklist off`     | Borra la lista negra |

### Saludo y normas del grupo<a name="section15">

Si tienes activado el **mensaje de bienvenida** ([ver configuración avanzada](#section13)), puedes cambiar el mensaje que mostrará Oak a los nuevos usuarios que entren al canal. Escribe `editar mensaje de bienvenida` y Oak te preguntará el nuevo mensaje.

De la misma forma, puedes cambiar las **normas del grupo** escribiendo `cambiar las normas`. Los usuarios podrán consultarlas escribiendo `normas del grupo`.

| Comando | Descripción |
|---------|-------------|
| `editar mensaje de bienvenida` | Permite cambiar el mensaje de bienvenida |
| `cambiar las normas` | Permite cambiar las normas del grupo |
| `normas del grupo` | Permite consultar las normas del grupo |

## Grupos relacionados<a name="section2">

### Grupos exclusivos de color<a name="section21">

Los **grupos exclusivos de Color** permiten mantener conversaciones de equipos privadas para el resto de los jugadores, lo que viene muy bien a la hora de organizarse por equipos.

Para crear grupos exclusivos de color debes seguir los siguientes pasos:

1. Crea un grupo nuevo y conviértelo en supergrupo, manteniéndolo privado. Este será el **grupo exclusivo de color**.
2. Invita al menos a cuatro personas más (del color del equipo correspondiente). Es necesario, porque sino Oak no querrá quedarse en el grupo.
3. Invita al grupo exclusivo a `@profesoroak_bot` y comprueba que saluda a la gente. Hazlo administrador del grupo.
4. Escribe `Oak, configuracion exclusiva`. Debería aparecer junto al resto de la configuración `Grupo de color detectado ❤️` con el color del corazón correspondiente el equipo.
5. Desde las opciones del grupo, crea un enlace para invitar al grupo si no lo tiene aún y extrae la parte después de la última barra. Por ejemplo, si el enlace es `https://t.me/joinchat/XFIXXEMXXV5xLeqXXXXX` debes quedarte con `XFIXXEMXXV5xLeqXXXXX`.
6. En el grupo exclusivo, pon `/set link_chat XFIXXEMXXV5xLeqXXXXX` para comunicar a Oak el enlace del grupo, poniendo la parte del enlace correcta. Debería aparecer junto al resto de la configuración: `✅ Link del grupo privado`.
7. En el grupo exclusivo, escribe el comando `crear unión del grupo` y Oak te enviará por privado un mensaje como este: `Unir grupo 0000MTAwMTEz00000000ODoyMD0000NzE6NT0000==`.
10. En el grupo general, un administrador debe pegar ese mensaje y Oak contestará `¡Grupo emparejado correctamente!`.

Puedes repetir este proceso para cada uno de los grupos de color. Los pasos del 1 al 7 puede hacerlos la persona que cree el grupo de color y después puede pasarle el mensaje para emparejar el grupo al administrador del grupo general para que realice el último paso.

Si preguntas `Oak, link del grupo COLOR` (por ejemplo `Oak, link del grupo rojo`) Oak enviará el enlace por privado. (Nota: actualmente no están llegando los enlaces por el bug duhow/ProfesorOak#314).

### Grupo de administración<a name="section22">

Un **grupo de administración** permite recibir las notificaciones de quién entra o sale de un canal, quién dice palabras prohibidas, o quién es kickeado. También permite introducir algunos comandos que afectarán al grupo relacionado, por ejemplo, [cambiar el saludo o las normas](#section15).

Para crear un grupo de administración debes seguir los siguientes pasos:

1. Crea un grupo nuevo y conviértelo en supergrupo, manteniéndolo privado. Este será el **grupo de administración**.
2. Invita al menos a cuatro personas más. Es necesario, porque sino Oak no querrá quedarse en el grupo.
3. Invita al grupo de administración a `@profesoroak_bot` y comprueba que saluda a la gente. Hazlo administrador del grupo.
4. Escribe `oak, dónde estoy?` y recibirás el identificador numérico del canal (¡ojo, puede ser un número negativo, es normal!). Si no funciona, puedes invitar al canal a `@groupinfobot` que hace la misma función.
5. En el grupo normal (no en el grupo de administración) escribe `/set admin_chat ID`, siendo `ID` el identificador del paso anterior.

Si lo has hecho bien, al [comprobar la configuración actual](#section11) en el grupo normal Oak te dirá que conoce el grupo administrativo.

## Organización de incursiones<a name="section3">

Para organizar una incursión, escribe un mensaje como el siguiente:
`Crear incursión de Lapras a las 14:30 en Un lugar muy especial` o `Crear raid de Lapras a las 14:30 en Un lugar muy especial`.

Si lo has escrito realmente bien y Oak es administrador del canal, además borrará el mensaje original del usuario, de forma que solo quedará el mensaje con la lista de apuntados.

Los usuarios pueden entonces apuntarse pulsando una vez en el botón `¡Me apunto!`, retirarse volviendo a pulsar una segunda vez, o avisar de que ya están pulsando en el botón `¡Ya estoy!`.

Los siguientes mensajes **no funcionarán**:

 - `Crear incursión de Lepras a las 14:30 en Un lugar muy especial` _(el nombre del Pokémon está mal escrito)_
 - `Crear incursión de Lapras a las 14.30 en Un lugar muy especial` _(la hora no está escrita en el formato correcto, debe escribirse con dos puntos)_
 - `Nueva incursión de Lapras a las 14:30 en Un lugar muy especial` _(hay que poner **crear**, no **nueva**)_
 - `Crear incursión Lapras 14:30 en Un lugar muy especial` _(faltan conectores en la frase)_


 | Comando                                          | Descripción |
 |--------------------------------------------------|-------------|
 | `crear incursión de POKEMON a las HORA en LUGAR` | Crea la incursión de `POKEMON` a las `HORA` (obligatorio formato _XX:XX_) en `LUGAR` |

## Lista de nidos<a name="section4">

Oak mantiene una lista de nidos de Pokémon. Para añadir un nido a la lista, escribe `confirmar nido de Scyther en la alameda`.

Para consultar los Pokémon que están en la lista, escribe `lista de nidos`. Puedes preguntar por un Pokémon en concreto, por ejemplo: `dónde hay scyther?` o `dónde sale scyther?`. Es obligatorio poner la **interrogación al final**.

También puedes preguntar la lista completa con sus localizaciones, escribiendo `lista completa de nidos`.

Puedes borrar un nido escribiendo `borrar nido de Scyther en la alameda`.

La lista **se reinicia automáticamente** cuando esté previsto que cambien los nidos (tradicionalmente, la madrugada del miércoles al jueves cada dos semanas).

| Comando | Descripción |
|---------|-------------|
| `confirmar nido de POKEMON en LUGAR` | Añade a la lista de nidos conocidos el `POKEMON` en `LUGAR` |
| `borrar nido de POKEMON en LUGAR` | Borra de la lista de nidos conocidos el `POKEMON` en `LUGAR` |
| `dónde hay POKEMON?`     | Pregunta la localización del nido del `POKEMON` |
| `lista de nidos`     | Pregunta la lista de Pokémon añadidos |
| `lista de nidos completa`     | Pregunta la lista completa de Pokémon añadidos con sus localizaciones |
