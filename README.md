# PROYECTO-ESTRUCTURAS

# Listas Doblemente Enlazadas
# Listas Doblemente Enlazadas  
*(Exposición Teórica)*  

---

## 🌐 **Concepto Básico**  
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

## 🔄 **Características Clave**  
1. **Recorrido bidireccional**:  
   - Se puede iterar desde la cabeza hacia adelante.  
   - O desde la cola hacia atrás.  
2. **Dinamismo**:  
   - Crece o reduce su tamaño durante la ejecución.  
3. **Complejidad de operaciones**:  
   - Inserción/eliminación en extremos: *O(1)*.  
   - Búsqueda: *O(n)* (como en listas simples).  

---

## ⚙️ **Operaciones Principales**  

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

## 📊 **Comparación con Listas Simples**  

| **Aspecto**       | **Lista Simple** | **Lista Doble** |  
|--------------------|------------------|-----------------|  
| **Memoria**        | Menor            | Mayor (por puntero extra) |  
| **Recorrido**      | Solo adelante    | Bidireccional   |  
| **Eliminación**    | O(n)*            | O(1) si se conoce el nodo |  
| **Flexibilidad**   | Limitada         | Alta            |  

*En listas simples, eliminar requiere buscar el nodo anterior.  

---

## 🏆 **Ventajas**  
1. **Eficiencia en operaciones de extremos**.  
2. **Historial de acciones**: Ideal para "rehacer/deshacer" (ej: editores de texto).  
3. **Navegación flexible**: Aplicaciones como galerías o reproductores de música.  

---

## ⚠️ **Desventajas**  
1. **Mayor consumo de memoria** (por el puntero adicional).  
2. **Implementación más compleja** (manejo de 2 punteros por nodo).  

---

## 🎯 **Aplicaciones Prácticas**  
1. **Navegadores web**: Historial de páginas visitadas.  
2. **Sistemas de caché**: Como el algoritmo LRU.  
3. **Editores gráficos**: Pilas de acciones para revertir cambios.  

---
