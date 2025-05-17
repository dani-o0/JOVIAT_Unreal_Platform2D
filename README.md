# Plataformas 2D - Dani Oller Fernandez

## 🎮 Controles

- **A / D**: Moverse a la izquierda / derecha
- **Espacio**: Saltar
- **Shift Izquierdo**: Dash
- **Ctrl Izquierdo**: Agacharse
- **Click Izquierdo del ratón**: Disparar

---

## Características principales

### 🏁 Checkpoints

- Los **checkpoints** guardan la posición actual del jugador y los power ups obtenidos.
- Al iniciar el juego, el jugador puede:
  - Empezar una partida desde cero.
  - Cargar la partida guardada (si existe).

#### Cómo funcionan los checkpoints

- Cada checkpoint tiene un **índice único** (`index`).
- Cuando el jugador alcanza un checkpoint, se guarda el índice para saber hasta dónde ha llegado.
- En el `BeginPlay` de cada checkpoint:
  - Se comprueba si hay datos guardados.
  - Si el índice del checkpoint es menor que el último índice guardado, se elimina automáticamente con `DestroyActor`. Esto evita que el jugador pueda guardar en checkpoints anteriores.

---

### ⚡ Power Ups

- Los power ups se guardan automáticamente al alcanzar un checkpoint.
- Si ya has conseguido un power up y cargas la partida:
  - El juego comprueba si ya lo tienes.
  - En caso afirmativo, el power up se destruye para que no aparezca de nuevo si el jugador vuelve atrás.

#### Tipos de Power Ups

- **Doble salto**: permite al jugador realizar un segundo salto en el aire.

![image](https://github.com/user-attachments/assets/90a4d3e9-742b-44d4-b29e-cd6fc5fcaac7)
- **Dash**: permite al jugador impulsarse rápidamente hacia una dirección.

![image](https://github.com/user-attachments/assets/da146890-616e-4847-af0e-6301cfe06b48)

---

### 🌍 Elementos del Mapa

- **Jumper**: plataforma que lanza al jugador hacia arriba.

![image](https://github.com/user-attachments/assets/ce2b7432-541f-4d34-9fdf-d49e1998a2ac)
- **Plataforma movible**: se desplaza siguiendo un patrón predefinido.

![image](https://github.com/user-attachments/assets/2d8fcf28-4863-4922-838f-c7a7d2dff7fb)
- **Power ups**: potenciadores que el jugador puede recoger.

![image](https://github.com/user-attachments/assets/da146890-616e-4847-af0e-6301cfe06b48)

![image](https://github.com/user-attachments/assets/90a4d3e9-742b-44d4-b29e-cd6fc5fcaac7)
- **Torretas**: enemigos estáticos que disparan y pueden ser destruidos.

![image](https://github.com/user-attachments/assets/a5961e6c-b7d6-41f4-923e-4a6055f1fc5c)

---

## 💾 Guardado de Partida

El juego utiliza un sistema de guardado automático al llegar a los checkpoints. Este sistema incluye:

- Posición del jugador.
- Power ups recogidos.
- Último checkpoint alcanzado.
