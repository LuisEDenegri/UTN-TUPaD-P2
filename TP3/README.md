# Programación II - Trabajo Práctico 3: Introducción a la POO

Este repositorio contiene la resolución del **Trabajo Práctico N°3** de la materia **Programación II**, centrado en la **Introducción a la Programación Orientada a Objetos (POO)**. Incluye la implementación de cinco clases en Java que modelan distintos tipos de entidades con sus respectivos atributos y comportamientos.

---

## 📁 Estructura del Proyecto

El proyecto está compuesto por las siguientes clases:

### 1. **`Estudiante`**
Representa a un estudiante con información personal y académica.
- **Atributos**: nombre, apellido, curso, calificación
- **Métodos**: 
  - `mostrarInfo()`
  - `subirCalificacion(double puntos)`
  - `bajarCalificacion(double puntos)`

### 2. **`Mascota`**
Modela una mascota con datos básicos.
- **Atributos**: nombre, especie, edad
- **Métodos**:
  - `mostrarInfo()`
  - `cumplirAnios()`

### 3. **`Libro`**
Representa un libro con validación en el año de publicación.
- **Atributos**: título, autor, año de publicación
- **Métodos**:
  - `getTitulo()`, `getAutor()`, `getAnioPublication()`
  - `setAnioPublication(int anioPublication)`
  - `mostrarInfo()`

### 4. **`Gallina`**
Simula el comportamiento de una gallina en una granja.
- **Atributos**: idGallina, edad, huevosPuestos
- **Métodos**:
  - `ponerHuevo()`
  - `envejecer()`
  - `mostrarEstado()`

### 5. **`NaveEspacial`**
Modela una nave espacial con gestión de combustible.
- **Atributos**: nombre, combustible, limiteCombustible
- **Métodos**:
  - `despegar()`
  - `avanzar(double distancia)`
  - `recargarCombustible(double cantidad)`
  - `mostrarEstado()`
