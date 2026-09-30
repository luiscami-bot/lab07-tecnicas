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
## Ejercicio 6: Prompt estructurado y autocritica
