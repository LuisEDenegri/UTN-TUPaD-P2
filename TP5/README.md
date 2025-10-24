# 🔗 TP 5 - Relaciones UML 1:1

Este repositorio contiene la **resolución del Trabajo Práctico Nº5** de la materia *Introducción a la Programación en Java*.  
El objetivo es implementar y comprender las **relaciones uno a uno (1:1)** en UML a través de ejercicios prácticos.

---

## 📚 Contenido del TP

- Implementación de **relaciones bidireccionales** entre clases.
- Uso de **composición** para objetos dependientes.
- Sincronización automática para evitar inconsistencias.
- Modelado de sistemas del mundo real con asociaciones 1:1.

---

## 📋 Ejercicios Implementados

1. **Pasaporte - Foto - Titular**
2. **Celular - Batería - Usuario**
3. **Libro - Autor - Editorial**
4. **TarjetaDeCredito - Cliente - Banco**
5. **Computadora - PlacaMadre - Propietario**
6. **Reserva - Cliente - Mesa**
7. **Vehículo - Motor - Conductor**
8. **Documento - FirmaDigital - Usuario**
9. **CitaMédica - Paciente - Profesional**
10. **CuentaBancaria - ClaveSeguridad - Titular**
11. **Reproductor - Canción - Artista**
12. **Impuesto - Contribuyente - Calculadora**
13. **GeneradorQR - Usuario - CodigoQR**
14. **EditorVideo - Proyecto - Render**

---

## 💻 Ejemplo de Código

### Relación Bidireccional

```java
public class Titular {
    private Pasaporte pasaporte;
    
    public void setPasaporte(Pasaporte pasaporte) {
        this.pasaporte = pasaporte;
        if (pasaporte != null && pasaporte.getTitular() != this) {
            pasaporte.setTitular(this);
        }
    }
}

public class Pasaporte {
    private Titular titular;
    private Foto foto; // Composición
    
    public void setTitular(Titular titular) {
        this.titular = titular;
        if (titular != null && titular.getPasaporte() != this) {
            titular.setPasaporte(this);
        }
    }
}
```

### Uso

```java
Titular titular = new Titular("Juan Pérez", "12345678");
Pasaporte pasaporte = new Pasaporte("ARG123456", "2024-01-15", "foto.jpg", "JPG");
titular.setPasaporte(pasaporte); // Sincronización automática
```

---

## 🎯 Conceptos Clave

- **Asociación 1:1**: Cada objeto se relaciona con exactamente uno del otro tipo.
- **Bidireccionalidad**: Ambos objetos se conocen y sincronizan automáticamente.
- **Composición**: El objeto contenido no existe sin su contenedor.

---

## 🛠️ Tecnologías

- **Paradigma**: Programación Orientada a Objetos
