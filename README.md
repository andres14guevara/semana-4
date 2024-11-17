# Controladores por Retroalimentación de Estados

Este documento explica los conceptos clave sobre controlabilidad, observabilidad y el diseño de controladores por retroalimentación de estados.

---

## Controlabilidad y Observabilidad

### Controlabilidad

Un sistema es **controlable** en el tiempo \( t_0 \) si puede transferirse desde cualquier estado inicial \( x(t_0) \) a cualquier otro estado, mediante un vector de control sin restricciones, en un intervalo de tiempo finito.

En otras palabras:
- **El sistema puede seguir cualquier estado aplicado como entrada en sus variables de estado.**

#### Matriz de Controlabilidad
- Si el sistema es controlable, entonces el determinante de la matriz de controlabilidad es diferente de 0.
- Si el sistema es controlable, el rango de la matriz de controlabilidad es igual a la cantidad de variables de estado.

#### Ejemplo:
![](https://github.com/andres14guevara/semana-4/blob/main/imagen%202-3apuntes..png)

---

### Observabilidad

Un sistema es **observable** en el tiempo \( t_0 \) si, con el sistema en el estado \( x(t_0) \), es posible determinar este estado a partir de la observación de la salida durante un intervalo de tiempo finito.

En otras palabras:
- **Es posible estimar cualquier estado a partir de la salida y la entrada conocidas.**

#### Matriz de Observabilidad
- Las dimensiones de la matriz de observabilidad coinciden con las dimensiones de la matriz \( A \).
- Si el sistema es observable, entonces el determinante de la matriz de observabilidad es diferente de 0.
- Si el sistema es observable, el rango de la matriz de observabilidad es igual a la cantidad de variables de estado.

#### Ejemplo:
![](https://github.com/andres14guevara/semana-4/blob/main/imagen%201-3apuntes..png)

---

## ¿Para qué sirven?

Las condiciones de **controlabilidad** y **observabilidad** determinan la existencia de soluciones para problemas de control. 

- La mayoría de los sistemas físicos en la realidad son controlables y observables.
- Sin embargo, los modelos obtenidos en algunas ocasiones no cumplen estas condiciones.

---

## Control por Retroalimentación de Estados

El objetivo de la **retroalimentación de estados** es asignar los polos del sistema en lazo cerrado de manera arbitraria por medio de ganancias proporcionales.

- La señal de control \( u(t) \) se obtiene a partir de las variables de estado.
- Por lo tanto, es necesario **conocer o medir todas las variables de estado.**

---

## Representación en Bloques del Espacio de Estados

_**Espacio para subir una imagen aquí.**_

---

## Metodología de Diseño

1. **Comprobar Controlabilidad:**
   - Asegurarse de que el sistema sea controlable mediante el cálculo de la matriz de controlabilidad.

2. **Determinar los Coeficientes del Polinomio Característico (Lazo Abierto):**
   \[
   zI - A = z^n + a_1 z^{n-1} + \dots + a_{n-1} z + a_n
   \]

3. **Determinar la Matriz de Transformación \( T \):**
   - Si el sistema está en forma canónica controlable, entonces \( T = I \) (matriz identidad).

4. **Determinar el Polinomio Deseado:**
   - A partir de la ubicación deseada de los polos:
     \[
     z^n + \alpha_1 z^{n-1} + \dots + \alpha_{n-1} z + \alpha_n
     \]

5. **Calcular la Matriz de Ganancias de Retroalimentación de Estado:**
   \[
   K = \begin{bmatrix}
   \alpha_n - a_n & \alpha_{n-1} - a_{n-1} & \dots & \alpha_2 - a_2 & \alpha_1 - a_1
   \end{bmatrix} T^{-1}
   \]

---

## Notas Finales

- **Controlabilidad y Observabilidad** son conceptos esenciales en el diseño de controladores.
- La retroalimentación de estados permite controlar las dinámicas del sistema mediante la ubicación arbitraria de polos.

### Espacios Reservados para Imágenes

Reemplaza los espacios etiquetados como _**Espacio para subir una imagen aquí**_ con tus diagramas, matrices, o ejemplos específicos.

---

### Autor

_Agrega aquí el nombre o equipo que desarrolla este contenido._

