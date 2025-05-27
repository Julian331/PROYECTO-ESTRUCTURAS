# PROYECTO-ESTRUCTURAS
# Listas Enlazadas - Mapa Conceptual

## 📌 **Lista Enlazada Simple**
### **Estructura**
- Nodos con:
  - **Dato** (valor).
  - **Puntero** (solo al siguiente nodo).
- Último nodo apunta a `null`.

### **Características**
- **Recorrido unidireccional** (solo hacia adelante).
- **Inserción/Eliminación rápida** al inicio (O(1)).
- **Búsqueda/Acceso secuencial** (O(n)).

### **Ventajas**
- Memoria eficiente (solo 1 puntero por nodo).
- Simple implementación.

### **Desventajas**
- No puede retroceder.
- Eliminar nodos requiere recorrido previo.

---

## 🔄 **Lista Doblemente Enlazada**
### **Estructura**
- Nodos con:
  - **Dato**.
  - **Puntero anterior**.
  - **Puntero siguiente**.
- Extremos: `cabeza.anterior = null` y `cola.siguiente = null`.

### **Características**
- **Recorrido bidireccional** (adelante/atrás).
- **Inserción/Eliminación eficiente** en extremos (O(1)).
- **Búsqueda optimizada** (desde cabeza o cola).

### **Ventajas**
- Mayor flexibilidad para operaciones.
- Eliminación sin recorrido previo.

### **Desventajas**
- Mayor uso de memoria (2 punteros por nodo).
- Complejidad en mantenimiento de punteros.

---

## 🔁 **Lista Circular**
### **Tipos**
1. **Simple Circular**: 
   - Último nodo apunta al primero.
2. **Doble Circular**: 
   - `cabeza.anterior = cola` y `cola.siguiente = cabeza`.

### **Características**
- **Sin `null`** en punteros (ciclo infinito).
- **Recorrido circular** (útil para buffers o rondas).

### **Ventajas**
- Fácil rotación de elementos.
- Útil para algoritmos repetitivos.

### **Desventajas**
- Riesgo de bucles infinitos.
- Complejidad en operaciones de inserción.

---

## 🔍 **Comparativa General**
| **Criterio**       | **Simple** | **Doble**       | **Circular**      |
|--------------------|------------|-----------------|-------------------|
| Dirección          | Unidireccional | Bidireccional | Uni/Bidireccional |
| Memoria            | Baja        | Alta            | Media/Alta        |
| Inserción inicio   | O(1)       | O(1)           | O(1)             |
| Eliminación final  | O(n)       | O(1)           | O(1)*            |
| Casos de uso       | Pilas, colas | Historiales, cachés | Buffers, scheduling |

*(*) Depende de si es simple o doble circular.*
