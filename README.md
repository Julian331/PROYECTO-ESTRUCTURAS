# PROYECTO-ESTRUCTURAS
# Listas Enlazadas - Mapa Conceptual

## **Lista Enlazada Simple**
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

## **Lista Doblemente Enlazada**
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

## **Lista Circular**
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

## **Comparativa General**
| **Criterio**       | **Simple** | **Doble**       | **Circular**      |
|--------------------|------------|-----------------|-------------------|
| Dirección          | Unidireccional | Bidireccional | Uni/Bidireccional |
| Memoria            | Baja        | Alta            | Media/Alta        |
| Inserción inicio   | O(1)       | O(1)           | O(1)             |
| Eliminación final  | O(n)       | O(1)           | O(1)*            |
| Casos de uso       | Pilas, colas | Historiales, cachés | Buffers, scheduling |

*(*) Depende de si es simple o doble circular.*
--------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------

# Pilas 

## **Concepto General**
- **LIFO**: Last In, First Out (Último en entrar, primero en salir).
- **Operaciones clave**:
  - `Push`: Insertar un elemento.
  - `Pop`: Eliminar el último elemento insertado.
  - `Peek/Top`: Ver el tope sin eliminarlo.
  - `isEmpty`: Verificar si está vacía.

---

## **Pila Implementada con Lista Enlazada**
### **Estructura**
- **Nodos** con:
  - `Dato` (valor almacenado).
  - `Puntero` al siguiente nodo (o `null` si es el último).
- **Tope**: Apunta al nodo más reciente (cabeza de la lista).

### **Características**
- **Dinámica**: Tamaño flexible (crece o reduce según elementos).
- **Sin límite máximo** (excepto por memoria disponible).
- **Operaciones**:
  - `Push`: O(1) (inserta al inicio).
  - `Pop`: O(1) (elimina el primer nodo).
  - `Peek`: O(1).

### **Ventajas**
- No desperdicia memoria (solo usa lo necesario).
- Ideal cuando el tamaño es impredecible.

### **Desventajas**
- Mayor overhead por almacenar punteros.
- Acceso secuencial (no aleatorio).

---

## **Pila Implementada con Arreglo (Array)**
### **Estructura**
- **Arreglo estático/dinámico** con tamaño fijo o redimensionable.
- **Índice `tope`** que apunta al último elemento insertado.

### **Características**
- **Tamaño fijo** (en implementación estática) o redimensionable (dinámico).
- **Operaciones**:
  - `Push`: O(1) (si hay espacio) o O(n) si se redimensiona.
  - `Pop`: O(1).
  - `Peek`: O(1).

### **Ventajas**
- Acceso rápido y predecible (uso de memoria contigua).
- Menos overhead (sin punteros).

### **Desventajas**
- **Desperdicio de memoria** si el arreglo está subutilizado.
- **Overflow** en arreglos estáticos (tamaño fijo).

---

## **Comparativa: Lista vs. Arreglo**
| **Criterio**       | **Lista Enlazada**         | **Arreglo**               |
|--------------------|----------------------------|---------------------------|
| **Tamaño**         | Dinámico (sin límite)      | Fijo/Redimensionable      |
| **Memoria**        | Overhead por punteros      | Compacta (contigua)       |
| **Push/Pop**       | O(1) siempre               | O(1) (O(n) si redimensiona)|
| **Uso de memoria** | Eficiente (sin desperdicio)| Puede haber desperdicio   |
| **Acceso**         | Secuencial                 | Aleatorio (índices)       |

---

## **Aplicaciones Comunes**
- **Ejemplos con listas**: 
  - Gestión de memoria en lenguajes (call stack).
  - Undo/Redo en editores de texto (cuando el historial es grande).
- **Ejemplos con arreglos**:
  - Evaluación de expresiones (notación postfija).
  - Algoritmos recursivos (simulación de call stack).

---

## **Consideraciones**
- **Lista**: Mejor para tamaños variables y memoria limitada.
- **Arreglo**: Mejor para tamaños predecibles y velocidad crítica.

--------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------

# Colas 

## **Concepto General**
- **FIFO**: First In, First Out (Primero en entrar, primero en salir).
- **Operaciones clave**:
  - `Enqueue`: Insertar un elemento al final.
  - `Dequeue`: Eliminar el elemento al frente.
  - `Front/Peek`: Ver el primer elemento sin eliminarlo.
  - `isEmpty`: Verificar si está vacía.

---

## **Cola Simple**
### **Estructura**
- **Lineal**: Secuencia de elementos en orden de llegada.
- **Punteros**:
  - `Frente` (apunta al primer elemento).
  - `Final` (apunta al último elemento).

### **Características**
- **Inserción (`Enqueue`)**: Al final (O(1) en lista, O(1)* en arreglo).
- **Eliminación (`Dequeue`)**: Al frente (O(1) en lista, O(n) en arreglo por desplazamiento).
- **Tamaño**: Dinámico (lista) o fijo (arreglo).

### **Ventajas**
- Simple y intuitiva.
- Eficiente para procesos secuenciales.

### **Desventajas**
- En arreglos: Desperdicio de espacio ("cola hueca" tras `Dequeue`).

---

## **Cola Circular**
### **Estructura**
- **Arreglo circular**: Reutiliza espacios vacíos tras `Dequeue`.
- **Punteros**:
  - `Frente` y `Final` se "envuelven" al llegar al límite del arreglo.

### **Características**
- **Tamaño fijo** pero eficiente en memoria.
- **Inserción/Eliminación**: O(1) (sin desplazamientos).
- **Full/Empty**: Se manejan con condiciones:
  - `(Final + 1) % tamaño == Frente` → Llena.
  - `Frente == Final` → Vacía.

### **Ventajas**
- Evita desperdicio de memoria en arreglos.
- Ideal para buffers y scheduling.

### **Desventajas**
- Tamaño fijo (no dinámico).

---

## **Cola de Prioridad**
### **Estructura**
- **Elementos con prioridad**: Se ordenan al insertar.
- **Implementaciones comunes**:
  - **Heap** (arreglo): Prioridad alta siempre al frente.
  - **Lista ordenada**: Inserción O(n), acceso O(1).

### **Características**
- **`Enqueue`**: O(log n) en heap, O(n) en lista.
- **`Dequeue`**: O(log n) en heap (reordenar), O(1) en lista.
- **Prioridad**: Mínima o máxima (ej: hospitales, sistemas operativos).

### **Ventajas**
- Gestión eficiente de tareas prioritarias.
- Flexibilidad en criterios de orden.

### **Desventajas**
- Mayor complejidad operacional.

---

## **Comparativa General**
| **Criterio**       | **Cola Simple** | **Cola Circular** | **Cola de Prioridad** |
|--------------------|-----------------|-------------------|-----------------------|
| **Estructura**     | Lineal          | Arreglo circular  | Heap/Lista ordenada   |
| **Tamaño**         | Dinámico/Fijo   | Fijo              | Dinámico              |
| `Enqueue`          | O(1)*           | O(1)              | O(log n) o O(n)       |
| `Dequeue`          | O(1) o O(n)     | O(1)              | O(log n) o O(1)       |
| **Uso de memoria** | Ineficiente*    | Eficiente         | Variable              |
| **Caso de uso**    | Procesos FIFO   | Buffers           | Scheduling, emergencias |

*(*) Depende de si se usa lista o arreglo.*

---

## **Aplicaciones Prácticas**
- **Cola Simple**: Impresión de documentos, atención al cliente.
- **Cola Circular**: Almacenamiento en buffers (audio/video).
- **Cola de Prioridad**: 
  - Sistemas operativos (planificación de procesos).
  - Servicios de emergencia (triaje).
