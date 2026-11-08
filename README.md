# Asteroids

Clon del clásico arcade **Asteroids** implementado en canvas HTML5 puro, sin dependencias ni bundler.

## Descripción

Nave espacial en un campo de asteroides con envolvimiento de bordes (el espacio es toroidal). Destruye asteroides para sumar puntos: los grandes se parten en medianos, los medianos en pequeños. Incluye power-ups especiales y tipos de asteroides únicos como la estrella fugaz.

## Tecnologías

- **HTML5 Canvas** — renderizado 2D
- **JavaScript (ES6+)** — lógica del juego en un solo archivo `game.js`
- Sin frameworks, sin bundler, sin dependencias

## Cómo correr

Abre `index.html` directamente en el navegador (doble clic), o usa un servidor local:

```bash
npx serve .
```

Luego visita `http://localhost:3000`.

## Controles

| Tecla     | Acción     |
| --------- | ---------- |
| `←` `→`   | Rotar nave |
| `↑`       | Propulsar  |
| `Espacio` | Disparar   |
| `S`       | Cambiar skin de la nave |

## Puntuación

| Asteroide | Puntos |
| --------- | ------ |
| Grande    | 20     |
| Mediano   | 50     |
| Pequeño   | 100    |

## Características

- 3 vidas con invencibilidad temporal al reaparecer (parpadeo)
- Asteroides se parten en fragmentos más pequeños al ser destruidos
- Partículas de explosión al destruir asteroides
- Power-up **Velocidad**: lo sueltan asteroides (15%) y OVNIs (35%); al recogerlo, el propulsor acelera el doble durante 5 segundos
- Power-up **Triple Shot**: lo sueltan asteroides (15%) y OVNIs (35%); durante 5 segundos la nave dispara 3 balas en abanico
- Power-up **Escudo**: lo sueltan asteroides (15%) y OVNIs (35%); durante 6 segundos la nave queda protegida por un anillo verde frente a proyectiles y OVNIs
- **Estrella fugaz**: aparece cada ~15 segundos, se mueve al triple de velocidad, se desvanece a los 8 segundos y otorga 150 puntos si la destruyes
- **OVNI enemigo**: aparece cada ~10-15 segundos desde un borde, dispara proyectiles hacia la nave y otorga 200 puntos si lo destruyes
- **Skins de nave**: 4 apariencias (Clásica, Neón, Roja y Dorada) que cambian silueta, color y brillo; se seleccionan con `S` y se guardan en el navegador
