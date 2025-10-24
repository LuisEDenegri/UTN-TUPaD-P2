# 🔗 TP 6 - Relaciones UML 1:N

Este repositorio contiene la **resolución del Trabajo Práctico Nº6** de la materia *Introducción a la Programación en Java*.  
El objetivo es implementar y comprender las **relaciones uno a muchos (1:N)** en UML mediante sistemas complejos.

---

## 📚 Contenido del TP

- Implementación de **relaciones 1:N** (uno a muchos) entre clases.
- Uso de **Enums** para categorías predefinidas.
- Gestión de colecciones con **ArrayList** y operaciones CRUD.
- **Composición 1:N**: El contenedor gestiona el ciclo de vida de los elementos.
- **Asociación bidireccional 1:N**: Sincronización automática entre objetos.
- Métodos de búsqueda, filtrado y reportes sobre colecciones.

---

## 📋 Ejercicios Implementados

### 1. Sistema de Stock (Enum + ArrayList)
Sistema de inventario con productos categorizados.

**Características:**
- Enum `CategoriaProducto` con 4 tipos: ALIMENTOS, ELECTRONICA, ROPA, HOGAR
- CRUD completo de productos
- Filtros por categoría y rango de precios
- Estadísticas: total de stock, producto con mayor stock

---

### 2. Biblioteca y Libros (Composición 1:N)
Gestión de biblioteca con libros y autores.

**Características:**
- Composición: `Biblioteca` crea y gestiona instancias de `Libro`
- Cada libro tiene un autor asociado
- Búsqueda por ISBN y filtrado por año
- Listado de autores únicos en la colección

---

### 3. Universidad - Profesor - Curso (Bidireccional 1:N)
Sistema universitario con profesores y cursos relacionados bidireccionalmente.

**Características:**
- **Relación bidireccional**: Profesor conoce sus cursos, Curso conoce su profesor
- Sincronización automática al asignar/eliminar relaciones
- Gestión completa: agregar, eliminar, reasignar
- Reportes de cantidad de cursos por profesor

---

## 💻 Ejemplo de Código

### Enum y Filtrado

```java
public enum CategoriaProducto {
    ALIMENTOS("Productos comestibles"),
    ELECTRONICA("Dispositivos electronicos");
    
    private final String descripcion;
    
    private CategoriaProducto(String descripcion) {
        this.descripcion = descripcion;
    }
}

// Filtrar productos por categoría
public List<Producto> filtrarPorCategoria(CategoriaProducto categoria) {
    ArrayList<Producto> res = new ArrayList<>();
    for (Producto p : productos) {
        if (p.getCategoria() == categoria) {
            res.add(p);
        }
    }
    return res;
}
```

### Composición 1:N

```java
public class Biblioteca {
    private List<Libro> libros = new ArrayList<>();
    
    // Biblioteca crea y gestiona los libros
    public void agregarLibro(String isbn, String titulo, int anio, Autor autor) {
        libros.add(new Libro(isbn, titulo, anio, autor));
    }
}
```

### Relación Bidireccional 1:N

```java
public class Profesor {
    private List<Curso> cursos = new ArrayList<>();
    
    public void agregarCurso(Curso c) {
        if (!cursos.contains(c)) {
            cursos.add(c);
            if (c.getProfesor() != this) {
                c.setProfesor(this); // Sincronización
            }
        }
    }
}

public class Curso {
    private Profesor profesor;
    
    public void setProfesor(Profesor p) {
        Profesor anterior = this.profesor;
        this.profesor = p;
        
        if (anterior != null) {
            anterior.eliminarCurso(this);
        }
        if (p != null && !p.getCursos().contains(this)) {
            p.agregarCurso(this); // Sincronización
        }
    }
}
```

---

## 🎯 Conceptos Clave

- **Relación 1:N**: Un objeto se relaciona con múltiples objetos del otro tipo.
- **Enum**: Tipo de dato para valores constantes predefinidos (ej: categorías).
- **Composición 1:N**: El contenedor crea y destruye los elementos (ciclo de vida dependiente).
- **Bidireccionalidad 1:N**: Ambos lados conocen la relación y se sincronizan automáticamente.
- **Collections**: Uso de `ArrayList` para gestionar colecciones dinámicas.

---

## 🛠️ Tecnologías

- **Estructuras**: ArrayList, Enum
- **Paradigma**: Programación Orientada a Objetos
