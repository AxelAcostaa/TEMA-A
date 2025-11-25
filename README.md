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
# 📚 Solucionario 2do Parcial JAVA - Plan 2024

### 🛠️ Ejercicios de Programación

1. **Ejercicio: Agregar Elemento (Inventario)**
   - **Clase:** `Inventario`
   - **Método:** `agregarAuto(Auto auto)`
   - **Lógica:** Iterar la lista `autos`. Si `a.getPatente().equals(auto.getPatente())`, retornar `false`. Si termina el bucle, hacer `autos.add(auto)` y retornar `true`.

2. **Ejercicio: Excepción Personalizada**
   - **Clase:** `PuertasInsuficientesException`
   - **Herencia:** `extends Exception` (para ser Checked).
   - **Constructores:** Uno vacío (`super("mensaje default")`) y uno con String (`super(mensaje)`).

3. **Ejercicio: Analizar Igualdad (Equals/HashCode)**
   - **Clase:** `Vehiculo`
   - **Lógica Equals:** Comparar `this == obj`, `obj == null`, `getClass() != obj.getClass()`. Castear y retornar `this.patente.equals(other.patente)`.
   - **Lógica HashCode:** Usar primo 31 y el hash de la patente.

4. **Ejercicio: Implementar Interface (Ventas)**
   - **Clase:** `Auto`
   - **Método:** `calcularPrecioFinal(double precioBase)`
   - **Lógica:**
     1. `aniosUso = Year.now().getValue() - this.anio;`
     2. `depreciacion = aniosUso * 0.05;`
     3. `precio = precioBase * (1 - depreciacion);`
     4. `if (puertas == 3) adic = 0.30; else if (puertas == 4) adic = 0.40; else adic = 0.35;`
     5. `return precio * (1 + adic);`

---

### ✅ Respuestas Multiple Choice (Validado)

| Tema | Pregunta Clave | Respuesta Correcta | Por qué (Anti-Trampa) |
| :--- | :--- | :--- | :--- |
| **Excepciones** | `ComparadorRaro` (Integer x no inic.) | **d. La línea 5 lanza NullPointerException** | `x` es null. Al hacer unboxing (`x == y`), explota. |
| **Strings** | `Maize` (s.concat) | **12** | Los Strings son inmutables. Los `concat` no se asignan. |
| **Excepciones** | Afirmación Correcta sobre Throwable | **d. Tanto Error como Exception son subclases directas de Throwable** | Jerarquía básica de Java. |
| **Colecciones** | `HashSet` output (JAVA, 5, true) | **b. Se muestran... en un orden no determinado** | `Set` elimina duplicados y `HashSet` no tiene orden. |
| **Strings** | Comparar c1 y c2 | **b. c1.equals(c2)** | Objetos se comparan con `equals`, no `==`. |
| **Map** | Agregar a un Map (`map.add`) | **d. Ninguna de las anteriores** | Los Maps usan `.put()`, no `.add()`. |
| **Colecciones** | Definición de `Set` | **c. Almacena... una sola vez como máximo. No mantiene orden.** | Definición exacta. |
| **IO Files** | `new File(..., null)` | **c. NullPointerException en línea 2** | (O `false` si el profe usa lógica antigua, pero técnicamente explota). |
| **Threads** | `Checkout2` (Tiempo transcurrido) | **8 segundos** | Hilos paralelos con locks distintos. Tiempo del más lento. |
| **Herencia** | `Noodle` / `AsianNoodle` | **false false \| true false \| true false** | `Noodle` usa `==` (false). `Asian` usa `equals` (true). |
| **Hilos** | `Tshirt` (t.start) | **Compilación falla... línea 8** | Variable `t` no existe (son `t1` y `t2`). |
| **Strings** | `Twine` (StringBuffer vs String) | **345** | `StringBuffer` compara referencias (false). `String` compara contenido (true). |
| **Sintaxis** | `try-catch` con `if(i==j)` | **3, 4** (o **0, 4** si hay div/0 implícito) | `2==0` es falso. Si no hay error oculto, imprime finally y fin. Si hay div/0, imprime catch. |


