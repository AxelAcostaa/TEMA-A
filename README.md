# 🚀 Solucionario 2do Parcial JAVA - Plan 2024 (TEMA A)

Este repositorio contiene la resolución completa de los ejercicios de programación y las preguntas teóricas (Multiple Choice).

---

## 💻 PARTE 1: Ejercicios de Programación

### Ejercicio 1: Implementar Interface (Ventas)
**Archivo:** `Auto.java`
**Consigna:** Calcular precio final con depreciación (5% anual) y recargo por puertas.

```java
// Asegurate de importar esto arriba: import java.time.Year;

@Override
public double calcularPrecioFinal(double precioBase) {

    int anioActual = Year.now().getValue();
    // Asumimos que 'anio' o 'modelo' es el atributo del año de fabricación
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
