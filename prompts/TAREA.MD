# Tarea: Diseñar las Clases para un Sistema de Notas Escolares

---

## 1. Evolución del Prompt (Versiones v1, v2 y v3)

### Versión 1: Prompt Básico (Zero-Shot)

```text
Diseña las clases en Java para un sistema de gestión de notas escolares que maneje estudiantes, cursos y calificaciones.
```

* **Técnica agregada:** Ninguna (Zero-shot directo).
* **Por qué se usó:** Para establecer una línea base y evaluar cómo responde el modelo sin contexto, restricciones ni estructura.
* **Qué mejoró en la respuesta:** Entregó un esqueleto inicial mínimo de clases (`Estudiante`, `Curso`, `Nota`), pero sin diseño de arquitectura, relaciones claras ni reglas de negocio.

---

### Versión 2: Prompt Intermedio (Role + Prompt Estructurado)

```text
<rol>Actúa como un Líder Técnico Backend en Java y POO.</rol>
<contexto>Estamos desarrollando el módulo core para un sistema de gestión académica escolar.</contexto>

<tarea>
Diseña las clases del dominio para gestionar estudiantes, cursos y calificaciones.
</tarea>

<formato>
Presenta cada clase indicando:
- Atributos con sus tipos de datos.
- Métodos principales.
- Breve descripción de la responsabilidad.
</formato>
```

* **Técnica agregada:** **Role Prompting** + **Prompt Estructurado** (etiquetas XML).
* **Por qué se usó:** Para definir el perfil profesional de la IA y organizar el pedido en secciones claras, evitando respuestas vagas.
* **Qué mejoró en la respuesta:** Entregó un formato con mejor jerarquía visual y precisión técnica en los tipos de datos en Java, aunque obvió la lógica de promedios ponderados y relaciones avanzadas.

---

### Versión 3: Prompt Avanzado (Prompt Final)

```text
<rol>
Actúa como un Arquitecto de Software Orientado a Objetos (POO) especializado en Java.
</rol>

<contexto>
Estamos construyendo el módulo de notas escolares. Se requiere calcular promedios ponderados por período y manejar estados de aprobación de estudiantes sin acoplar rígidamente las clases.
</contexto>

<pasos_razonamiento>
Antes de mostrar la respuesta final, realiza un análisis paso a paso en una sección llamada "### Razonamiento de Arquitectura":
1. Identifica las entidades principales y resuelve la relación N:M entre Estudiante y Curso.
2. Define las reglas de negocio para el cálculo de promedios ponderados.
3. Elige los principios SOLID que eviten código duplicado o alto acoplamiento.
</pasos_razonamiento>

<ejemplos>
Ejemplo 1 (Entidad base):
Clase: Evaluacion
Atributos: - id: Long, - nombre: String, - pesoPorcentaje: double, - nota: double
Métodos: +calcularPuntajePonderado(): double, +esAprobatoria(): boolean

Ejemplo 2 (Entidad intermedia):
Clase: Matricula
Atributos: - id: Long, - estudiante: Estudiante, - curso: Curso, - evaluaciones: List<Evaluacion>
Métodos: +calcularPromedioCurso(): double, +obtenerEstado(): EstadoAprobacion
</ejemplos>

<tarea>
Diseña la estructura de clases en Java para las entidades: Estudiante, Curso, Matricula, Evaluacion y BoletinAcademico.
</tarea>

<formato_salida>
1. ### Razonamiento de Arquitectura
2. ### Especificación de Clases
Presenta las clases en formato de listas markdown usando la estructura del ejemplo provisto.
</formato_salida>
```

* **Técnica agregada:** **Chain of Thought (CoT)** + **Few-Shot Prompting**.
* **Por qué se usó:** Para obligar al modelo a razonar la arquitectura paso a paso antes de entregar el resultado y darle ejemplos del nivel de detalle esperado.
* **Qué mejoró en la respuesta:** Incluyó una justificación técnica previa, resolvió el acoplamiento $N:M$ agregando la entidad `Matricula` y manejó correctamente la lógica de notas ponderadas.

---

## 2. Desglose de Técnicas en el Prompt Final (v3)

| Parte / Sección del Prompt Final | Técnica de Prompting Aplicada |
| :--- | :--- |
| `<rol>Actúa como un Arquitecto de Software...</rol>` | **Role Prompting** (Rol específico sin usar "experto"). |
| `<pasos_razonamiento>1. Identifica... 2. Define...</pasos_razonamiento>` | **Chain of Thought (CoT)** / **Descomposición**. |
| `<ejemplos>Ejemplo 1... Ejemplo 2...</ejemplos>` | **Few-Shot Prompting** (Múltiples ejemplos de referencia). |
| `<rol>`, `<contexto>`, `<tarea>`, `<formato_salida>` | **Prompt Estructurado** (Uso de etiquetas XML para organizar). |
| `<formato_salida>1. ### Razonamiento... 2. ### Especificación...</formato_salida>` | **Formato de respuesta definido**. |

---

## 3. Justificación de las Técnicas Elegidas

Elegí **Role Prompting**, **Chain of Thought (CoT)**, **Few-Shot** y **Prompt Estructurado** porque el diseño de clases requiere precisión arquitectónica y apego estricto a las reglas de la programación orientada a objetos. El **Role Prompting** delimitó el criterio técnico; el **Prompt Estructurado** separó claramente las restricciones; el **Few-Shot** garantizó que la IA adoptara la granularidad deseada sin divagar; y la **Cadena de Pensamiento (CoT)** obligó al modelo a deducir las relaciones entre entidades antes de escribirlas. Decidí no utilizar la técnica de *Autocrítica* en el prompt final debido a que el análisis previo con CoT ya resolvía las incoherencias lógicas en un solo ciclo de generación.

---

## 4. Tabla de Evaluación del Resultado (Bitácora de Cotejo)

| Criterio de Evaluación | Cumple (Sí / No) |
| :--- | :---: |
| ¿El rol definido es específico y evita la palabra genérica "experto"? | **Sí** |
| ¿El prompt final incluye al menos tres técnicas combinadas y un formato definido? | **Sí** |
| ¿El resultado incluye la sección de razonamiento paso a paso (CoT)? | **Sí** |
| ¿Las clases diseñadas resuelven adecuadamente el problema sin presentar incoherencias? | **Sí** |