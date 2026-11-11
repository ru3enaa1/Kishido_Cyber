<div align="center">

# Kishidō · 騎士道

**Un acompañante con IA para aprender ciberseguridad practicando: te orienta por etapas
mientras resuelves un reto, sin darte la solución, y guarda tus notas.**

Y, con el mismo peso, lo que **no** hace: no aloja laboratorios, no entrega banderas y no
es una herramienta contra sistemas reales.

[![Java](https://img.shields.io/badge/Java-25-orange?logo=openjdk)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1-6DB33F?logo=spring)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Estado](https://img.shields.io/badge/estado-en%20desarrollo-FF2E88)](#estado)
[![Licencia](https://img.shields.io/badge/licencia-propietaria-A39E94)](#licencia)

<br>

<img src="docs/capturas/01-tablero.png" width="900"
     alt="El tablero de Kishidō: el paladín Shirogane vuela desde la izquierda y su espada señala el cofre de la etapa; detrás, un castillo japonés en grabado dentro de un corte de papel con paisaje; abajo a la izquierda, la barra de recorrido en la etapa 3 de 5; a la derecha, el pergamino de tesoros">

<sub>Diseño aprobado de la pantalla principal (mockup). El programa está en construcción:
todavía no hay capturas del producto real.</sub>

</div>

> **In English.** Kishidō is an AI companion for people learning offensive security
> through practice challenges (CTFs and retired training machines). It walks the learner
> through five stages, suggests which tools fit the stage they are in, and gives
> spoiler-free guidance on the output they paste, so they keep solving the challenge
> themselves. It keeps their findings as notes they can export as Markdown. It does not
> host labs, it never hands over the flag, and it only works on environments the learner
> is authorized to practice on. Spanish-first. Built with Java 25, Spring Boot 4 and
> PostgreSQL. Currently in development: what you see here is the approved design, not
> the running product.

---

## El problema

Quien empieza en ciberseguridad ofensiva se atasca pronto, y las dos salidas habituales
le enseñan poco: mirar la solución completa de otro, o pedirle a un chatbot que resuelva
el reto. En los dos casos el reto queda resuelto y la persona no aprendió a pensar el
siguiente paso. Además, casi todo el material de apoyo está en inglés.

## Qué hace Kishidō

| | |
|---|---|
| **1 · Ordena el reto en cinco etapas** | Reconocimiento, entrada, pasillos, cuarto y cámara. Siempre se sabe en qué punto se está y qué queda |
| **2 · Abre el cofre de la etapa** | Un catálogo fijo de herramientas para esa etapa, cada una con su documentación oficial, y una guía de enfoque. Funciona aunque la IA no esté disponible |
| **3 · Orienta sin spoilers** | El aprendiz pega la salida de su terminal y recibe una pista sobre cómo leerla y qué mirar después. Nunca la bandera ni el paso exacto |
| **4 · Guarda los tesoros** | Cada hallazgo se anota en su etapa, y se cuenta cuántos cuartos se han explorado |
| **5 · Exporta las notas** | En Markdown, y sin el texto de la IA por defecto: las notas son de quien las escribió |

## El tablero

El centro de la pantalla es **Shirogane** (白銀), un paladín de armadura plateada. Su
espada señala siempre el cofre, que es la acción principal. Detrás, la mazmorra cambia
de escena con cada etapa del recorrido.

<table>
<tr>
<td width="50%"><img src="docs/capturas/02-etapa-reconocimiento.png" alt="Etapa 1, reconocimiento: el castillo entero visto desde fuera"></td>
<td width="50%"><img src="docs/capturas/03-etapa-entrada.png" alt="Etapa 2, entrada: la puerta principal del castillo, cerrada"></td>
</tr>
<tr>
<td><sub><b>01 · Reconocimiento.</b> Se mira el objetivo desde fuera: qué hay y qué está expuesto.</sub></td>
<td><sub><b>02 · Entrada.</b> Se ha encontrado una puerta. La parte en azul marca dónde mirar.</sub></td>
</tr>
<tr>
<td><img src="docs/capturas/04-etapa-pasillos.png" alt="Etapa 3, pasillos: un pasillo interior con muchas puertas"></td>
<td><img src="docs/capturas/05-etapa-cuarto.png" alt="Etapa 4, cuarto: una habitación con un cofre pequeño sobre una mesa"></td>
</tr>
<tr>
<td><sub><b>03 · Pasillos.</b> Ya dentro, con muchas puertas por probar.</sub></td>
<td><sub><b>04 · Cuarto.</b> Una puerta cedió y dentro hay algo de valor. Después se vuelve al pasillo.</sub></td>
</tr>
<tr>
<td><img src="docs/capturas/06-etapa-camara.png" alt="Etapa 5, cámara: una sala grande con un arcón sobre una tarima entre dos faroles"></td>
<td></td>
</tr>
<tr>
<td><sub><b>05 · Cámara.</b> El final del recorrido.</sub></td>
<td></td>
</tr>
</table>

<sub>Todas las imágenes son arte propio del proyecto, montado sobre el diseño aprobado.
No son capturas del programa.</sub>

## Principios

- **Nunca da la bandera.** La orientación ayuda a pensar el siguiente paso; no resuelve el reto.
- **Solo entornos autorizados.** Cada expedición empieza confirmando que se practica sobre un entorno permitido: un CTF, un laboratorio propio o una máquina de práctica.
- **El cofre funciona sin IA.** Las herramientas y las preguntas de cada etapa no dependen de un proveedor externo.
- **Las notas son tuyas.** Se exportan, se descargan con el resto de tus datos y se borran con la cuenta.
- **Sin cifra inventada.** Cada herramienta lleva su documentación oficial y la fecha en que se comprobó.
- **No promete resultados.** No promete aprobar un examen ni conseguir un empleo.
- **No sustituye a las plataformas.** Acompaña al aprendiz mientras practica en ellas; no aloja máquinas ni retos.

## Stack

Java 25 · Spring Boot 4 · Thymeleaf + HTMX · PostgreSQL · Flyway. El núcleo con las
reglas del producto es Java puro, separado de la web y de la base de datos.

## Estado

En desarrollo. Están cerrados el estudio previo, la marca, el diseño del tablero y la
arquitectura; la construcción empieza por los cimientos (compilación, pruebas, datos y
seguridad). La primera versión será una aplicación web en español, para escritorio.

Este repositorio se actualiza en hitos: cuando exista el programa, estas imágenes se
cambiarán por capturas reales.

## Licencia

Software propietario. Este repositorio publica **solo** una presentación (texto e
imágenes); no contiene código fuente y su visibilidad no concede ningún derecho de uso.
Ver [LICENSE](LICENSE).

Kishidō es un proyecto independiente. No está afiliado ni avalado por ninguna plataforma
de práctica ni por ningún organismo de certificación; los nombres de terceros pertenecen
a sus propietarios.

© 2026 Rubén Agudelo Alzate.
