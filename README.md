# Laboratorio 2 - Haskell

## 📌 Descripción  
Este laboratorio tiene como objetivo que los estudiantes fortalezcan sus conocimientos relacionados con **Haskell** y la programación funcional.

---

## Ambiente de desarrollo

[Jupyter Haskell](https://mybinder.org/v2/gh/IHaskell/IHaskell/mybinder). 

## 🛠️ Instrucciones Generales  

1. **Fork del repositorio**  
   - Realice un **fork** de este repositorio en su cuenta personal de GitHub.  
   - No realice cambios directamente sobre el repositorio original.

2. **Estructura de carpetas**  
   - Dentro de su fork, cree una carpeta llamada **`lab02/`**.  
   - Cada ejercicio debe resolverse en un archivo **independiente** con el siguiente formato:  
     ```
     lab02/ejercicio01.ipynb
     lab02/ejercicio02.ipynb
     ...
     ```  

3. **Resolución de ejercicios**  
   - Desarrolle los programas en el entorno de programacion indicado en clase.  
   - Una vez finalizados, copie el código a los archivos `.ipynb` correspondientes en su repositorio.  
   - Cada archivo debe contener:
     - La implementación de su solución.  

4. **Buenas prácticas**  
   - Use **nombres de predicados claros y significativos**.
---

## 🚀 Entrega  

- **Plazo**: La entrega debe realizarse a mas tardar el proximo lunes, se habilitara una tarea en Moodle para adjuntar el link del repositorio.

---

## ✅ Criterios de Evaluación  

1. **Correctitud de las soluciones** (funcionalidad de los predicados).  
2. **Cumplimiento de la estructura solicitada** (archivos independientes en `lab01/`).  
3. **Claridad en la codificación** (nombres, comentarios y legibilidad).  
4. **Uso adecuado de variables** (incluyendo variables anónimas donde corresponda).  

---

## 💡 Recomendaciones  

- Revise la documentación oficial de Haskell: [Haskell Documentation](https://www.haskell.org/documentation/).  
- Antes de subir sus archivos, **ejecute y verifique** cada consulta en el compilador en linea.  
- Mantenga su repositorio organizado y actualizado.

---

## Ejercicio 1 - Manejo de listas

1. Definir las siguientes funciones usando recursión.

```  
Retorna la longitud de una lista
miLength :: [a] -> Int

Retorna el último elemento de una lista
miLast :: [a] -> a

Duplica cada elemento de una lista de números
duplicar :: [Int] -> [Int]

Eliminar los elementos pares de una lista
eliminarPares :: [Int] -> [Int]
 ```

2. Define estas mismas funciones pero ahora usando funciones de orden superior como map y filter


---

## Ejercicio 2 - Listas por comprensión

1. Usa comprensión de listas para:

 ```
a. Obtener los cuadrados de los primeros 10 números.

b. Filtrar los divisibles por 3 entre 1 y 30.

c. Generar una lista de pares (x, y) donde x < y y ambos estén en [1..5].

 ```

2. Define una función que devuelva los divisores de un número (usando lista por comprensión):
    ```
     divisores :: Int -> [Int]
     ```

3. Define la función divisoresPropios, crea una función que determine si un número es perfecto (suma de sus divisores propios = número):

  ```
  esPerfecto :: Int -> Bool
  ```

---

## Ejercicio 3 - Funciones de orden superior


1. Reescribe las siguientes funciones sin recursión explícita, usando funciones de orden superior:
   
    ```
    a. Suma de todos los elementos
    sumaLista :: [Int] -> Int
    
    b. Contar cuántos elementos son mayores que 10
    mayoresQue10 :: [Int] -> Int
    
    c. Calcular el producto de una lista de números
    productoLista :: [Int] -> Int

    d. Convierte una lista de grados Celsius a Fahrenheit
    celsiusAFahrenheit :: [Double] -> [Double]

    e. Suma 5 a cada número impar de una lista y deja igual los pares.
    ajustarImpares :: [Int] -> [Int]
    ```
    
2. Define las siguientes funciones usando filter
   ```
   a. Devuelve solo los nombres con más de 5 letras.
   nombresLargos :: [String] -> [String]

   b. Filtra los números negativos de una lista.
   soloNegativos :: [Int] -> [Int]

   c. De una lista de edades, obtiene las que estén entre 18 y 25 años.
   edadesUniversitarios :: [Int] -> [Int]
   ```

3. Define las siguientes funciones usando filter y map
   ```
   a. Dada una lista de precios, sumar IVA (19%) solo a los valores mayores o iguales a 1000.
   agregarIVA :: [Double] -> [Double]

   b. De una lista de palabras, obtener solo las que comienzan con vocal y devolver su longitud.
   longitudesVocales :: [String] -> [Int]

   c. Dada una lista de números, devuelve los cuadrados de los pares.
   cuadradosPares :: [Int] -> [Int]
   ```

4. Define las siguientes funciones usando any o all
   ```
   a. Verifica si algún número en la lista es negativo.
   hayNegativo :: [Int] -> Bool

   b. Verifica si todos los números son pares.
   todosPares :: [Int] -> Bool

   c. Comprueba si todos los nombres empiezan con mayúscula.
   import Data.Char (isUpper)
   nombresCorrectos :: [String] -> Bool
   ```

5. Define las siguientes funciones usando takeWhile o dropWhile
   ```
   a.De una lista ordenada, toma los elementos menores que 100.
   menoresQue100 :: [Int] -> [Int]

   b. Quita los ceros iniciales de una lista.
   sinCerosIniciales :: [Int] -> [Int]
   ```
---

## Ejercicio 4 - Funciones que reciben y retornan funciones

1. Define una funcion que recibe una función que transforma un dato (por ejemplo, conversión de grados Celsius a Fahrenheit),
y lo aplica a una lista de datos.

   ```
   procesarLecturas :: (Double -> Double) -> [Double] -> [Double]
   #Implementa procesarLecturas

   Ejemplo:
   procesarLecturas celsiusAFaranheit [0,12,20]
   ```

2. Define una función que retorne un filtro personalizado:
    ```
   crearFiltro :: (a -> Bool) -> ([a] -> [a])
   #Implementa crearFiltro

   Ejemplo:
   
   soloPares = crearFiltro even
   soloPares [1..10] == [2,4,6,8,10]
    ```

3. Crea una función que genera “verificadores” de rangos.
    ```
    enRango :: Int -> Int -> (Int -> Bool)
    #Implementa enRango

    Ejemplo:
    
    entre5y10 = enRango 5 10
    entre5y10 7   -- True
    ```

4. Genera una función que eleva a una potencia dada.

   ```
   potenciador :: Int -> (Int -> Int)
   #Implementa potenciador

   Ejemplo:

   potencia5 = potenciador 5
   potencia5 7
   ```


## Ejercicio 5 - “El problema de las dos jarras” usando A*

**Objetivo:**

Usar el algoritmo A* para encontrar la secuencia más corta de acciones que permita medir exactamente 4 litros usando dos jarras:

* una de 5 litros,
* otra de 3 litros,
* y una fuente de agua infinita.

**Descripción del problema**

Tienes:

* Jarra A de capacidad 5 L
* Jarra B de capacidad 3 L

**Operaciones posibles:**

* Llenar una jarra completamente.
* Vaciar una jarra.
* Verter el contenido de una jarra en la otra hasta que una se vacíe o la otra se llene.

Estado inicial: (0, 0)

Meta: Estado donde la primera jarra tenga 4 litros, es decir: (4, 0 )

**Representación de estados**

Cada estado es un par (a, b) donde:

* a = litros en la jarra de 5 L
* b = litros en la jarra de 3 L
  
```
type Estado = (Int, Int)
type Nodo = Estado
type Costo = Int
type Grafo = [(Nodo, [(Nodo, Costo)])]
```

Definimos las operaciones válidas desde un estado (a, b):

```
capA, capB :: Int
capA = 5
capB = 3

-- Genera todos los estados alcanzables desde uno dado
vecinos :: Estado -> [(Estado, Costo)]
vecinos (a,b) =
  [ ((capA, b), 1)            -- Llenar jarra A
  , ((a, capB), 1)            -- Llenar jarra B
  , ((0, b), 1)               -- Vaciar jarra A
  , ((a, 0), 1)               -- Vaciar jarra B
  , (transferirAB (a,b), 1)  -- Verter A→B
  , (transferirBA (a,b), 1)  -- Verter B→A
  ]
```

Definir funciones de transicion de estados
```
-- Verter de A a B
-- Definir transferirAB :: Estado -> Estado

-- Verter de B a A
-- Definir transferirBA :: Estado -> Estado
```

Definir una heurística admisible

```
heuristica :: Estado -> Costo
```

Probar la solución con el algoritmo base de A*

```
import Data.List (sortOn)

aStar :: (Nodo -> [(Nodo, Costo)]) -> (Nodo -> Costo) -> Nodo -> Nodo -> [(Nodo, Costo)]
aStar sucesores heuristica inicio meta = buscar [(inicio, 0)] []
  where
    buscar [] _ = []
    buscar ((nodo, costo):cola) visitados
      | nodo == meta = [(nodo, costo)]
      | nodo `elem` visitados = buscar cola visitados
      | otherwise =
          let nuevos = [ (v, costo + c) | (v, c) <- sucesores nodo, v `notElem` visitados ]
              ordenados = sortOn (\(v, c) -> c + heuristica v) (cola ++ nuevos)
          in (nodo, costo) : buscar ordenados (nodo : visitados)

aStar vecinos heuristica inicio meta

```


## Retrospectiva
1. ¿Cuál fue el tiempo total invertido en el laboratorio por cada uno de ustedes? (Horas/Hombre)
El tiempo total invertido en el laboratorio fue aproximadamente de 10–12 horas, distribuidas entre la comprensión del problema, la implementación del algoritmo A* y la realización de pruebas para verificar su funcionamiento.

2. ¿Cuál es el estado actual del laboratorio? ¿Por qué?
El laboratorio se encuentra completado y funcional, ya que se logró implementar correctamente el algoritmo A* para resolver el problema de las dos jarras.
El programa permite encontrar una secuencia válida de pasos desde el estado inicial hasta el estado objetivo.

3. ¿Cuál consideran fue el mayor logro? ¿Por qué?
El mayor logro fue implementar correctamente el algoritmo A* en Haskell.
Esto fue importante porque permitió aplicar conceptos teóricos de búsqueda informada en un problema concreto y entender mejor el uso de heurísticas.

4. ¿Cuál consideran que fue el mayor problema técnico? ¿Qué hicieron para resolverlo?
El mayor problema técnico fue definir correctamente las funciones de transición de estados, especialmente las funciones de transferencia entre jarras.
Para solucionarlo:
Analicé las restricciones de capacidad de cada jarra.
Utilicé la función min para controlar cuánto líquido se podía transferir.
Probé distintos casos manualmente hasta validar que las transiciones fueran correctas.

5. ¿Qué hicieron bien como equipo? ¿Qué se comprometen a hacer para mejorar los resultados?
Lo que hice bien:
Buena organización del desarrollo del problema.
Implementación progresiva del código (por partes).
Validación del resultado con ejemplos.

Para mejorar:
Optimizar la gestión del tiempo.
Documentar mejor el código desde el inicio.
Profundizar más en el diseño de heurísticas.

6. ¿Qué referencias usaron? ¿Cuál fue la más útil? Incluyan citas con estándares adecuados.
Russell, S., & Norvig, P. (2010). Artificial Intelligence: A Modern Approach. Prentice Hall.
Material de clase sobre algoritmos de búsqueda informada.
Documentación oficial de Haskell: https://www.haskell.org/documentation/

Referencia más útil:
El libro de Russell y Norvig fue el más útil, ya que explica de forma clara el algoritmo A* y el concepto de heurística.
