# Trabajo Práctico - POO: Sistema de Empleados

## Descripción
Implementación de un sistema de gestión de empleados aplicando conceptos de Programación Orientada a Objetos en Java.

## Clase Empleado

### Atributos
- `id`, `nombre`, `puesto`, `salario`
- `totalEmpleados` (static) - contador de empleados

### Constructores
```java
Empleado(int id, String nombre, String puesto, double salario)
Empleado(String nombre, String puesto)  // Salario default: $100,000
```
### Métodos Principales
- actualizarSalario(double porcentaje) - aumento porcentual

- actualizarSalario(int aumentoFijo) - aumento fijo

- mostrarTotalEmpleados() - método estático

- toString() - muestra información del empleado

---
### Conceptos POO Aplicados
- Encapsulamiento

- Sobrecarga de métodos

- Variables y métodos estáticos

- Múltiples constructores

---

### Salida Esperada
ID: 1 | Nombre: Luis Denegri | Puesto: Desarrollador | Salario: $165000.0
Total de empleados: 2
