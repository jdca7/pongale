# Póngale — Mejoras pendientes

## Features de retención y engagement

### Alta prioridad

| Feature | Descripción | Complejidad | Estado |
|---|---|---|---|
| **Aviso de racha en peligro** | Banner naranja en el mapa si racha > 1 y no practicó hoy | Baja | ✅ Hecho (2026-04-26) |
| **Escudo de racha (1x/semana)** | Auto-consume si falla un día; se recarga con 5 lecciones/semana. Pill muestra 🛡️ | Baja | ✅ Hecho (2026-04-26) |
| **Repaso al inicio de sesión** | Overlay con pregunta aleatoria de módulo completado, +5 XP al acertar, 1x/día | Media | ✅ Hecho (2026-04-26) |
| **Teclado virtual en móvil** | Barra de caracteres especiales (`_`, `(`, `:`, etc.) sobre el teclado en el editor | Alta | ✅ Hecho (2026-04-26) |

### Media prioridad

| Feature | Descripción | Complejidad | Estado |
|---|---|---|---|
| **Spaced repetition básico** | Marcar preguntas falladas para que reaparezcan al día siguiente | Media | ⬜ Pendiente |
| **Sugerencia de pausa** | Después de 4+ lecciones en el día, mensaje "Tu cerebro necesita dormir" sin bloquear | Baja | ⬜ Pendiente |
| **Desafío semanal** | Cada lunes: "Completa 3 módulos esta semana para ganar +200 XP bonus" | Media | ⬜ Pendiente |
| **Compartir logro** | Al completar módulo, botón que genera imagen con nombre, módulo y XP. Canvas API | Baja | ⬜ Pendiente |

### Multiidioma

| Feature | Descripción | Complejidad | Estado |
|---|---|---|---|
| **Selección de idioma** | El usuario elige idioma al inicio: Español, English, Português | Media | ⬜ Pendiente |
| **Español** | Idioma actual | — | ✅ Completo |
| **English** | Traducción completa: UI, explicaciones, analogías, preguntas, feedback | Alta | ⬜ Pendiente |
| **Português** | Igual que English | Alta | ⬜ Pendiente |

> **Nota de implementación:** Separar `MODULES` en `CONTENT[lang]`. UI con objeto `T[lang]` de strings traducidos. Idioma en `localStorage`.

---

### Baja prioridad

| Feature | Descripción | Complejidad | Estado |
|---|---|---|---|
| **Panel de padre** | Vista de progreso del hijo con código de 6 dígitos | Alta | ⬜ Pendiente |
| **Sonidos opcionales** | Sonido de éxito y de nivel. Web Audio API, opcional en config | Baja | ⬜ Pendiente |
| **Modo oscuro/claro** | Toggle entre tema oscuro (actual) y claro. Ya tiene variables CSS | Baja | ⬜ Pendiente |
| **Animación de nivel** | Animación elaborada al subir de nivel. CSS keyframes | Baja | ⬜ Pendiente |

---

## Módulos de contenido

| # | Módulo | Temas | Estado |
|---|---|---|---|
| 1 | Variables y tipos | int, float, str, bool, print, type() | ✅ Completo |
| 2 | Condicionales | if, elif, else, operadores de comparación | ✅ Completo |
| 3 | Bucles for | range(), listas, acumuladores | ✅ Completo |
| 4 | Funciones | def, parámetros, return | ✅ Completo |
| 5 | Proyecto: número secreto | Integración de módulos 1-4 | ✅ Completo |
| 6 | Listas | append(), índices, len(), recorrer, modificar | ✅ Completo |
| 7 | Strings | len(), upper/lower, slicing, in, f-strings | ✅ Completo |
| 8 | Diccionarios | keys, values, acceso, recorrer con for | ✅ Completo |
| 9 | Bucles while | while, break, continue, bucles infinitos con condición | ✅ Completo |
| 10 | Proyecto 2 | Boletín de notas — integra listas, dicts, def, for, promedio | ✅ Completo (2026-04-26) |
| 11 | Manejo de errores | try/except, ValueError, TypeError | ✅ Completo (2026-04-26) |
| 12 | Proyecto final: Aventura en código | mini-RPG de consola — integra todo el nivel básico | ✅ Completo (2026-04-27) |

---

### Nivel Medio — módulos 13–24

Prerrequisitos: haber completado el nivel básico (módulos 1–12).
Foco: Python más expresivo, programación orientada a objetos básica, patrones comunes.
**Nota técnica:** los módulos 18–20 (clases/herencia) y 21 (math/random) requieren extender pySimulate.

| # | Módulo | Temas clave | Estado |
|---|---|---|---|
| 13 | Comprensión de listas | `[expr for x in lista]`, `[expr for x in lista if cond]`, comparar con for clásico | ⬜ Pendiente |
| 14 | Funciones avanzadas | valores por defecto, argumentos keyword, múltiples `return`, funciones como parámetros | ⬜ Pendiente |
| 15 | Lambda y map/filter | `lambda x: expr`, `map()`, `filter()`, cuándo usarlos vs comprensión | ⬜ Pendiente |
| 16 | Recursión | base case, call stack, factorial, fibonacci, pensar recursivamente | ⬜ Pendiente |
| 17 | Proyecto 3: Filtros y transformaciones | pipeline de datos con comprensiones, lambda y recursión — sin clases | ⬜ Pendiente |
| 18 | Clases I — atributos y métodos | `class`, `__init__`, `self`, crear instancias, métodos de instancia | ⬜ Pendiente |
| 19 | Clases II — métodos especiales | `__str__`, `__repr__`, `__len__`, `__eq__`, hacer objetos "pythónicos" | ⬜ Pendiente |
| 20 | Herencia | `class B(A):`, `super()`, sobrescribir métodos, polimorfismo básico | ⬜ Pendiente |
| 21 | Módulos: math y random | `math.sqrt`, `math.floor`, `math.pi`; `random.randint`, `random.choice`, `random.shuffle` | ⬜ Pendiente |
| 22 | Tuplas y conjuntos | tuplas inmutables `(a, b)`, unpacking; sets `{a, b}`, unión, intersección, diferencia | ⬜ Pendiente |
| 23 | Excepciones avanzadas | múltiples `except`, `finally`, `else` en try, crear excepciones propias con `class` | ⬜ Pendiente |
| 24 | Proyecto 4: RPG con clases | refactor del RPG básico (módulo 12) usando `class Heroe`, `class Enemigo`, herencia `class Jefe(Enemigo)` | ⬜ Pendiente |

---

### Nivel Avanzado — módulos 25–36

Prerrequisitos: nivel medio completo.
Foco: algoritmos, estructuras de datos, Python profesional.
**Nota técnica:** módulos 33–35 (archivos, APIs, regex) requieren integración con Pyodide u otro intérprete real.

| # | Módulo | Temas clave | Estado |
|---|---|---|---|
| 25 | Complejidad algorítmica | Big O notation, O(1) O(n) O(n²) O(log n), medir con tiempo real, por qué importa | ⬜ Pendiente |
| 26 | Búsqueda | búsqueda lineal vs binaria, implementar ambas, cuándo usar cada una | ⬜ Pendiente |
| 27 | Ordenamiento I | bubble sort, selection sort, implementar desde cero, contar operaciones | ⬜ Pendiente |
| 28 | Ordenamiento II | merge sort (divide y vencerás), comparar eficiencia vs los anteriores | ⬜ Pendiente |
| 29 | Estructuras de datos | pila (LIFO) y cola (FIFO) implementadas con listas, casos de uso reales | ⬜ Pendiente |
| 30 | Proyecto 5: Analizador de datos | leer lista de datos, ordenar, buscar, calcular estadísticas — sin librerías externas | ⬜ Pendiente |
| 31 | Generadores | `yield`, diferencia con `return`, iteradores lazy, ahorrar memoria con datos grandes | ⬜ Pendiente |
| 32 | Decoradores | `@decorator`, función que envuelve función, `@staticmethod`, `@classmethod`, `@property` | ⬜ Pendiente |
| 33 | Archivos y JSON | `open()`, `read()`, `write()`, `with`, `json.loads()`, `json.dumps()`, serializar datos | ⬜ Pendiente |
| 34 | APIs y requests | HTTP GET/POST, `requests.get()`, parsear JSON de una API pública, manejar errores de red | ⬜ Pendiente |
| 35 | Expresiones regulares | `re.match()`, `re.search()`, `re.findall()`, grupos, patrones básicos, validar email/teléfono | ⬜ Pendiente |
| 36 | Proyecto final avanzado | aplicación completa: scraper simple, analizador de texto o cliente de API — OOP + algos + archivos | ⬜ Pendiente |

---

## Técnicas pedagógicas

| Técnica | Descripción | Impacto | Estado |
|---|---|---|---|
| **Active recall** | Preguntas antes de ver el contenido | Muy alto | ✅ Aplicado |
| **Feedback inmediato** | Explicación de por qué es correcto/incorrecto | Muy alto | ✅ Aplicado |
| **Sesiones cortas** | ≤5 min por lección | Alto | ✅ Aplicado |
| **Repaso diario** | Pregunta aleatoria de módulo completado al abrir la app | Alto | ✅ Aplicado (2026-04-26) |
| **Spaced repetition** | Intervalos crecientes: hoy → mañana → 3 días → 1 semana | Muy alto | ⬜ Pendiente |
| **Interleaving** | Mezclar preguntas de temas distintos ya vistos | Alto | ⬜ Pendiente |
| **Generative learning** | El estudiante escribe código desde cero | Alto | ⬜ Parcial (lecciones `run`) |
| **Elaborative interrogation** | Preguntar "¿por qué funciona así?" no solo "¿cuál es el resultado?" | Medio | ⬜ Pendiente |
| **Pausa sugerida** | Indicar cuándo parar para que el sueño consolide | Medio | ⬜ Pendiente |

---

## Mejoras técnicas / UX

| Mejora | Descripción | Prioridad | Estado |
|---|---|---|---|
| **Favicon** | Cohete SVG inline (data URL), sin archivo extra | Alta | ✅ Hecho (2026-04-26) |
| **Icono de marca** | SVG cohete con colores de la marca; reemplaza emoji serpiente | Alta | ✅ Hecho (2026-04-26) |
| **PWA install prompt** | Botón "Instalar app" para home screen del celular | Alta | ⬜ Pendiente |
| **Offline completo** | Service worker para funcionar sin internet | Media | ⬜ Pendiente |
| **Teclado virtual en móvil** | Barra de caracteres especiales sobre el teclado del editor | Alta | ✅ Hecho (2026-04-26) |
| **Altura del editor** | El textarea es fijo (5 filas); en móvil con código largo hay scroll | Media | ⬜ Pendiente |
| **Highlight de línea activa** | Resaltar la línea donde está el cursor en el editor | Baja | ⬜ Pendiente |
| **Mensajes de error mejores** | `pySimulate` devuelve mensajes genéricos — mejorar (ej: "Falta `:` al final del if") | Media | ⬜ Pendiente |
| **Persistencia cross-device** | Progreso solo en localStorage — Firebase lo resolvería | Alta (futuro) | ⬜ Pendiente |

---

## Migración a móvil nativo

| Opción | Descripción | Costo | Complejidad | Estado |
|---|---|---|---|---|
| **PWA** | manifest.json + service worker → instalar desde Chrome sin Play Store | Gratis | Baja | ✅ Implementado (manifest.json + sw.js) |
| **Capacitor** | Empaqueta el HTML existente como APK para Play Store sin reescribir código | $25 cuenta Google | Media | ⬜ Pendiente |
| **Flutter + Firebase** | Reescritura completa; solo si se necesita auth real y cross-device | Gratis (free tier) | Muy alta | ⬜ Futuro lejano |

> Nota: Para que Chrome muestre el botón "Instalar", faltan los íconos PNG `icon-192.png` y `icon-512.png` en el repo.

---

## Benchmark competencia

### Brilliant — Python
| Aspecto | Detalle |
|---|---|
| Modelo de negocio | Freemium: 2 lecciones/día gratis, ilimitado con suscripción (~$15/mes) |
| Fortaleza | Calidad interactiva muy alta, visualizaciones, problemas bien diseñados |
| Debilidad clave | El límite diario mata la retención en adolescentes |

### Duolingo (referencia de retención)
| Aspecto | Detalle |
|---|---|
| Mecanismo estrella | Spaced repetition + streaks + notificaciones agresivas |
| Retención | Récord en la industria — el modelo a seguir en engagement |

**Ventaja de Póngale:** sin límite de lecciones. Brecha con Brilliant: spaced repetition completo. Brecha con Duolingo: notificaciones push y desafíos semanales.

---

## Contexto del proyecto

- **App:** Póngale — aprendizaje de Python sin límites, gratis
- **Motivación:** Hijo de 13 años abandonó Brilliant por el límite de 2 lecciones/día
- **Stack:** HTML + CSS + JS (sin framework), `pySimulate` interpreta Python en el browser
- **Repo:** https://github.com/jdca7/pongale
- **Deploy:** GitHub Pages — https://jdca7.github.io/pongale/
- **Target:** Niños y adolescentes 10-16 años, mercado hispanohablante
