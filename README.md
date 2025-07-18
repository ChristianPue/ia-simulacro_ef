# 🧠 Simulacro para el Examen Final de Inteligencia Artificial

Este repositorio contiene la resolución de seis problemas enfocados en redes neuronales, aprendizaje supervisado, no supervisado y procesamiento de lenguaje natural. Cada ejercicio se desarrolla paso a paso para reforzar conceptos clave del curso y fomentar la aplicación práctica de los algoritmos.

---

## 📘 Problema 1: Adaline - Entrenamiento Manual (3 puntos)

**Objetivo:** Utilizar el algoritmo Adaline para entrenar manualmente una red neuronal con los siguientes datos:

| x1  | x2  | dx  |
|-----|-----|-----|
| -2  | -1  | -1  |
| -1  | -1.5| -1  |
|  2  | -2  | -1  |
| -2  |  1  |  1  |
| 1.5 | 0.5 |  1  |
|  1  |  1  |  1  |

**Condiciones iniciales:**
- Pesos: `w1 = 1`, `w2 = 0.5`, `θ = 0`
- Tasa de aprendizaje: `η = 0.1`

**Instrucciones:**
- Realizar una iteración completa manual para todos los datos.
- Calcular los nuevos pesos.
- Mostrar el Error Cuadrático Medio (ECM) final.

---

## ⚙️ Problema 2: Perceptrón Multicapa – XOR (3 puntos)

**Objetivo:** Entrenar una red MLP con backpropagation para resolver el problema lógico XOR usando los siguientes patrones:

| x1  | x2  | XOR |
|-----|-----|-----|
| -1  | -1  | -1  |
|  1  | -1  |  1  |
| -1  |  1  |  1  |
|  1  |  1  | -1  |

**Arquitectura:**
- Entradas: `2`
- Capa oculta: `1 capa con 2 neuronas`
- Salida: `1 neurona con función sigmoide`

**Parámetros:**
- Tasa de aprendizaje: `η = 0.1`
- Pesos iniciales: valores pequeños

**Instrucciones:**
- Realizar el entrenamiento paso a paso **solo para el primer patrón de entrada**.

---

## 🗺️ Problema 3: SOM – Mapa Autoorganizado (4 puntos)

**Objetivo:** Aplicar una iteración de entrenamiento a un mapa autoorganizado con datos no etiquetados:

| ID | x1   | x2   |
|----|------|------|
| 1  | -4   | 4    |
| 2  | -3.5 | -2.5 |

**Pesos Iniciales:**

| Neurona | W₁   | W₂   |
|---------|------|------|
| A       | -0.5 | 0.5  |
| B       | 0.5  | -1.5 |
| C       | -1   | -1.5 |
| D       | 0.5  | 0.5  |

**Configuración:**
- Entrada usada: punto 1 `(-4, 4)`
- Tasa de aprendizaje: `α = 0.5`

**Instrucciones:**
- Actualizar el peso de la neurona ganadora (BMU) y sus vecinos.
- Mostrar los pesos actualizados al finalizar la iteración.

---

## 🧩 Problema 4: Red de Hopfield – Recuperación de Patrón (4 puntos)

**Objetivo:** Entrenar una red de Hopfield para almacenar y recuperar patrones binarios.

**Patrones de entrenamiento:**
- `P1 = [1, -1, 1]`
- `P2 = [-1, 1, -1]`

**Instrucciones:**
a) Calcular la matriz de pesos sinápticos utilizando la **regla de Hebb**.  
b) Ingresar el patrón incompleto `[1, -1, -1]`.  
c) Aplicar **actualizaciones secuenciales** hasta que se alcance un patrón estable.  
d) Mostrar cómo evoluciona el estado de la red en cada paso de actualización.

---

## 🌸 Problema 5: Backpropagation con Datos Reales – Iris Dataset (4 puntos)

**Objetivo:** Aplicar el algoritmo de retropropagación (backpropagation) en un MLP utilizando datos reales simplificados del conjunto **Iris**.

**Pasos:**
a) Seleccionar dos **clases** y dos **variables numéricas** para reducir dimensionalidad.  
b) Dividir el dataset en:
   - **70% entrenamiento**
   - **30% prueba**
c) Entrenar un **Perceptrón Multicapa (MLP)** con los datos de entrenamiento.  
d) Clasificar los datos de prueba y mostrar la **matriz de confusión**.

> 🔎 Este problema fortalece tu habilidad para aplicar redes neuronales a casos reales con validación estadística.

---

## 💬 Problema 6: Procesamiento de Lenguaje Natural – Gramática (2 puntos)

**Objetivo:** Verificar la derivación de la frase `"juan ama paula"` a partir de una gramática formal.

**Símbolos Terminales (ΣT):** `{juan, ama, paula}`  
**Símbolos No Terminales (ΣN):** `<frase>`, `<sujeto>`, `<predicado>`, `<verbo transitivo>`, `<objeto directo>`  
**Símbolo inicial:** `<frase>`

**Reglas de Producción:**
1. `<frase>` ::= `<sujeto>` `<predicado>`  
2. `<sujeto>` ::= `juan`  
3. `<predicado>` ::= `<verbo transitivo>` `<objeto directo>`  
4. `<verbo transitivo>` ::= `ama`  
5. `<objeto directo>` ::= `paula`

**Derivación Paso a Paso:**
```text
<frase>
→ <sujeto> <predicado>                      [Regla 1]
→ juan <predicado>                          [Regla 2]
→ juan <verbo transitivo> <objeto directo>  [Regla 3]
→ juan ama <objeto directo>                 [Regla 4]
→ juan ama paula                            [Regla 5]

```

---

📂 ¡Cada problema busca afianzar tus conocimientos en aprendizaje supervisado y no supervisado dentro de IA!
