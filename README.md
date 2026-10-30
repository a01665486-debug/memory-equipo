# Memory - Proyecto colaborativo

## Descripción

Adaptación del juego Memory de Free Python Games, desarrollado
en Python con Turtle Graphics.

El jugador busca parejas de casillas con el mismo contenido.
Las parejas encontradas se retiran para revelar una imagen.

## Fuente original

Código base de Grant Jenks:

https://grantjenks.com/docs/freegames/memory.html

El código se obtuvo con:

```bash
python -m freegames copy memory
```

El primer commit conserva el archivo original sin modificaciones.

## Integrantes

| Nombre | Matrícula | GitHub | Rol |
|---|---|---|---|
| Diego Lemus Mejía | A01665486 | a01665486-debug | Dueño / Main |
| Yerik Escobar Asprón | A01829079 | Yeaspron | Fork |

Yerik contribuye desde su propio fork, sin acceso de colaborador
al repositorio original.

## Instalación

Se requiere Python 3 con Turtle y Tkinter.

Desde la carpeta del repositorio:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Cada integrante crea su ambiente virtual. La carpeta `.venv/`
no se incluye en GitHub.

## Ejecución

Con el ambiente activado:

```bash
python memory.py
```

Para sesiones posteriores:

```bash
source .venv/bin/activate
python memory.py
```

Para salir del ambiente:

```bash
deactivate
```

## Controles

- Clic izquierdo: seleccionar una casilla.
- Seleccionar dos casillas con el mismo contenido permite retirar
  la pareja.
- Para reiniciar, cerrar la ventana y ejecutar otra vez el programa.

## Reparto de funcionalidades

| Responsable | Funcionalidad | Estado |
|---|---|---|
| Diego | Contar y mostrar taps | HECHO |
| Diego | Detectar que se completó el tablero | Pendiente |
| Yerik | Centrar el contenido en las casillas | Pendiente |
| Yerik | Sustituir números por elementos memorables | Pendiente |

## Acuerdos de colaboración

- Cada funcionalidad tendrá un commit separado.
- Las contribuciones se integrarán mediante pull requests.
- Diego modificará el estado, la selección de casillas y el marcador.
- Yerik modificará los valores de las parejas y su presentación.
- Se conservarán 64 casillas y 32 parejas.
- Cada valor deberá aparecer exactamente dos veces.
- No se cambiará la comparación entre parejas basada en `tiles`.
- Cada integrante documentará sus modificaciones y pruebas.
- Después de integrar los cambios se probará el juego completo.

## Pruebas

Los resultados se registrarán después de realizar las pruebas.

| Prueba | Resultado esperado | Resultado observado |
|---|---|---|
| Inicio | El juego abre y muestra el tablero | HECHO  |
| Contador | Aumenta por cada clic aceptado sobre una casilla oculta | HECHO |
| Clic fuera del tablero | No cuenta y no provoca errores | HECHO |
| Pareja resuelta | No vuelve a seleccionarse ni aumenta el contador | HECHO |
| Victoria | Se anuncia al resolver las 32 parejas | Pendiente |
| Fin de partida | El contador deja de aumentar | Pendiente |
| Centrado | El contenido aparece centrado en la casilla | Pendiente |
| Nuevos elementos | Se pueden reconocer y emparejar correctamente | Pendiente |

## Problemas encontrados

Pendiente de registrar durante el desarrollo.

Se documentarán únicamente problemas reales, su solución y
la comprobación realizada.

## Evidencias

El repositorio conserva el código, los commits individuales,
los pull requests y sus merges.

Para consultar el historial:

```bash
git --no-pager log --graph --oneline --all
```


# Contador de taps:

El contador registra cada clic dentro del tablero sobre una casilla todavía oculta. 
Los clics fuera del tablero y sobre parejas resueltas se ignoran. 
Un clic repetido sobre una casilla pendiente también cuenta.
