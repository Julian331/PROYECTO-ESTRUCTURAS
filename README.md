# PROYECTO-ESTRUCTURAS

# Listas Doblemente Enlazadas

## **Concepto Básico**  
Estructura de datos lineal donde:  
- Cada **nodo** contiene:  
  - Un **valor** (dato).  
  - Un **enlace al nodo anterior**.  
  - Un **enlace al nodo siguiente**.  
- La lista tiene dos extremos:  
  - **Cabeza**: Primer nodo (su `anterior` es `null`).  
  - **Cola**: Último nodo (su `siguiente` es `null`).  

**Representación visual**:  
null ⇄ [5] ⇄ [8] ⇄ [3] ⇄ null


---

## **Características **  
1. **Recorrido bidireccional**:  
   - Se puede iterar desde la cabeza hacia adelante.  
   - O desde la cola hacia atrás.  
2. **Dinamismo**:  
   - Crece o reduce su tamaño durante la ejecución.  
3. **Complejidad de operaciones**:  
   - Inserción/eliminación en extremos: *O(1)*.  
   - Búsqueda: *O(n)* (como en listas simples).  

---

## **Operaciones **  

### **Inserción**  
- **Al inicio**:  
  - Se crea un nuevo nodo cuyo `siguiente` apunta a la antigua cabeza.  
  - La antigua cabeza ahora apunta al nuevo nodo como su `anterior`.  
- **Al final**: Similar, pero trabajando con la cola.  
- **En medio**: Requiere ajustar 4 punteros:  
  - `anterior` y `siguiente` del nuevo nodo.  
  - `siguiente` del nodo previo y `anterior` del nodo siguiente.  

### **Eliminación**  
- Se actualizan los punteros de los nodos vecinos para "saltar" el nodo eliminado.  
- **Ventaja clave**: No es necesario recorrer desde el inicio para eliminar (a diferencia de las listas simples).  

### **Búsqueda**  
- Se recorre desde la cabeza o cola hasta encontrar el valor.  

---

## **Comparación con Listas Simples**  

| **Aspecto**       | **Lista Simple** | **Lista Doble** |  
|--------------------|------------------|-----------------|  
| **Memoria**        | Menor            | Mayor (por puntero extra) |  
| **Recorrido**      | Solo adelante    | Bidireccional   |  
| **Eliminación**    | O(n)*            | O(1) si se conoce el nodo |  
| **Flexibilidad**   | Limitada         | Alta            |  

*En listas simples, eliminar requiere buscar el nodo anterior.  

---

## **Ventajas**  
1. **Eficiencia en operaciones de extremos**.  
2. **Historial de acciones**: Ideal para "rehacer/deshacer" (ej: editores de texto).  
3. **Navegación flexible**: Aplicaciones como galerías o reproductores de música.  

---

## **Desventajas**  
1. **Mayor consumo de memoria** (por el puntero adicional).  
2. **Implementación más compleja** (manejo de 2 punteros por nodo).  

---

## **Aplicaciones Prácticas**  
1. **Navegadores web**: Historial de páginas visitadas.  
2. **Sistemas de caché**: Como el algoritmo LRU.  
3. **Editores gráficos**: Pilas de acciones para revertir cambios.  

**---**
# Lista Doblemente Enlazada - Teoría

## 📌 Definición
Estructura de datos compuesta por nodos interconectados donde cada uno contiene:
- **Dato**: Información almacenada
- **Anterior**: Referencia al nodo previo
- **Siguiente**: Referencia al nodo posterior

**Analogía**: Como un tren de vagones con puertas en ambos extremos

## 🔍 Estructura Básica
[Anterior] ← [Dato] → [Siguiente]
**Caso especial**:
- Primer nodo: `Anterior = null`
- Último nodo: `Siguiente = null`

## ⚙️ Operaciones Fundamentales

### Inserción
1. **Al inicio**:
   - Nuevo nodo apunta a la antigua cabeza
   - Antigua cabeza apunta al nuevo nodo como anterior

2. **Al final**:
   - Último nodo apunta al nuevo
   - Nuevo nodo apunta al anterior último

3. **En posición intermedia**:
   - Requiere ajustar 4 conexiones
   - Dos en el nuevo nodo
   - Dos en los nodos adyacentes

### Eliminación
1. **Por valor**:
   - Buscar el nodo
   - Reconfigurar conexiones de nodos vecinos
   - Eliminar referencias al nodo borrado

2. **Por posición**:
   - Recorrer hasta la posición
   - Mismo proceso de reconfiguración

### Búsqueda
- **Secuencial**: Desde cabeza o cola
- **Mejor caso**: O(1) si está en extremos
- **Peor caso**: O(n) si no existe

## 🔄 Recorrido
- **Hacia adelante**: Desde cabeza
- **Hacia atrás**: Desde cola
- **Puede detenerse** en cualquier punto

## 📊 Comparación de Complejidades
| Operación        | Lista Simple | Lista Doble |
|------------------|--------------|-------------|
| Inserción inicio | O(1)         | O(1)        |
| Eliminación      | O(n)         | O(1)*       |
| Búsqueda         | O(n)         | O(n)        |
| Memoria          | +1 puntero   | +2 punteros |

*Cuando se tiene referencia directa al nodo

## 🏆 Ventajas Clave
1. Navegación bidireccional
2. Eliminación eficiente
3. Mayor flexibilidad en operaciones
4. Ideal para historiales y sistemas de caché

## ⚠️ Limitaciones
1. Mayor consumo de memoria (33% más)
2. Operaciones más complejas de implementar
3. Sobrecarga en mantenimiento de punteros

## 🌍 Aplicaciones Prácticas
1. **Sistemas de navegación**:
   - Historial web (adelante/atrás)
   - Galerías de imágenes

2. **Editores**:
   - Funciones deshacer/rehacer
   - Control de cambios

3. **Sistemas operativos**:
   - Administración de memoria
   - Colas de procesos

## 🖼️ Ejemplo Visual
**Estado inicial**:
null ← [A] ↔ [B] ↔ [C] → null


**Después de insertar [X] entre [A] y [B]**:
null ← [A] ↔ [X] ↔ [B] ↔ [C] → null


**Eliminar [X]**:
null ← [A] ↔ [B] ↔ [C] → null


## 💡 Conceptos Relacionados
1. **Listas circulares dobles**: Último nodo enlaza al primero
2. **Nodos centinelas**: Nodos ficticios para simplificar operaciones
3. **Listas multi-enlazadas**: Múltiples punteros por nodo

## 📚 Para Recordar
1. Cada operación debe mantener la integridad de los punteros
2. Siempre verificar casos extremos (lista vacía, un solo nodo)
3. El manejo de memoria es crucial en lenguajes de bajo nivel
