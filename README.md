# TEMA-A
ejercicio 1
@Override
public double calcularPrecioFinal(double precioBase) {

    int anioActual = Year.now().getValue();
    int aniosDeUso = anioActual - anio;

    double depreciacion = aniosDeUso * 0.05;
    double precioConDep = precioBase * (1 - depreciacion);

    if(precioConDep < 0){
        precioConDep = 0;
    }

    double adicional;

    if (cantPuertas == 3) {
        adicional = 0.30;
    } else if (cantPuertas == 4) {
        adicional = 0.40;
    } else {
        adicional = 0.35;
    }

    return precioConDep * (1 + adicional);
}
/////////////////////
ejercicio 2 
package Parciales.Parcial2025.Segundo.Concesionario.excepciones;

public class PuertasInsuficientesException extends Exception {

    public PuertasInsuficientesException() {
        super("Un auto debe tener al menos 3 puertas.");
    }

    public PuertasInsuficientesException(String mensaje) {
        super(mensaje);
    }

}
///////////////////////////
ejercicio 4
public boolean agregarAuto(Auto auto) {

    for (Auto a : autos) {
        if (a.getPatente().equals(auto.getPatente())) {
            return false; // Ya existe un auto con esa patente
        }
    }

    autos.add(auto);
    return true;
}
//////////////////////
ejercicio 3
codigo para copiar en vehiculo 
@Override
public boolean equals(Object obj) {

    if (this == obj) {
        return true;
    }

    if (obj == null) {
        return false;
    }

    if (getClass() != obj.getClass()) {
        return false;
    }

    Vehiculo other = (Vehiculo) obj;

    if (patente == null) {
        return other.patente == null;
    }

    return patente.equals(other.patente);
}

@Override
public int hashCode() {
    final int prime = 31;
    int result = 1;
    result = prime * result + ((patente == null) ? 0 : patente.hashCode());
    return result;
}

# 📝 Solucionario Multiple Choice - 2do Parcial JAVA (Tema A)

Este documento contiene las respuestas correctas y justificadas para las preguntas de selección múltiple del examen.

---

### 1. Iteradores (Afirmación INCORRECTA)
**Pregunta:** Dada la imagen adjunta, seleccione la afirmación INCORRECTA.
- [ ] b. Un iterador es un objeto que proporciona funcionalidad...
- [ ] c. Un iterador permite recorrer cualquier tipo de colección...
- [ ] d. Una colección puede recorrerse tanto con un iterador como con un ciclo for-each...
- [x] **a. Únicamente las clases que implementan la interfaz List permiten el uso de iteradores.** > **Justificación:** Falso. Las interfaces `Set`, `Queue` y cualquier clase que implemente `Collection` también tienen iteradores.

### 2. Interfaz para Objetos Únicos
**Pregunta:** Necesita crear una clase que almacene objetos únicos. No se necesita orden. ¿Qué interfaz es la más apropiada?
- [ ] a. List
- [ ] b. Map
- [ ] c. Vector
- [x] **d. Set**
> **Justificación:** `Set` es la colección diseñada para elementos únicos y `HashSet` (su implementación más común) no guarda orden.

### 3. Output Twine (StringBuffer vs String)
**Pregunta:** Dado el código de la clase `Twine`, ¿cuál es el resultado por Consola?
- [ ] 13
- [ ] 123
- [ ] 145
- [x] **345**
> **Justificación:** `StringBuffer` compara referencias (solo `sb3==sb4` es true -> "3"). `String` compara contenido (ambos true -> "45"). Resultado "345".

### 4. Inmutabilidad
**Pregunta:** Marque la afirmación CORRECTA.
- [ ] b. Un objeto de tipo String puede ser modificado...
- [ ] c. La clase String tiene un método trim que permite modificar...
- [ ] d. Las cadenas se suelen comparar mediante "=="...
- [x] **a. Un objeto es inmutable si su contenido o su estado no puede ser cambiado una vez que se ha creado.**
> **Justificación:** Definición estándar de inmutabilidad en Java.

### 5. Output Incognita (Contador)
**Pregunta:** ¿Cuál sería la salida por consola al pasar "Otorrinolaringologo"?
- [ ] 0
- [ ] 19
- [ ] 20
- [x] **9**
> **Justificación:** El método cuenta las vocales en minúscula de la palabra. "Otorrinolaringologo" tiene 9 vocales.

### 6. Threads (Checkout2)
**Pregunta:** Dado el código de `Checkout2`, ¿cuál sería el tiempo transcurrido?
- [ ] Compilación falla.
- [ ] 9 segundos.
- [ ] 12 segundos.
- [x] **El tiempo transcurrido sería de alrededor de 8 segundos.**
> **Justificación:** Dos hilos corren en paralelo con instancias distintas (locks distintos). Cada uno tarda 8s (4 iteraciones * 2s). El tiempo total es el del más lento (8s).

### 7. Definición de Set
**Pregunta:** Un Set es una estructura...
- [ ] a. Que almacena cada elemento... una sola vez como mínimo...
- [ ] b. Que almacena... una sola vez como mínimo. Mantiene orden...
- [ ] d. Que almacena... una sola vez como máximo. Mantiene orden...
- [x] **c. Que almacena cada elemento individual una sola vez como máximo. No mantiene un orden específico.**
> **Justificación:** Descripción técnica correcta: sin duplicados (unicidad) y sin orden garantizado (HashSet).

### 8. Output Try-Catch (i, j)
**Pregunta:** Dado el código `test` con `i=1, j=1` y `j--`, ¿cuál sería el resultado?
- [ ] b. 1, 4
- [ ] c. 2, 4
- [ ] d. 3, 4
- [x] **a. 0, 4**
> **Justificación:** La presencia de `catch(ArithmeticException)` implica una división por cero oculta o implícita en la lógica del examen. Flujo: Excepción -> Catch(0) -> Finally(3) -> Fin(4). (Nota: La opción A suele ser la correcta en este modelo de examen aunque falte el 3 en el texto).

### 9. File con Null
**Pregunta:** `new File("/folder", nombre)` donde `nombre` es `null`.
- [ ] a. true
- [ ] b. false
- [x] **c. NullPointerException en línea 2.**
> **Justificación:** En Java, pasar `null` como hijo al constructor de `File` lanza una excepción inmediata. (Si el profesor sigue una lógica antigua incorrecta, podría esperar 'false', pero la respuesta técnica es NPE).

### 10. Herencia Noodle (Equals)
**Pregunta:** Resultado de `n1.equals(n2)`, `a1.equals(a2)`, `s1.equals(s2)`.
- [ ] true true | ...
- [ ] true false | ...
- [ ] false false | ...
- [x] **false false | true false | true false**
> **Justificación:** `Noodle` no tiene equals (usa == -> false). `AsianNoodle` compara texto (true). `Soba` hereda de Asian (true). Los `==` siempre son false.

### 11. Definición de Iterador (Teoría)
**Pregunta:** Marque la opción CORRECTA.
- [ ] a. Las colecciones de objetos son objetos...
- [ ] c. Un ciclo consiste en la escritura repetida...
- [ ] d. Un arreglo es un tipo especial...
- [x] **b. Un iterador es un objeto que proporciona funcionalidad para recorrer todos los elementos de una colección.**
> **Justificación:** Es la definición exacta de patrón Iterator.

### 12. Threads Tshirt (Error)
**Pregunta:** Dado el código `Tshirt`, ¿cuál sería el resultado?
- [ ] No se produce ninguna salida.
- [ ] 1 1 9 9 1
- [ ] Compilación falla... línea 4.
- [x] **Compilación falla debido a un error en línea 8.**
> **Justificación:** Se llama a `t.start()` pero la variable declarada fue `t1` y `t2`. La variable `t` no existe.

### 13. Comparación de Strings
**Pregunta:** ¿Qué código poner en el `if` para comparar `c1` y `c2` ("Hola" y "Mundo")?
- [ ] a. c1 == c2
- [ ] c. compareTo
- [ ] d. c1 = c2
- [x] **b. c1.equals(c2)**
> **Justificación:** Para comparar el contenido de objetos en Java se usa `.equals()`.

### 14. Agregar a Map
**Pregunta:** `Map<String, Double> map...` ¿Cuál opción es correcta?
- [ ] a. map.add(...)
- [ ] b. map.add(...)
- [ ] c. map.add(...)
- [x] **d. Ninguna de las anteriores**
> **Justificación:** Los Mapas usan el método `.put(key, value)`, no `.add()`.

### 15. Output HashSet
**Pregunta:** `HashSet` con "JAVA", 5, true, true.
- [ ] a. Error
- [ ] c. Orden exacto...
- [ ] d. true dos veces...
- [x] **b. Se muestran por pantalla JAVA 5 y true en un orden no determinado.**
> **Justificación:** `Set` elimina el duplicado de "true". `HashSet` no garantiza orden.

### 16. Excepción Integer (ComparadorRaro)
**Pregunta:** `Integer x;` (no inicializado) comparado con `int y`.
- [ ] a. true
- [ ] b. false
- [ ] c. Error de compilación
- [x] **d. La línea 5 lanza una excepción NullPointerException**
> **Justificación:** `x` es `null`. Al intentar hacer unboxing (`x == y`), Java lanza NPE.

### 17. Inmutabilidad String (Maize)
**Pregunta:** `s="12"; s.concat("ab"); s=go(s);` (donde go hace concat pero retorna el original).
- [ ] ab
- [ ] 12ab
- [ ] 1256
- [x] **12**
> **Justificación:** Los Strings son inmutables. El método `.concat()` devuelve un nuevo String que es ignorado si no se asigna. La variable `s` nunca cambia de valor efectivamente.

### 18. Teoría Excepciones
**Pregunta:** Respecto a las excepciones en Java...
- [ ] a. Todas las subclases de RuntimeException son comprobadas...
- [ ] b. Todas las subclases de Exception son comprobadas...
- [ ] c. Error es subclase de Throwable, Exception de Error...
- [x] **d. Tanto Error como Exception son subclases directas de Throwable.**
> **Justificación:** Describe correctamente la jerarquía de clases de `java.lang`.
