# 🧬 TP 7 - Herencia y Polimorfismo

Este repositorio contiene la **resolución del Trabajo Práctico Nº7** de la materia *Introducción a la Programación en Java*.  
El objetivo es implementar y comprender **herencia, clases abstractas y polimorfismo** mediante ejercicios prácticos.

---

## 📚 Contenido del TP

- Implementación de **herencia** con `extends`.
- Uso de **clases abstractas** con métodos abstractos.
- Aplicación de **polimorfismo** para tratar objetos de distintas clases de forma uniforme.
- Sobrescritura de métodos con `@Override`.
- Uso de `instanceof` para verificar tipos en tiempo de ejecución.
- Atributos y métodos `protected` para acceso en subclases.

---

## 📋 Katas Implementadas

### 1. Vehículos y Herencia Básica
Introducción a la herencia con vehículos.

**Conceptos:**
- Clase base `Vehiculo` con atributos `protected`
- Subclase `Auto` que extiende `Vehiculo`
- Polimorfismo: referencia de tipo padre apuntando a objeto hijo

---

### 2. Figuras Geométricas y Métodos Abstractos
Cálculo de áreas con clases abstractas.

**Conceptos:**
- Clase abstracta `Figura` con método abstracto `calcularArea()`
- Subclases concretas: `Circulo` y `Rectangulo`
- Cada subclase implementa su propio cálculo de área
- Array de tipo `Figura` conteniendo distintas figuras

---

### 3. Empleados y Polimorfismo
Sistema de gestión de empleados con diferentes tipos de contrato.

**Conceptos:**
- Clase abstracta `Empleado` con método abstracto `calcularSueldo()`
- `EmpleadoPlanta`: sueldo base + plus
- `EmpleadoTemporal`: valor hora × horas trabajadas
- Uso de `instanceof` para identificar tipo de empleado
- Lista polimórfica de empleados

---

### 4. Animales y Comportamiento Sobrescrito
Modelado de animales con sonidos específicos.

**Conceptos:**
- Clase concreta `Animal` con método `hacerSonido()`
- Subclases: `Perro`, `Gato`, `Vaca`
- Sobrescritura de método para comportamiento específico
- Método común `describirAnimal()` heredado sin modificar

---

## 💻 Ejemplo de Código

### Clase Abstracta y Herencia

```java
public abstract class Figura {
    protected String nombre;
    
    public Figura(String nombre) {
        this.nombre = nombre;
    }
    
    public abstract double calcularArea(); // Método abstracto
}

public class Circulo extends Figura {
    private double radio;
    
    public Circulo(double radio) {
        super("Circulo");
        this.radio = radio;
    }
    
    @Override
    public double calcularArea() {
        return Math.PI * radio * radio;
    }
}
```

### Polimorfismo

```java
// Array polimórfico
Figura[] figuras = new Figura[3];
figuras[0] = new Circulo(3.0);
figuras[1] = new Rectangulo(4.0, 5.0);
figuras[2] = new Circulo(1.5);

// Mismo código, comportamiento diferente
for (Figura f : figuras) {
    System.out.println(f.getNombre() + " Area: " + f.calcularArea());
}
```

### Sobrescritura de Métodos

```java
public class Animal {
    public void hacerSonido() {
        System.out.println("Sonido generico de animal");
    }
}

public class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Guau");
    }
}
```

### Uso de instanceof

```java
for (Empleado e : lista) {
    System.out.println("Sueldo: " + e.calcularSueldo());
    
    if (e instanceof EmpleadoPlanta) {
        System.out.println("Tipo: Planta");
    } else if (e instanceof EmpleadoTemporal) {
        System.out.println("Tipo: Temporal");
    }
}
```

---

## 🎯 Conceptos Clave

- **Herencia**: Una clase hija hereda atributos y métodos de la clase padre con `extends`.
- **Clases Abstractas**: No se pueden instanciar, definen métodos abstractos que las subclases deben implementar.
- **Polimorfismo**: Tratar objetos de diferentes clases como si fueran del mismo tipo (clase padre).
- **@Override**: Anotación que indica sobrescritura de un método heredado.
- **instanceof**: Operador para verificar si un objeto es instancia de una clase específica.
- **protected**: Modificador que permite acceso en subclases y mismo paquete.

---

## 🛠️ Tecnologías

- **Paradigma**: Programación Orientada a Objetos
- **Conceptos**: Herencia, Abstracción, Polimorfismo
