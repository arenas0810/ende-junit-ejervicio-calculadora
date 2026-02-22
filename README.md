# Testing con Junit

Este es un ejemplo sencillo de pruebas unitarias usando Junit 5

Observa que este proyecto no tiene ninguna clase con el método `main`, no nos hace fatal. Además, tampoco tiene ningún `scanner` ni ningún `print`.

Haz un fork de este proyecto en tu repositorio de Github y contesta a las siguientes preguntas:

1. **¿Qué sentido puede tener este proyecto y para que lo podrías usar?**

    Este proyecto puede servir para practicar en ciertas facetas de la programación, con los atributos, objetos, métodos, etc. Este proyecto se podria usar a priori para calcular diversas operaciones matemáticas básicas.

2. **Revisa las pruebas de la suma y comenta lo que te parezca de interés**

    Me parece de interés el resultado que te da cuando testeas ya que en la pestaña de Test Results el resultado es muy confuso y no entiendo mucho lo que quiere decir. También, Me parece bueno que se almacenen los testeos que has realizado con sus resultados.

3. **Realiza un estudio de caja negra de la división e implementa las pruebas en junit: Se realizará en markdown.**
    
    ```bash
    public static int dividir(int a, int b) throws OperacionNoValidaException
    ```

    Entradas:
    a - dividendo (int)
    b - divisor (int)

    Salidas posibles:
    Resultado entero de a / b
    OperacionNoValidaException si b == 0
    
    ---
    
    1. Determinación de Clases de Equivalencia:
    
    |Clase|Descripción|Resultado esperado|
    |---|---|---|
    |C1|a>0, b>0|Positivo|
    |C2|a<0, b>0|Negativo|
    |C3|a>0, b<0|Negativo|
    |C4|a<0, b<0|Positivo|
    |C5|a=0, b=/0|0|
    |C6|b=0|OperacionNoValidaException|

    2. Análisis de valores límite

    |Caso|Entrada|Resultado esperado|
    |---|---|---|
    |V1|(5, 1)|5|
    |V2|(5, -1)|-5|
    |V3|(5, 0)|Excepción|
    |V4|(0, 5)|0|
    |V5|(0, -5)|0|

    3. Pruebas aleatorias

    |Caso|Entrada|Resultado esperado|
    |---|---|---|
    |P1|(27, 3)|9|
    |P2|(-45, 9)|-5|
    |P3|(100, -25)|-4|

    4. Conjetura de errores

        - No controla división por cero.
        - Excepción sin mensaje correcto, podria poner "ERROR".

    5. Generación de casos de uso
     
    Casos válidos
    |Caso|Entrada|Resultado esperado|
    |---|---|---|
    |CU1|(10, 2)|5|
    |CU2|(-10, 2)|-5|
    |CU3|(-10, -2)|5|

    Casos inválidos
    Caso|Entrada|Resultado esperado|
    |---|---|---|
    |CU4|(5, 0)|OperacionNoValidaException|
    |CU5|(0,0)|OperacionNoValidaException|




## Instrucciones

El alumno deberá hacer un fork de este proyecto e implementar la solución solicitada (preguntas y código).

>Se deberá utilizar este fichero, y los artefactos de código del proyecto, para resolver el ejercicio.


**Si no se puede acceder al repositorio la evaluación del ejercicio será de 0. No se evaluarán entregas modificadas/entregadas fuera del plazo establecido en la tarea**