# GESTORDENOTAS

Aplicación web para la gestión académica de asignaturas: notas, rúbricas por Resultados de Aprendizaje (RA), asistencia, consolidados y análisis estadístico por grupo y por estudiante. Incluye además un módulo independiente para la gestión de RAs a nivel de programa académico completo.

Toda la información vive en memoria mientras la pestaña está abierta; el respaldo y el traslado de datos entre equipos se hace mediante archivos `.json` descargables (ver [Guardar y cargar información](#guardar-y-cargar-información)).

## Funcionalidades

### Gestor de Notas RA

Al entrar se muestra **Mis Cursos**: una lista de todas las asignaturas creadas en la sesión.

- Crear cursos nuevos (siempre en blanco, sin datos de ejemplo), abrirlos o eliminarlos.
- Cada curso conserva su propia información de forma independiente mientras se navega entre ellos.

Dentro de un curso, el menú lateral da acceso a:

- **Información General** — datos del curso (institución, materia, programa, grupo, período, duración, % de inasistencia permitido) y el listado de estudiantes, editable directamente en la tabla (documento, nombre, email institucional y personal). Incluye:
  - Carga del listado de estudiantes desde el archivo Excel/HTML institucional.
  - Carga de un respaldo de un solo curso (`curso.json`).
  - Copiar todos los correos (institucionales y personales) para un envío masivo.
  - Marcar un estudiante como "no pertenece al grupo" (p. ej. trasladado de otro salón): sigue viendo su ficha y comparativa individual, pero queda fuera de los promedios y gráficas del grupo.
- **Manual Estudiantil** — resumen navegable del reglamento académico institucional (asistencia, evaluación, estímulos, disciplina, etc.), con enlace al PDF oficial completo.
- **Resultados (RAs)** — creación y edición de los Resultados de Aprendizaje del curso; descarga y carga de una plantilla de RAs en `.json` para reutilizarlos en otro curso.
- **Rúbricas** — construcción de la rúbrica de evaluación por momentos (parciales, entregas, etc.), cada uno con su peso; cada momento puede tener actividades independientes o criterios directos, cada criterio vinculado a uno o varios RA. Incluye plantillas descargables/cargables (curso completo o un solo momento) y exportación de la ficha de rúbrica en PDF o imagen.
- **Asistencia** — registro de sesiones de clase (fecha, horas, si es evaluativa y a qué momento pertenece), marcación de faltas por estudiante y sesión, resumen del curso con semáforo de riesgo por inasistencia, registro de cancelación de la asignatura por estudiante, y exportación del reporte completo a Excel.
- **Evaluación** — calificación por criterio o por actividad, de forma individual o por grupo de trabajo; retroalimentación cualitativa, nota calculada en vivo y nivel de desempeño.
- **Consolidado Grupal** — tabla única con nota por momento, nota definitiva, asistencia y desempeño de cada estudiante; filtros, modo mapa de calor y exportación a Excel o imagen.
- **Análisis Grupal** — KPIs del curso, distribución de notas y desempeño, dispersión por criterio/momento, evolución por momentos, rendimiento por RA, alertas de riesgo (notas y asistencia) y exportación del informe completo en PDF/imagen.
- **Análisis Individual** — ficha de seguimiento por estudiante: notas, comparación de su rúbrica contra el promedio y el máximo del grupo, asistencia, retroalimentación y estado de alerta por inasistencia acumulada; exportable de forma individual o en lote (todos los estudiantes en un `.zip`).

### Gestión de RAs de Programa

Módulo independiente para trabajar los RA a nivel de todo un programa académico (no de un curso puntual):

- Información general del programa.
- Definición de los RA de programa (RAM): código, título, descripción, categoría, eje temático y asignaturas que lo validan.
- Plan de estudios por semestres, con vistas de lista, grilla, mapa de prerrequisitos y matriz RAM × asignatura.
- Plantillas de rúbrica por categoría de evaluación.
- Mapeo de asignaturas a categorías de evaluación por semestre.
- Guía de referencia sobre la metodología para definir RA y categorías.

### Guardar y cargar información

- **Guardar** → *Guardar Todos los Cursos* (un solo archivo con todos los cursos de la sesión) o *Guardar Curso Actual* (solo el curso abierto, útil para compartir una asignatura puntual).
- **Cargar** → *Cargar Todos los Cursos* (reemplaza la lista completa de cursos) o *Cargar Curso Específico* (carga un curso puntual dentro del curso que se tiene abierto).
- **Limpiar** — reinicia únicamente el curso que se está viendo.

## Ejecutar en local

**Requisitos:** Node.js

```bash
npm install
npm run dev
```

La app queda disponible en `http://localhost:3000`.

Otros comandos disponibles:

```bash
npm run build     # build de producción
npm run preview    # sirve el build de producción localmente
npm run lint       # verificación de tipos (tsc --noEmit)
```
