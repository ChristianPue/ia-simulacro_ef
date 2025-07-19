# 🧠 Redes Hopfield

## 🔷 Patrones de Entrenamiento

- Patrón $P_1 = [1, -1, 1]$
- Patrón $P_2 = [-1, 1, -1]$
- Estado inicial (incompleto): $E = [1, -1, -1]$

---

## 🛠️ Aprendizaje con la regla de Hebb

Se calcula el producto externo de cada patrón de entrenamiento:

### Matriz de pesos $W_1 = P_1^\top \cdot P_1$

$$
W_1 = 
\begin{bmatrix}
1 \\
-1 \\
1
\end{bmatrix}
\cdot
\begin{bmatrix}
1 & -1 & 1
\end{bmatrix}
=
\begin{bmatrix}
1 & -1 & 1 \\
-1 & 1 & -1 \\
1 & -1 & 1
\end{bmatrix}
$$

### Matriz de pesos $W_2 = P_2^\top \cdot P_2$

$$
W_2 =
\begin{bmatrix}
-1 \\
1 \\
-1
\end{bmatrix}
\cdot
\begin{bmatrix}
-1 & 1 & -1
\end{bmatrix}
=
\begin{bmatrix}
1 & -1 & 1 \\
-1 & 1 & -1 \\
1 & -1 & 1
\end{bmatrix}
$$

### Matriz total de pesos: $W = W_1 + W_2$

$$
W =
\begin{bmatrix}
2 & -2 & 2 \\
-2 & 2 & -2 \\
2 & -2 & 2
\end{bmatrix}
$$

Eliminamos la diagonal para evitar autoconexión:

$$
W =
\begin{bmatrix}
0 & -2 & 2 \\
-2 & 0 & -2 \\
2 & -2 & 0
\end{bmatrix}
$$

---

## 🔍 Evaluación del patrón inicial

### Regla de activación:

Si $h_i > 0 \Rightarrow S_i = 1$  
Si $h_i < 0 \Rightarrow S_i = -1$  
Si $h_i = 0 \Rightarrow S_i$ no cambia

### Estado inicial: $E = [1, -1, -1]$

#### Neurona 1

$$
h_1 = (1 \cdot 0) + (-1 \cdot -2) + (-1 \cdot 2) = 2 - 2 = 0 \Rightarrow S_1 = 1
$$

#### Neurona 2

$$
h_2 = (1 \cdot -2) + (-1 \cdot 0) + (-1 \cdot -2) = -2 + 2 = 0 \Rightarrow S_2 = -1
$$

#### Neurona 3

$$
h_3 = (1 \cdot 2) + (-1 \cdot -2) + (-1 \cdot 0) = 2 + 2 = 4 \Rightarrow S_3 = 1
$$

Nuevo estado: $E = [1, -1, 1]$

---

## 🔁 Verificación de estabilidad

Con $E = [1, -1, 1]$:

#### Neurona 1

$$
h_1 = (1 \cdot 0) + (-1 \cdot -2) + (1 \cdot 2) = 2 + 2 = 4 \Rightarrow S_1 = 1
$$

#### Neurona 2

$$
h_2 = (1 \cdot -2) + (-1 \cdot 0) + (1 \cdot -2) = -2 - 2 = -4 \Rightarrow S_2 = -1
$$

#### Neurona 3

$$
h_3 = (1 \cdot 2) + (-1 \cdot -2) + (1 \cdot 0) = 2 + 2 = 4 \Rightarrow S_3 = 1
$$

✅ El patrón se mantiene estable: $E = [1, -1, 1]$  
📌 La red converge correctamente al patrón $P_1$