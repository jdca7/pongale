# Póngale — Mejoras pendientes

## Features de retención y engagement

### Alta prioridad

| Feature | Descripción | Complejidad | Notas |
|---|---|---|---|
| **Aviso de racha en peligro** | Banner al abrir la app si el usuario tiene racha activa y aún no ha practicado hoy. "🔥 Tu racha de X días termina hoy" | Baja | Solo verificar fechas al cargar el mapa. Sin push notifications |
| **Escudo de racha (1x/semana)** | Si el usuario falla un día, un escudo se consume automáticamente y la racha se mantiene. Se recarga al completar 5 lecciones en la semana | Baja | 2 variables en localStorage: `shieldAvailable`, `lessonsThisWeek` |
| **Repaso al inicio de sesión** | Al abrir la app, mostrar 1 pregunta aleatoria de un módulo ya completado antes de continuar | Media | Selección aleatoria del banco de preguntas de módulos completados |

### Media prioridad

| Feature | Descripción | Complejidad | Notas |
|---|---|---|---|
| **Spaced repetition básico** | Marcar preguntas como "para repasar" si se respondieron mal. Reaparecer al día siguiente | Media | Guardar en localStorage: `{lessonId, nextReview, failCount}` |
| **Sugerencia de pausa** | Después de 4+ lecciones en el día, mostrar mensaje "Tu cerebro necesita dormir para consolidar — volvé mañana" sin bloquear | Baja | Solo un contador de lecciones del día, sin bloqueo |
| **Desafío semanal** | Cada lunes aparece un reto especial: "Completa 3 módulos esta semana para ganar +200 XP bonus" | Media | Requiere trackear lecciones por semana |
| **Compartir logro** | Al completar un módulo, botón "Compartir" que genera una imagen con el nombre, módulo y XP ganado | Baja | Canvas API o CSS-to-image. Sin servidor |

### Multiidioma

| Feature | Descripción | Complejidad | Notas |
|---|---|---|---|
| **Selección de idioma** | El usuario elige el idioma de la interfaz al inicio (o en configuración): Español, English, Português | Media | Actualmente todo el texto está hardcodeado en español dentro del JS |
| **Español** | Idioma actual | — | ✅ Completo |
| **English** | Traducción completa: UI, explicaciones, analogías, preguntas, feedback, opciones | Alta | Todo el contenido de los 5 módulos debe traducirse |
| **Português** | Igual que English | Alta | Mercado brasileño es enorme para este tipo de app |

> **Nota de implementación:** El enfoque más limpio sería separar el array `MODULES` en un objeto `CONTENT[lang]` con las lecciones de cada idioma. La UI (botones, mensajes del sistema) se maneja con un objeto `T[lang]` de strings traducidos. El idioma seleccionado se guarda en `localStorage`.

---

### Baja prioridad

| Feature | Descripción | Complejidad | Notas |
|---|---|---|---|
| **Panel de padre** | Vista separada donde el padre/madre ve el progreso del hijo con un código de 6 dígitos | Alta | Requiere Firebase activo o localStorage compartido (mismo dispositivo) |
| **Sonidos opcionales** | Sonido de éxito al responder bien, sonido de nivel al completar módulo | Baja | Web Audio API, opcional en configuración |
| **Modo oscuro/claro** | Toggle entre tema oscuro (actual) y claro | Baja | Ya tiene variables CSS, fácil de extender |
| **Animación de nivel** | Animación elaborada cuando el XP sube de nivel (actualmente solo hay barra) | Baja | CSS keyframes |

---

## Módulos de contenido pendientes

El camino de Python completo debería cubrir:

| # | Módulo | Temas | Estado |
|---|---|---|---|
| 1 | Variables y tipos | int, float, str, bool, print, type() | ✅ Completo |
| 2 | Condicionales | if, elif, else, operadores de comparación | ✅ Completo |
| 3 | Bucles for | range(), listas, acumuladores | ✅ Completo |
| 4 | Funciones | def, parámetros, return | ✅ Completo |
| 5 | Proyecto: número secreto | Integración de módulos 1-4 | ✅ Completo |
| 6 | Listas | append(), índices, len(), recorrer, modificar | ⬜ Pendiente |
| 7 | Strings | len(), upper/lower, slicing, in, format/f-strings | ⬜ Pendiente |
| 8 | Diccionarios | keys, values, acceso, recorrer con for | ⬜ Pendiente |
| 9 | Bucles while | while, break, continue, bucles infinitos con condición | ⬜ Pendiente |
| 10 | Proyecto 2 | App de lista de tareas o calculadora interactiva | ⬜ Pendiente |
| 11 | Manejo de errores | try/except, tipos de error comunes | ⬜ Pendiente |
| 12 | Proyecto final | Juego completo (texto aventura o similar) | ⬜ Pendiente |

> Orden sugerido: 6 → 7 → 8 → 9 → 10 → 11 → 12
> Módulos 6-9 son fundamentos; 10-12 son proyectos integradores.

---

## Técnicas pedagógicas pendientes de aplicar

| Técnica | Descripción | Impacto en retención | Estado |
|---|---|---|---|
| **Active recall** | Preguntas antes de ver el contenido | Muy alto | ✅ Aplicado (fase Aprende → Practica) |
| **Feedback inmediato** | Explicación de por qué es correcto/incorrecto | Muy alto | ✅ Aplicado (ok/fail con explicación) |
| **Sesiones cortas** | ≤5 min por lección | Alto | ✅ Aplicado |
| **Spaced repetition** | Repasar con intervalos crecientes (hoy → mañana → 3 días → 1 semana) | Muy alto | ⬜ Pendiente |
| **Interleaving** | Mezclar preguntas de temas distintos ya vistos | Alto | ⬜ Pendiente |
| **Generative learning** | El estudiante escribe código desde cero, no solo elige opciones | Alto | ⬜ Parcial (lecciones `run`) |
| **Elaborative interrogation** | Preguntar "¿por qué funciona así?" no solo "¿cuál es el resultado?" | Medio | ⬜ Pendiente (agregar preguntas de razonamiento) |
| **Pausa sugerida** | Indicar cuándo parar para que el sueño consolide | Medio | ⬜ Pendiente |

---

## Mejoras técnicas / UX

| Mejora | Descripción | Prioridad |
|---|---|---|
| **PWA install prompt** | Botón "Instalar app" para que quede en el home screen del celular | Alta |
| **Offline completo** | Service worker para funcionar sin internet | Media |
| **Altura del editor** | El textarea del editor de código es fijo (5 filas); en móvil con código largo hay que hacer scroll | Media |
| **Teclado virtual en móvil** | En el editor de código, el teclado del celular no tiene `_`, `(`, `:` fácilmente — considerar barra de caracteres especiales | Alta |
| **Highlight de línea activa** | En el editor, resaltar la línea donde está el cursor | Baja |
| **Mensajes de error mejores** | `pySimulate` devuelve "Error: ..." genérico — mejorar mensajes (ej: "Falta el `:` al final del if") | Media |
| **Persistencia cross-device** | Actualmente el progreso está solo en localStorage — si el usuario cambia de celular, pierde todo. Firebase resolvería esto | Alta (futuro) |

---

## Benchmark competencia

### Brilliant — Python

| Aspecto | Detalle |
|---|---|
| Curso principal | "Programming with Python" — ~20-30 lecciones en 5-6 capítulos |
| Continuación | Cursos separados de Computer Science, algoritmos y matemáticas |
| Modelo de negocio | Freemium: 2 lecciones/día gratis, ilimitado con suscripción (~$15 USD/mes) |
| Fortaleza | Calidad interactiva muy alta, visualizaciones, problemas bien diseñados |
| Debilidad clave | El límite diario del plan gratis es el principal killer de retención en adolescentes |
| Profundidad de Python | Fundamentos sólidos pero no llega a proyectos reales ni a nivel intermedio |

### Duolingo (referencia de retención)

| Aspecto | Detalle |
|---|---|
| Mecanismo estrella | Spaced repetition + streaks + notificaciones agresivas |
| Lección promedio | 3-5 minutos |
| Retención | Récord en la industria para apps de aprendizaje — el modelo a seguir en engagement |
| Debilidad | Aprendizaje superficial; funciona para idiomas, no necesariamente para programación |

### Conclusión para Póngale

Póngale ya tiene la ventaja más importante: **sin límite de lecciones**. La brecha más grande con Brilliant es el **spaced repetition** y las **notificaciones de racha**. La brecha con Duolingo es el **engagement diario** (notificaciones, shield, desafíos semanales).

---

## Contexto del proyecto

- **App:** Póngale — aprendizaje de Python sin límites, gratis
- **Motivación:** Hijo de 13 años abandonó Brilliant por el límite de 2 lecciones/día del plan gratuito
- **Stack:** HTML + CSS + JS (sin framework), `pySimulate` como intérprete Python en el browser
- **Repo:** https://github.com/jdca7/pongale
- **Deploy:** GitHub Pages — https://jdca7.github.io/pongale/
- **Target:** Niños y adolescentes 10-16 años, mercado hispanohablante
