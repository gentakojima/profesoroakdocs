# Documentación de Profesor Oak

Este es un esfuerzo para intentar documentar el uso del bot del Profesor Oak para Telegram. La documentación aún está muy incompleta.

## Índice

1. [Configuración básica del canal](#section1)
 1. [Ver configuración actual](#secion11)
 2. [Configuración rápida](#section12)
 3. [Configuración avanzada](#section13)
 4. [Configuración fina](#section14)

## Configuración básica del canal<a name="section1">

### Ver configuración actual

Hay dos comandos básicos para ver la configuración actual de Oak en el canal. Generalmente, hace falta usar ambos para conocer el estado actual.

| Comando |   |
|---------|---|
| `Oak, Configuración actual` | Muestra la configuración en un formato dirigido a usuarios, con iconos |
| `Oak, qué tienes activado?` | Muestra la configuración en un formato dirigido a admins |

### Configuración rápida

Hay diversos tipos de configuraciones rápidas que se pueden aplicar a un canal. Para aplicarlas, hay que usar el comando `Oak, configuración <TIPO>`. Por ejemplo, `Oak, configuración divertida`.

| Tipo de configuración rápida | Descripción |
|------------------------------|-------------|
| `inicial`    | La configuración por defecto. Saluda a los nuevos usuarios, está en modo silencioso, permite bromas, pole y Pokégram, pero no permite juegos. No permite entrar a algunos usuarios problemáticos. |
| `divertida`  | Como la inicial, pero permite juegos y permite entrar a todos los usuarios. |
| `silenciosa` | Como la inicial, pero no permite bromas, ni pole, ni Pokégram. |
| `exclusiva` | Como la inicial, pero no permite bromas, ni pole, ni Pokégram. No permite entrar a ningún tipo de usuario problemático, ni usuarios sin registrar ni validar. |

### Configuración avanzada

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

### Lista negra de usuarios

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
