# TaskTec — Plan del proyecto

> Entrada al **Codédex Monthly Challenge — September 2026: Back 2 School**
> Entrega límite: **30 de septiembre de 2026, 23:59**

---

## 1. El brief, en corto

Codédex pide:

- Construir en **Codédex Builds** usando **HTML, CSS y JavaScript**
- Algo para **tu escuela, campus, compañeros o docentes**
- Cita textual: *"Don't build something for every school. Build something for your school."*
- Idea sugerida por el propio brief: *"⏰ Deadline reminder for those 11:59 pm submissions"*

Premios relevantes: **🏟️ School Spirit** (lo más hecho para tu campus) y **🦄 TheFacebook** (el Build que *NEEDS to exist*).

---

## 2. El recorte

**Institución:** Tecsup — Instituto de Educación Superior Privado TECSUP N° 1
**Carrera:** Diseño y Desarrollo de Software
**Ciclo:** 6 (el último)
**Sede:** por definir (Lima / Arequipa / Trujillo)

El diferencial **no** es la idea — el recordatorio de entregas es la idea más obvia del challenge y la van a elegir cientos de personas. El diferencial es la **especificidad institucional**: que la app hable el idioma de Tecsup y conozca su estructura real. Eso es lo que gana School Spirit.

---

## 3. Datos verificados (no inventados)

Todo lo que sigue salió de fuentes oficiales de Tecsup o de organismos públicos. Lo que no se pudo verificar está marcado explícitamente en la sección 8.

### Estructura del período académico

**Fuente:** Reglamento Institucional de Tecsup (Art. 37)

> "TECSUP programará dos (2) Periodos Académicos Ordinarios al año. Cada Período Académico Ordinario consta de dieciocho (18) semanas, las cuales incluyen dieciséis (16) semanas de clases y dos (02) semanas de evaluaciones finales."

→ **18 semanas = 16 de clases + 2 de evaluaciones finales.** Esto es autoritativo.

### Calendario del período 2026-II

**Fuente:** Resolución Jefatural N° 1590-2026-MINEDU/VMGI-PRONABEC-OAF

Cronograma de pagos para TECSUP 2026-II: matrícula en **agosto 2026**, pensiones hasta **diciembre 2026**.

→ El ciclo 6 corre **agosto → diciembre de 2026**.

### Canvas — el LMS

**Fuente:** `tecsup.edu.pe/canvas/guia-alumno.pdf` (Guía de Canvas para alumnos de Tecsup)

Comportamiento real de las evaluaciones en Canvas:

- **3 intentos permitidos** por evaluación
- **"la nota final será la más alta"** — cuenta el mejor intento, no el último
- Tiempo límite típico: **15 minutos**
- Cada evaluación tiene "Fecha límite" y ventana "Disponible"

→ Esto es oro: información que solo conoce alguien de adentro.

### Vocabulario institucional

**Fuente:** Reglamento Institucional (Art. 36-42) y malla curricular

- Tecsup dice **"ciclo"**, no "semestre"
- Tecsup dice **"unidades didácticas"**, no "cursos" ni "asignaturas"
- Las unidades se agrupan en **"Competencias para la Empleabilidad"** y **"Competencias Específicas"**
- Las evaluaciones se llaman **"evaluaciones de teoría"**, **"evaluación final"**, **"evaluación extraordinaria"**

→ Usar el vocabulario de la institución es el gesto más barato y de mayor señal de todo el proyecto.

### Malla curricular — ciclo 6 (8 unidades didácticas)

**Fuente:** `tecsup.edu.pe/carrera/diseno-y-desarrollo-de-software-2/`

| Bloque | Unidad didáctica |
| --- | --- |
| Competencias para la Empleabilidad | Consultoría y Desarrollo Profesional |
| Competencias para la Empleabilidad | Emprendimiento |
| Competencias para la Empleabilidad | Sociedad y Desarrollo Sostenible |
| Competencias Específicas | Gestión de Servicios de Software |
| Competencias Específicas | Integración de Sistemas Empresariales Avanzado |
| Competencias Específicas | Desarrollo de Aplicaciones Empresariales Avanzado |
| Competencias Específicas | Startup Venture Project |
| Competencias Específicas | Inteligencia de Negocios |

### La carrera

3 años · **131 créditos** · **2960 horas** · 6 ciclos · modalidad semipresencial
Título: *Profesional Técnico en Diseño y Desarrollo de Software*
Certificaciones modulares anuales:

- Año 1 — Tecnologías aplicadas al desarrollo de software
- Año 2 — Programación de aplicaciones web y móviles
- Año 3 — Diseño de integración de aplicaciones empresariales

### El dolor real

Hoy el estudiante de Tecsup vive en **tres sistemas separados**:

| Sistema | Qué resuelve |
| --- | --- |
| `sis.tecsup.edu.pe/Alumnos` | Matrícula, información académica, financiera |
| Canvas | Cursos, evaluaciones, fechas, notas |
| `app.tecsup.edu.pe/matricula` + `academico-cloud.tecsup.edu.pe/pcc` | Procesos académicos |

**No existe una vista unificada de vencimientos.** Ese es el problema que TaskTec resuelve.

---

## 4. Qué es TaskTec

> **TaskTec — tu ciclo en una pantalla.**
> Las 18 semanas del ciclo de Tecsup, tus 8 unidades didácticas, tus entregas y tus intentos de Canvas. Todo junto, por primera vez.

### Los hooks que nadie de afuera puede copiar

1. **Semana N de 18** — el ciclo tiene forma y la app te dice dónde estás parado
2. **Los intentos de Canvas** — *"te quedan 2 intentos, tenés 14, cuenta la más alta"*. Solo existe si conocés Tecsup
3. **El vocabulario** — "ciclo", "unidades didácticas", "competencias específicas"
4. **La malla real** — las 8 unidades del ciclo 6, con nombre y apellido

---

## 5. Alcance

**Construir todo el proyecto en un solo HTML/CSS/JS autocontenido.**

Un archivo, cero dependencias externas, cero build step. Eso es exactamente lo que Codédex Builds consume y lo que permite pegar y correr.

### Dentro del alcance

- Dashboard "Mi Ciclo" con semana N de 18, barra de progreso y countdown
- Línea de tiempo de 18 semanas con hitos marcados
- Gestión de entregas (crear, editar, completar, borrar) con fecha y hora
- Las 8 unidades didácticas reales, agrupadas por bloque de competencias
- Tracker de intentos de Canvas (3 intentos, cuenta la más alta)
- Configuración: fecha de inicio del ciclo, sede, carrera
- Persistencia en `localStorage`
- Tema claro / oscuro
- Responsive (mobile-first — se usa en el celular entre clases)

### Fuera del alcance (explícito)

- Sin backend, sin login, sin sincronización
- Sin integración real con Canvas ni con el SIS (no hay API pública)
- Sin notificaciones push
- Sin cuentas de usuario

---

## 6. Modelo de datos

```js
const ACADEMIC_CYCLE = {
  number: 6,
  program: "Diseño y Desarrollo de Software",
  campus: null,          // "Lima" | "Arequipa" | "Trujillo"
  startDate: null,       // ISO date — CONFIGURABLE, nunca hardcodeado
  totalWeeks: 18,
  classWeeks: 16,
  finalWeeks: [17, 18],
  theoryAssessmentWeeks: [4, 8, 12, 16],  // ver sección 8 — configurable
  courseUnits: [
    { id: "u1", name: "Consultoría y Desarrollo Profesional",             track: "employability" },
    { id: "u2", name: "Emprendimiento",                                   track: "employability" },
    { id: "u3", name: "Sociedad y Desarrollo Sostenible",                 track: "employability" },
    { id: "u4", name: "Gestión de Servicios de Software",                 track: "specific" },
    { id: "u5", name: "Integración de Sistemas Empresariales Avanzado",   track: "specific" },
    { id: "u6", name: "Desarrollo de Aplicaciones Empresariales Avanzado",track: "specific" },
    { id: "u7", name: "Startup Venture Project",                          track: "specific" },
    { id: "u8", name: "Inteligencia de Negocios",                         track: "specific" }
  ]
};

// Una entrega
{
  id: "…",
  unitId: "u4",
  title: "…",
  dueAt: "2026-09-25T23:59",   // la hora importa: el 23:59 es el enemigo
  status: "pending" | "submitted",
  weight: null                  // % de la nota, opcional
}

// Tracker de Canvas por unidad
{
  unitId: "u4",
  attemptsUsed: 0,              // 0..3
  bestScore: null,              // la más alta cuenta
  maxAttempts: 3
}
```

---

## 7. Pantallas

Navegación por tabs, mobile-first.

### Mi Ciclo (dashboard)

- Encabezado: `Ciclo 6 · Diseño y Desarrollo de Software` + sede
- **Semana N de 18** en grande, con barra de progreso del ciclo
- Fase actual: `Clases (sem 1-16)` / `Evaluaciones finales (sem 17-18)`
- **Countdown al próximo hito** — días y horas
- Próximas 3 entregas ordenadas por vencimiento
- Alerta si hay entregas que vencen en menos de 48 h

### Línea de tiempo (dentro de Mi Ciclo)

Las 18 semanas en una tira horizontal, con:

- Semana actual destacada
- Hitos de evaluación de teoría marcados (semanas 4 / 8 / 12 / 16)
- Semanas 17-18 marcadas como evaluaciones finales
- Las semanas ya cursadas atenuadas

### Entregas

- Lista de entregas ordenadas por fecha
- Agrupables por unidad didáctica
- Estado: pendiente / entregado
- Cada una muestra countdown (`vence en 2 días`, `vence hoy`, `vencida`)
- Crear / editar / borrar
- Filtro: todas / pendientes / entregadas

### Unidades

- Las 8 unidades didácticas, agrupadas en:
  - **Competencias para la Empleabilidad** (3)
  - **Competencias Específicas** (5)
- Cada unidad muestra: entregas pendientes y estado de intentos de Canvas

### Detalle de unidad (modal)

- Nombre y bloque de la unidad
- **Tracker de Canvas**: 3 intentos, cuáles se usaron, mejor nota, *"te quedan N intentos"*
- Entregas de esa unidad
- Recordatorio de la regla: *"cuenta la nota más alta"*

### Configuración

- **Fecha de inicio del ciclo** ← el campo crítico
- Sede
- Tema claro / oscuro
- Reset de datos

---

## 8. Honestidad de datos — lo que NO está confirmado

Esto es deliberado y es parte del diseño, no una nota al pie.

### El ritmo de evaluaciones cada 4 semanas

Se observó en un webinar oficial de Tecsup sobre **Cursos de Cálculo y Estadística** (ciclo 1-2):

> "cada cuatro semanas, nosotros evaluamos con una evaluación que le llamamos de teoría"

**No está confirmado que aplique al ciclo 6.** El ciclo 6 tiene *Startup Venture Project*, *Inteligencia de Negocios* y *Emprendimiento*, que tienen perfil proyectual, no de examen teórico cada 4 semanas.

**Decisión:** `theoryAssessmentWeeks` es **configurable desde la UI**, con `[4, 8, 12, 16]` como valor por defecto. La app no afirma que sea verdad — la ofrece como configuración.

**Pendiente del usuario:** revisar los sílabos del ciclo 6 y ajustar.

### La fecha de inicio del ciclo

No es pública. El Reglamento solo fija la estructura; el calendario con fechas "se publica oportunamente".

**Decisión:** `startDate` es un **campo de configuración obligatorio**. Mientras no se complete, el dashboard muestra un estado vacío claro pidiendo la fecha, en vez de inventar una semana.

Esto es mejor ingeniería: la app sirve para cualquier ciclo, carrera y sede, y corregir la fecha es un renglón.

### Los pesos de evaluación

Los pesos 20/30/50 (fases de Aula Invertida) y 40/60 (teoría vs actividades) también vienen del webinar de Cálculo y Estadística. **No se usan como dato duro** — el campo `weight` es opcional y lo carga el usuario.

---

## 9. Sistema visual

- **Mobile-first**, una columna, tabs abajo
- **Paleta** vía variables CSS: neutros slate + acento fuerte. Ajustable en un bloque
- **Tema claro / oscuro** con persistencia
- Tipografía del sistema (sin webfonts — cero dependencias)
- Componentes: cards, progress bar, chips de estado, modal full-screen, bottom tabs
- Microinteracción: countdown que se actualiza en vivo

Se reutiliza la **arquitectura visual** del prototipo `DayTesk/htmls/index.html` (patrón `.screen` / `.full-modal` / `switchTab()`), que ya está probada y es autocontenida. No se reutiliza su contenido ni su identidad: eso era una app GTD genérica.

---

## 10. Convenciones de código

- **UI copy: español**, con el vocabulario de Tecsup ("ciclo", "unidades didácticas", "competencias")
- **Identificadores, funciones, variables y comentarios: inglés**
- **Cero dependencias externas** — ni CSS, ni JS, ni fuentes
- Un solo archivo `index.html`
- Sin build step

---

## 11. Cronograma

Hoy: **18 de septiembre de 2026** · Entrega: **30 de septiembre de 2026**

| Días | Qué |
| --- | --- |
| 1 | Estructura, sistema visual, navegación, modelo de datos |
| 2-3 | Mi Ciclo: semana N de 18, barra, línea de tiempo, countdown |
| 4-5 | Entregas: CRUD completo, countdowns, estados |
| 6 | Unidades + tracker de Canvas |
| 7 | Configuración + persistencia + tema oscuro |
| 8 | Pulido visual, responsive, estados vacíos |
| 9 | **Revisar sílabos y corregir `theoryAssessmentWeeks`** |
| 10 | Deploy (GitHub Pages o Vercel) + capturas / GIF |
| 11 | Escribir el post de submission |
| 12 | Buffer + Show & Tell |

---

## 12. Entrega

Formato que pide el challenge:

- **Title:** el nombre del proyecto
- **Images:** capturas o GIF mostrando la app
- **Body:** qué construiste, para quién, qué problema resuelve

### Borrador del body

> **TaskTec — your Tecsup cycle on one screen**
>
> Every Tecsup student juggles three separate systems: the SIS portal for enrollment, Canvas for courses and assessments, and the academic system for everything else. None of them gives you a single view of what's actually due.
>
> TaskTec is built for one institution only — Tecsup, Peru — and for one cycle: the 6th cycle of Diseño y Desarrollo de Software. It knows that a Tecsup cycle is 18 weeks (16 of classes plus 2 of final assessments). It knows the real course units, grouped the way Tecsup groups them: Competencias para la Empleabilidad and Competencias Específicas. It even knows Canvas's grading rule — three attempts, and the highest score counts.
>
> It solves a small, real problem: not missing a deadline. Built with HTML, CSS and JavaScript, no dependencies.

### Bonus

⭐️ Asistir a un club tecnológico, feria de empleo o hackathon. Post aparte con foto.
(MLH para universitarios, Hack Club, Devpost)

---

## 13. Riesgos

| Riesgo | Mitigación |
| --- | --- |
| El ritmo "cada 4 semanas" no aplica al ciclo 6 | Es configurable; la app no lo afirma |
| Fecha de inicio desconocida | Campo de configuración; estado vacío honesto |
| La idea es la más obvia del challenge | El diferencial es la especificidad, no la idea |
| Un solo archivo se vuelve inmanejable | Secciones comentadas; CSS y JS en bloques ordenados |
| Se pierde foco por querer hacer todo | Alcance cerrado y explícito en la sección 5 |

---

## 14. Estado

- [x] Recorte de institución, carrera y ciclo
- [x] Investigación verificada de Tecsup
- [x] Malla real del ciclo 6
- [x] Decisiones de diseño y de honestidad de datos
- [x] Plan completo
- [ ] `index.html` — implementación
- [ ] Confirmar sílabos → `theoryAssessmentWeeks`
- [ ] Confirmar fecha de inicio del ciclo → `startDate`
- [ ] Deploy
- [ ] Capturas / GIF
- [ ] Post de submission
