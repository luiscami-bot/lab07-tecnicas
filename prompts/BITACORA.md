# Bitacora de tecnicas avanzadas 
Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: Chatgpt 
## Ejercicio 2: Zero-shot, one-shot y few-shot 
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| **Zero-shot** | 5 | Tabla con emojis y mensaje de introducción | No |
| **One-shot** | 5 | Lista numerada con flechas (`1. Comentario → Clasificación`) | Sí |
| **Few-shot** | 5 | Texto entre comillas con flecha (`"Comentario" -> Clasificación`) | Sí |
## Ejercicio 3: Chain of Thought 
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|---|---|---|---|
| Directo | 318.24 | No | No |
| Paso a paso | Muestra el desarrollo detallado (descuento del 25%, IGV del 18%, total por 3 unidades y comprobación) dando como resultado S/ 318.60. | Si | Si |
## Ejercicio 4: Role prompting 
| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
| :--- | :--- | :--- | :--- |
| **A. Sin rol** | **Sencillo y directo.** Usa lenguaje cotidiano, explica con la analogía básica de una caja y evita tecnicismos profundos[cite: 1]. | **Sí.** Muestra ejemplos breves y conceptuales de código en Python (`edad = 20`)[cite: 1]. | **Usuarios que buscan una respuesta rápida** o una definición directa sin rodeos ni explicaciones extensas[cite: 1]. |
| **B. Rol docente** | **Sencillo, didáctico y gradual.** Utiliza un tono pedagógico, diminutivos ("cajita"), analogías cotidianas (casillero de colegio) e introduce tipos de datos paso a paso[cite: 2]. | **Sí.** Emplea varios bloques de código en Python, muestra la salida (`print`) y un diagrama en texto[cite: 2]. | **Principiantes absolutos** que jamás han programado y necesitan una explicación pausada y muy visual[cite: 2]. |
| **C. Rol senior** | **Técnico y formal.** Incorpora conceptos de arquitectura como *espacio de memoria*, *tipado estático*, *asignación* y reglas de inmutabilidad (`final`)[cite: 3]. | **Sí.** Utiliza Java con sintaxis tipada (`int`, `String`), operaciones entre variables y representación de memoria[cite: 3]. | **Desarrolladores o estudiantes con bases** que buscan comprender el funcionamiento de las variables en lenguajes tipados o a nivel de sistema[cite: 3]. |
## Ejercicio 5: Descomposicion 
# Bitácora de Desarrollo del Sistema de Inventario

---

### Paso 1: Definición de Requisitos
* **Entrega de la IA:** Una lista estructurada con los 5 requisitos principales para un sistema de inventario en Java (Gestión de productos, Control de stock, Registro de ventas, Alertas de stock bajo, y Reportes y consultas)[cite: 2].
* **Comparación con el pedido de una sola vez:** A diferencia del primer intento generalista donde la IA ofrecía elegir entre web, escritorio o Excel[cite: 1], aquí acotó los requisitos específicamente al lenguaje y alcance solicitado[cite: 2].

---

### Paso 2: Diseño de Clases y Atributos
* **Entrega de la IA:** Una tabla con la estructura de 6 clases principales (`Producto`, `Inventario`, `Venta`, `DetalleVenta`, `Movimiento`, `Reporte`), detallando sus atributos, tipos de datos y relaciones[cite: 3].
* **Comparación con el pedido de una sola vez:** Frente a la propuesta abstracta inicial[cite: 1], transformó las necesidades en una arquitectura de datos técnica y concreta lista para programar[cite: 3].

---

### Paso 3: Codificación de la Clase Base
* **Entrega de la IA:** El código fuente completo en Java para la clase `Producto`, incorporando encapsulamiento con atributos privados, constructor y métodos *getter/setter*[cite: 4].
* **Comparación con el pedido de una sola vez:** En lugar de sugerencias conceptuales[cite: 1], entregó implementación real y ejecutable del primer componente del sistema[cite: 4].

---

### Paso 4: Revisión y Refactorización de Código
* **Entrega de la IA:** Tres propuestas de mejora técnica (validación de datos en setters, uso de `BigDecimal` para dinero y el método `toString()`) junto con una sugerencia adicional para evitar nulos[cite: 5].
* **Comparación con el pedido de una sola vez:** En lugar de quedarse en un alcance estático[cite: 1], realizó una auditoría de calidad de software orientada a robustez y buenas prácticas de programación[cite: 5].
## Ejercicio 6: Prompt estructurado y autocritica
PROMPT ESTRUCTURADO INICIAL:
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato>

MENSAJE DE AUTOCRÍTICA (PROMPT DE CORRECCIÓN):
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
