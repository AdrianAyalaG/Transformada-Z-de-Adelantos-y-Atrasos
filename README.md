08/08/24
## Transformada Z de Adelantos y Atrasos

En esta clase se abordó la Transformada Z y su aplicación en la representación matemática de sistemas mediante la solución de ecuaciones en diferencias. Se estudiaron los conceptos de adelantos y atrasos en señales, así como las funciones de transferencia discretas correspondientes.

### 1. Muestreo en Términos Matemáticos

Para expresar una función de tiempo continuo en tiempo discreto, se introduce una variable "K" (número de muestras) a la variable "t" del tiempo continuo.

#### 💡 Ejemplo 1
\$$f(t) = f(kT)$$

### 2. Ecuación en Diferencias
Las ecuaciones en diferencias describen el comportamiento de un sistema en función de su entrada y salida. Estas pueden ser:

#### Lineales
Ecuaciones donde la variable "K" aparece con exponentes de uno y sin productos que la alteren.

#### 💡 Ejemplo 1:
\$$y(k) + 5y(k-2) + u(k) = 0$$

#### Homogéneas

Ecuaciones donde no se conoce la entrada ni aparece en la ecuación.

#### 💡 Ejemplo 2:

\[ y(k) + 5y(k-2) = 0 \]

#### No Homogéneas

Ecuaciones donde la variable "K" aparece con exponentes mayores a uno y productos que la alteran.

#### 💡 Ejemplo 3:

\$$y(k)^2 + 5y(0.2k) + u(2k) = 0$$

### 3. Solución de Ecuaciones en Diferencias

#### Métodos Iterativos

Consiste en calcular la solución paso a paso a partir de una condición inicial dada.

#### 💡 Ejemplo 4:

\$$y(k) = \frac{1}{3}[-2y(k-1) + y(k-2) + 2u(k-1) - 3u(k-2)]$$

* Condiciones iniciales:
  \$$y(-2) = 1, \, y(-1) = -2$$
  \$$u(k) = \begin{cases}
  1 & \text{si } k = 0, 1, 2, 3, \ldots \\
  0 & \text{si } k < 0 
  \end{cases}$$

* Cálculos:
  * \( k = 0 \)
    \$$y(0) = \frac{5}{3}$$
  * \( k = 1 \)
    \$$y(1) = -\frac{10}{9}$$
  * \( k = 2 \)
    \$$y(2) = \frac{26}{27}$$

#### Transformada Z

Es la contraparte discreta de la Transformada de Laplace.

* *Transformada de Laplace:*

  \$$L\{f(t)\} = \int_{0}^{\infty} f(t) \cdot e^{-st} \, dt$$

* *Transformada Z:*

  \$$Z\{f(k)\} = \sum_{k=0}^{\infty} f(k) \cdot z^{-k} = F(z)$$

Para resolver ecuaciones en diferencias usando la Transformada Z:

1. Aplicar la Transformada Z a la ecuación.
2. Despejar la salida del sistema.
3. Aplicar la Transformada Z inversa \( Z^{-1} \).

#### Atrasos

Desplazamiento de la función hacia la derecha.

#### 💡 Ejemplo 5

\$$Z\{f(k-1)\} = z^{-1} \cdot (f(-1)z + F(z))$$

#### Adelantos

Desplazamiento de la función hacia la izquierda.

#### 💡 Ejemplo 6

\$$Z\{f(k+1)\} = z \cdot (F(z) - f(0))$$

#### Función de Transferencia en Tiempo Discreto

Relación entre la salida y la entrada del sistema.

#### 💡 Ejemplo 7

\$$H(z) = \frac{Y(z)}{X(z)}$$

#### 💡 Ejemplo Clase 1

* Encontrar la función de transferencia para la ecuación:

  \$$3y(k) + 2y(k-1) - y(k-2) = 2u(k-1) - 3u(k-2)$$

* Aplicando Transformada Z:

  \$$3Y(z) + 2z^{-1}(Y(z) + y(-1)z) - z^{-2}(Y(z) + y(-1)z + y(-2)z^2) = 2z^{-1}U(z) - 3z^{-2}U(z)$$

  \$$Y(z) = \frac{U(z)(2z^{-1} - 3z^{-2})}{3 + 2z^{-1} - z^{-2}}$$

  \$$\frac{Y(z)}{U(z)} = \frac{2z^{-1} - 3z^{-2}}{3 + 2z^{-1} - z^{-2}}$$

  * Multiplicando por el exponente de mayor magnitud:

  \$$\frac{Y(z)}{U(z)} = \frac{2z - 3}{3z^2 + 2z - 1}$$

## 📚 Ejercicios

1. *Función de Transferencia:*

  Dada la ecuación:

  \$$y(k) - 4y(k-1) + 5y(k-2) - 8y(k-3) = u(k) - 3u(k-1) + 9u(k-2)$$

  * Transformada Z:

  \$$Y(z) - 4z^{-1}Y(z) + 5z^{-2}Y(z) - 8z^{-3}Y(z) = U(z) - 3z^{-1}U(z) + 9z^{-2}U(z)$$

  \$$Y(z) = \frac{U(z)(-3z^{-1} + 9z^{-2})}{1 - 4z^{-1} + 5z^{-2} + 8z^{-3}}$$

  * Cambiar a \( z \) positivas:

  \$$\frac{Y(z)}{U(z)} = \frac{-3z^2 + 9z}{z^3 - 4z^2 + 5z + 8}$$

## Conclusiones

La Transformada Z es esencial para el análisis y diseño de sistemas discretos, facilitando la conversión de problemas en el dominio temporal discreto a un dominio de frecuencia complejo. Comprender los conceptos de adelantos, atrasos y funciones de transferencia en el dominio Z es clave para diseñar sistemas digitales eficaces.

## Referencias

[1] “AulasVirtualesECCI: Entrar al sitio”, Edu.co. [En línea]. Disponible: https://aulas.ecci.edu.co/course/view.php?id=9304 . [Consulta: 20 de agosto de 2024].
