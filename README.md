# 🏚️ Hollowmere House: Escape Room en Python

> *Una casa sin ventanas. Una mujer a la que llamaron bruja. Cuatro llaves para salir.*

Juego de texto hecho en Python para el mini proyecto **Escape Room** del bootcamp de Data Analytics de Ironhack.

Despiertas en un sofá dentro de una casa que no conoces. Cada objeto que examinas guarda una pista y, juntas, cuentan la historia de **Isolde**: la llamaron bruja, la encerraron en esta casa y la dejaron morir. Para escapar tienes que seguir sus pistas, recoger **4 llaves** y descifrar **1 código**.

## Grupo 1

Celia · Carlota · Ilaria · Jordi · Keni · Juan

## Cómo jugar

1. Haz **Fork** de este repo (botón arriba a la derecha) y clónalo, o abre el notebook directamente en Google Colab.
2. Abre `Scape_Room_Grupo_1.Hollowmere.ipynb`.
3. Ejecuta **todas las celdas en orden** (Run All):
   - **Celda 1:** los datos del juego (habitaciones, muebles, puertas, llaves y `object_relations`)
   - **Celda 2:** las funciones (`play_room`, `explore_room`, `examine_item`...)
   - **Celda 3:** crea `game_state` y arranca la partida
4. En cada habitación escribe:
   - `explore` para ver qué hay
   - `examine` y luego el nombre del objeto, **tal cual aparece** (por ejemplo `queen_bed`)
   - `yes` cuando abras una puerta y quieras pasar

> ⚠️ Para volver a jugar, **ejecuta otra vez la celda 1**. Las llaves se sacan de los muebles con `.pop()` y no vuelven solas.

Para parar el juego a mitad, usa el botón ⏹ (Interrupt).

## El mapa

```
 game_room ──door_a──▶ bedroom_1 ──door_b──▶ bedroom_2
                                                 │
                                              door_c
                                                 ▼
             outside ◀──────door_d──────── living_room
```

| Habitación    | Objetos                                   |
|---------------|-------------------------------------------|
| `game_room`   | mirror, closet, keyboard                  |
| `bedroom_1`   | photograph, lamp, queen_bed               |
| `bedroom_2`   | laptop, bookshelf, bed                    |
| `living_room` | clock, closet_living_room (con candado 🔒) |

## Qué añadimos al juego base de Ironhack

- **Una historia propia:** todos los textos cuentan la historia de Isolde, y el final cierra el círculo con el espejo del principio.
- **Pistas (`"hint"`):** los muebles pueden tener una clave `"hint"` con un texto que te dice dónde mirar después.
- **Un candado con código (`"code"`):** `closet_living_room` solo se abre si escribes el número correcto.
- **Un mapa en línea:** `door_c` une `bedroom_2` con `living_room`, así que no hay que volver atrás.

<details>
<summary>🔑 Solución (¡spoiler!)</summary>

`keyboard` → `door_a` → `queen_bed` → `door_b` → `bed` → `door_c` → `closet_living_room` (código **317**, la hora del reloj) → `door_d`

</details>
