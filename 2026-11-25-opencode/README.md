# Clase 1 · Construye con Claude desde OpenCode

**Miércoles 25 de noviembre de 2026 · 7:00 a 8:15 p. m. (hora de Colombia) · en vivo por YouTube**

Con lo que ya tienes (tus créditos de la API de Claude o una cuenta gratis de claude.ai) construyes, paso a paso, una
simulación 3D del proceso de fisioterapia para una hernia discal lumbar, y entiendes cómo trabaja un agente de código.

> **Aviso:** es una demo educativa y no reemplaza la valoración de un profesional de la salud.

## Agenda

| Hora | Qué |
|---|---|
| 7:00 | Bienvenida, qué vamos a construir y cuál camino vas a seguir (votación en iacaribe.org/vivo) |
| 7:05 | Qué es un agente de código |
| 7:12 | Instalar OpenCode y conectar Claude con tu llave de la API |
| 7:28 | Plan y Build: pensar antes de construir |
| 7:33 | **Primera ronda de preguntas** · primer prompt: el plan |
| 7:38 | Construimos en vivo: la columna en 3D y las etapas de la atención |
| 7:57 | Los ejercicios (tu reto) y pulir el resultado |
| 8:01 | **Segunda ronda de preguntas** |
| 8:07 | AGENTS.md: las instrucciones de tu proyecto |
| 8:10 | Tu reto y la convocatoria de proyectos |
| 8:15 | Cierre |

Empezamos a las 7:00 en punto. Las preguntas van en dos rondas fijas; lo que no alcancemos a responder se responde por
escrito en la comunidad al día siguiente.

## Elige tu camino

| Camino | Para quién | Con qué |
|---|---|---|
| **A** (el que se ve en pantalla) | Tienes créditos de la API de Claude | OpenCode + Claude con tu llave de la API |
| **B** | No tienes créditos o no pudiste instalar | claude.ai gratis, en el navegador |
| **C** | Quieres practicar OpenCode sin gastar | OpenCode con un modelo gratis (el resultado es más sencillo) |

Seguir el camino A completo cuesta unos USD 4 en créditos de la API. Si no quieres gastarlos, ve por el camino B.

## Prepárate antes (10 minutos)

**Si tienes créditos de la API de Claude:**
1. Descarga la app de escritorio de OpenCode desde [opencode.ai](https://opencode.ai) (Mac o Windows).
2. Entra a [platform.claude.com](https://platform.claude.com) y toca «Obtener clave de API». Si te pregunta dónde se
   ejecuta tu código, elige «En otro lugar». Crea la llave y guárdala: es como una contraseña.
3. Abre OpenCode, escribe `/connect`, elige Anthropic y pega tu llave. Pega **solo** el texto que empieza por `sk-ant-`,
   no el ejemplo de código que trae alrededor (si lo pegas, OpenCode responde `invalid x-api-key`).
4. Con `/models` elige **Claude Sonnet 5.5**.

**Si no tienes créditos:** no instales nada. Crea tu cuenta gratis en [claude.ai](https://claude.ai) y sigues la clase
con los mismos prompts.

**Importante:**
- Usa la **llave de la API**, no tu suscripción de claude.ai: conectar la suscripción a otras herramientas no está
  permitido y arriesga tu cuenta.
- Nunca pegues tu llave en un chat ni la muestres en una captura.
- En los modelos gratis no pongas datos personales: algunos guardan lo que escribes.

## Lo que hay que saber de OpenCode

- **Plan** piensa sin tocar archivos; **Build** escribe y ejecuta. Se cambia con **Shift+Tab**. Empieza siempre en Plan.
- `/undo` deshace el último cambio, pero solo dentro de un repositorio Git: crea tu carpeta y corre `git init` (o pídeselo a OpenCode).
- OpenCode lee las instrucciones de tu proyecto desde `AGENTS.md` (`/init` lo crea).

## Los prompts

Funcionan igual en OpenCode (camino A y C) y en un chat de claude.ai (camino B). Todo vive en un solo archivo HTML.

### Prompt 0 · Planear
En OpenCode, en modo **Plan**. En claude.ai, agrega «no escribas código todavía».
```
Quiero construir una simulación 3D educativa, en un solo archivo HTML con three.js cargado desde un CDN, que muestre el
proceso de atención de fisioterapia para una hernia discal lumbar en L4-L5. Debe tener:
1. Un modelo simple de la columna lumbar (vértebras L1 a S1 y sus discos) que se pueda girar con el mouse o el dedo, sin
   OrbitControls.
2. La hernia en el disco L4-L5 resaltada, presionando la raíz nerviosa.
3. Un panel lateral con las etapas de la atención: valoración, educación al paciente, control del dolor, ejercicios y
   progresión hasta el alta. Botones Anterior y Siguiente.
4. Textos en español y un aviso visible: «Demo educativa. No reemplaza la valoración de un profesional de la salud».
Antes de escribir código, dame el plan: qué piezas vas a construir, en qué orden y cómo las vas a probar.
```
Si el plan termina con preguntas, puedes responder «usa lo que asumiste».

### Prompt 1 · La columna
En OpenCode, pasa a **Build** (Shift+Tab).
```
Construye el paso 1 del plan: la página con la escena, la columna lumbar L1–S1 con sus discos, la hernia en L4-L5 en un color
que resalte y la rotación con mouse y dedo. Que se vea bien en el celular.
```

### Prompt 2 · Las etapas
```
Agrega el panel de etapas con Anterior y Siguiente. En cada etapa la cámara se mueve y resalta lo importante: en valoración,
la hernia y el nervio; en ejercicios, la zona lumbar. Cada etapa tiene un título y dos o tres frases claras para un paciente.
```

### Prompt 3 · Los ejercicios (tu reto en casa)
```
En la etapa de ejercicios agrega una figura humana simple, hecha con cilindros y esferas, que haga en bucle tres ejercicios:
extensión lumbar boca abajo, puente de glúteos y bird-dog (cuatro apoyos, brazo y pierna contrarios). Un botón para cambiar de
ejercicio y el nombre del ejercicio en pantalla.
```

### Prompt 4 · Pulir
```
Revisa todo: que no haya errores en la consola, que los textos quepan en el celular, que el aviso educativo se vea siempre y
que el código esté comentado en español. Dime qué cambiaste.
```

El agente nunca construye dos veces lo mismo: tu resultado será distinto al de la clase, y está bien. Si algo sale mal,
`/undo` y vuelve a pedirlo con más detalle.

## Tu reto

1. Corre el prompt 3 en casa.
2. Adapta la simulación a un caso de tu campo: otra lesión (rodilla, hombro), un proceso de tu área (un cultivo, un trámite
   legal, un experimento) o algo de tu trabajo.
3. Comparte una captura en tu grupo de la comunidad y **súbelo a la convocatoria de proyectos en
   [iacaribe.org/proyectos/nuevo](https://iacaribe.org/proyectos/nuevo) antes del domingo 29 de noviembre, 11:59 p. m.**
   Los mejores de cada vertical presentan su demo en el en vivo del miércoles 2 de diciembre.
