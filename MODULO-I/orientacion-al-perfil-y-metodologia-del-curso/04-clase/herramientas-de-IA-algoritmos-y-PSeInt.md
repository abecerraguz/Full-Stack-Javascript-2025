# Herramientas de IA, algoritmos y PSeInt  
_M1: Orientacion al perfil y metodologia del curso – AE4_

![Herramientas de IA, algoritmos y PSeInt](./img/header_ia_algoritmos_pseint.png)

Esta guia esta pensada para que la uses como **material de consulta** durante el modulo.  
No es necesario que sepas programar: la idea es acompanarte paso a paso desde **cero logica** hasta tus **primeros algoritmos** en PSeInt, y mostrarte como la **inteligencia artificial (IA)** puede ayudarte en el proceso.

---

## 1. ¿Que es un algoritmo?

Un **algoritmo** es una lista de pasos ordenados que sirve para resolver un problema o realizar una tarea.

- Es como una **receta de cocina**:  
  - tiene ingredientes (datos de entrada),  
  - tiene pasos (proceso),  
  - y tiene un plato final (salida).

![Algoritmo como receta](./img/algoritmo_receta.png)

(Un algoritmo no siempre se ve como codigo: la imagen lo muestra como comentarios porque estamos en un entorno "estilo editor", pero la idea es la misma: pasos claros y ordenados).

Un algoritmo debe:

- Tener **entrada**: los datos con los que trabajará (por ejemplo, notas, edades, precios).
- Tener **proceso**: los pasos que se realizan con esos datos.
- Tener **salida**: el resultado que se obtiene (un promedio, un mensaje, un total a pagar).
- Ser **claro**: cada paso debe entenderse sin ambigüedades.
- Ser **finito**: no puede quedarse ejecutándose para siempre; en algún momento termina.

### Ejemplo cotidiano

> **Problema:** Hacer un té.  
> **Algoritmo posible:**
> 1. Calentar agua.  
> 2. Poner una bolsa de té en la taza.  
> 3. Verter el agua caliente en la taza.  
> 4. Esperar unos minutos.  
> 5. Retirar la bolsa de té.  
> 6. Endulzar si quieres.  
> 7. Beber.

Aunque no haya “código”, eso ya es un algoritmo.

---

## 2. Pensamiento algorítmico (sin miedo a la palabra)

El **pensamiento algorítmico** es la capacidad de:

- **Dividir** un problema grande en partes pequeñas.
- Ordenar los pasos de forma lógica.
- Detectar repeticiones (cosas que hacemos muchas veces).
- Tomar decisiones según condiciones (“si pasa X, hago Y”).

Lo usas todo el tiempo:

- Al seguir una receta.
- Al organizar tu semana.
- Al decidir qué hacer primero cuando tienes muchas tareas.

Programar es **convertir ese pensamiento** en instrucciones que entienda una computadora.

---

## 3. ¿Qué es el pseudocódigo?

El **pseudocódigo** es una forma de escribir algoritmos usando frases parecidas al lenguaje natural, pero con una estructura más ordenada y cercana al código.

- No es un lenguaje de programación real.
- No lo entiende directamente la computadora.
- Se usa para **planificar** y **entender** la lógica de un programa.

Ventajas:

- Es más fácil de leer que un lenguaje de programación.
- Evita errores de sintaxis (tildes, puntos y comas, etc.).
- Te ayuda a pensar en la lógica antes de preocuparte por detalles técnicos.

### Ejemplo: determinar si una persona es mayor de edad

**Problema:** Leer la edad de una persona y mostrar si es mayor o menor de edad.

**Pseudocódigo:**

```pseint
Algoritmo Mayor_De_Edad
    Definir edad Como Entero

    Escribir "Ingrese su edad:"
    Leer edad

    Si edad >= 18 Entonces
        Escribir "Mayor de edad"
    Sino
        Escribir "Menor de edad"
    FinSi
FinAlgoritmo
```

Palabras clave importantes:

- `Escribir`: muestra un mensaje.
- `Leer`: pide un dato al usuario.
- `Si ... Entonces ... Sino ... FinSi`: toma decisiones.
- `Algoritmo ... FinAlgoritmo`: marca el inicio y el fin.

---

## 4. PSeInt: tu primer laboratorio de algoritmos

**PSeInt** es un programa que permite escribir pseudocódigo y **simular** cómo se ejecutaría.

Con PSeInt puedes:

- Escribir algoritmos en pseudocódigo.
- Ejecutarlos de manera normal.
- Ejecutarlos **paso a paso**, viendo cómo cambian las variables.
- Ver el **diagrama de flujo** correspondiente.

### Pasos básicos para usar PSeInt

1. Abrir PSeInt.
2. Crear un nuevo algoritmo.
3. Escribir el pseudocódigo.
4. Guardar el archivo (`.psc`).
5. Ejecutar:
   - Normal: botón “Ejecutar”.
   - Paso a paso: botón “Paso a paso” (muy útil para aprender).

---

## 5. Primer ejemplo en PSeInt: sumar dos números

Este ejemplo muestra cómo leer datos, sumarlos y mostrar el resultado.

```pseint
Algoritmo Suma_Dos_Numeros
    Definir a, b, suma Como Entero

    Escribir "Ingrese el primer numero:"
    Leer a

    Escribir "Ingrese el segundo numero:"
    Leer b

    suma <- a + b

    Escribir "La suma es: ", suma
FinAlgoritmo
```

![Algoritmo suma de dos números en PSeInt](./img/pseint_suma_dos_numeros.png)

### ¿Qué deberías observar?

Si ejecutas este algoritmo en modo **“Paso a paso”** en PSeInt, podrás ver:

- Cómo se guardan los valores que ingresas en `a` y `b`.
- Cómo se calcula `suma <- a + b`.
- Cómo cambia el valor de la variable `suma` justo después de la operación.

---

## 6. El factorial de un número

El **factorial** de un número entero `n` se escribe `n!` (se lee “n factorial”).

Significa:

> Tomar el número `n` y multiplicarlo por todos los números que vienen antes, hasta llegar al 1.

Ejemplos:

- `3! = 3 × 2 × 1 = 6`
- `4! = 4 × 3 × 2 × 1 = 24`
- `5! = 5 × 4 × 3 × 2 × 1 = 120`

**Caso especial importante:**

- `0! = 1` (esto se define así en matemáticas y conviene memorizarlo).

Puedes pensar el factorial como **“bajar por una escalera multiplicando”**:

- Para `5!`:
  - empiezas en 5,
  - bajas al 4 y multiplicas,
  - bajas al 3 y multiplicas,
  - bajas al 2 y multiplicas,
  - bajas al 1 y multiplicas.

---

## 7. ¿Qué es una variable acumuladora?

Una **variable acumuladora** es una variable que **va sumando o multiplicando resultados** a lo largo de un ciclo.

En el factorial, la variable acumuladora suele llamarse `fact` o `factorial`:

- Empieza en 1:
  ```pseint
  fact <- 1
  ```
- En cada vuelta del ciclo se actualiza:
  ```pseint
  fact <- fact * i
  ```

Así, `fact` va guardando el resultado parcial:

- Al principio: `fact = 1`
- Después de multiplicar por 1: `fact = 1`
- Después de multiplicar por 2: `fact = 2`
- Después de multiplicar por 3: `fact = 6`
- Después de multiplicar por 4: `fact = 24`
- …

![Factorial y variable acumuladora](./img/factorial_acumulador.png)

---

## 8. Algoritmo del factorial en PSeInt

Aquí tienes un algoritmo completo en PSeInt para calcular el factorial de un número:

```pseint
Algoritmo Factorial_De_Un_Numero
    Definir n, i Como Entero
    Definir fact Como Entero

    Escribir "Ingrese un numero entero mayor o igual a 0:"
    Leer n

    Si n < 0 Entonces
        Escribir "No existe factorial de numeros negativos."
    Sino
        fact <- 1  // variable acumuladora

        Para i <- 1 Hasta n Con Paso 1 Hacer
            fact <- fact * i
            Escribir "Iteracion ", i, ": fact = ", fact
        FinPara

        Escribir "El factorial de ", n, " es: ", fact
    FinSi
FinAlgoritmo
```

### ¿Qué pasa cuando se ejecuta?

Si ingresas `n = 4`, en cada iteración verás:

- Iteración 1: `i = 1` → `fact = 1 * 1 = 1`
- Iteración 2: `i = 2` → `fact = 1 * 2 = 2`
- Iteración 3: `i = 3` → `fact = 2 * 3 = 6`
- Iteración 4: `i = 4` → `fact = 6 * 4 = 24`

Resultado final:

- El programa mostrará: `El factorial de 4 es: 24`

Te recomendamos:

- Probar con `n = 0`
- Probar con `n = 3`
- Probar con `n = 5`

Y observar cómo cambia `fact` en la ventana de **variables** de PSeInt.

---

## 9. Ejecución paso a paso y vista de variables en PSeInt

La opción de **“Paso a paso”** de PSeInt es una de las herramientas más importantes para aprender.

Cuando ejecutas un algoritmo paso a paso, puedes ver:

- Qué línea se está ejecutando.
- Cómo cambian las variables (`i`, `fact`, `suma`, etc.).
- El orden real de ejecución del programa.

Esto te ayuda a:

- Entender **qué está haciendo el algoritmo por dentro**.
- Detectar errores de lógica.
- Relacionar el pseudocódigo con lo que luego harás en un lenguaje real de programación.

---

## 10. IA como apoyo a la programación

Hoy existen herramientas de **inteligencia artificial** que ayudan a programadores y estudiantes, por ejemplo:

- **ChatGPT**
- **GitHub Copilot**
- Otros asistentes integrados en editores de código

Con ellas puedes:

- Pedir explicaciones de código.
- Pedir que te generen pseudocódigo.
- Pedir ideas para mejorar un algoritmo.
- Preguntar por errores y posibles soluciones.

### Ejemplo de prompt útil

```text
Explícame con palabras simples qué es el factorial de un número
y genera el pseudocódigo en formato PSeInt para calcularlo.
Luego explícame qué hace la variable fact en ese algoritmo.
```

### Buenas prácticas al usar IA

- No copiar y pegar sin leer: **entiende** lo que la IA te devuelve.
- No pegar datos privados (contraseñas, nombres reales, etc.).
- Usar la IA como **apoyo para aprender**, no como reemplazo de tu razonamiento.

---

## 11. Actividades para practicar

Si quieres reforzar lo aprendido, puedes intentar estas actividades:

1. **Promedio de 3 notas**  
   - Escribe en pseudocódigo y en PSeInt un algoritmo que:
     - Pida 3 notas.
     - Calcule el promedio.
     - Muestre el resultado.

2. **Modificar el factorial**  
   - Toma el algoritmo del factorial y:
     - Agrega un mensaje especial si `n = 0`.
     - Por ejemplo: “El factorial de 0, por definición, es 1”.

3. **Inventar tu propio problema**  
   - Piensa en algo cotidiano (ej: calcular el total de una compra con descuento).
   - Escribe los pasos en lenguaje normal.
   - Luego pásalos a pseudocódigo en estilo PSeInt.
   - Si quieres, pídele ayuda a una IA usando un prompt como:
     ```text
     Genera el pseudocódigo en PSeInt para un algoritmo que lea el precio
     de un producto y un porcentaje de descuento, y muestre el precio final
     a pagar. Explícalo como si yo recién estuviera aprendiendo a programar.
     ```

---

## 12. Mensaje final

- No necesitas ser “bueno en matemáticas” para aprender algoritmos.
- Lo importante es **pensar paso a paso**.
- PSeInt te ayuda a ver lo que está pasando “por dentro”.
- La IA puede ser una **herramienta extra** para entender mejor y practicar.

Tómatelo con calma, experimenta, rompe los algoritmos y vuelve a armarlos.  
Así se aprende a programar 🙂  
