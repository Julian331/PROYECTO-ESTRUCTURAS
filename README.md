# PROYECTO-ESTRUCTURAS
📌 Definición
├─ Nodos con: Dato + Puntero anterior + Puntero siguiente
├─ Cabeza: Primer nodo (anterior = null)
├─ Cola: Último nodo (siguiente = null)

🔄 Recorrido
├─ Bidireccional: Adelante (cabeza → cola) o atrás (cola → cabeza)

⚙️ Operaciones
├─ Inserción
│ ├─ Al inicio: Actualiza cabeza y punteros vecinos
│ ├─ Al final: Usa cola para optimizar
│ └─ En medio: Reajusta anterior y siguiente de nodos adyacentes
├─ Eliminación
│ ├─ Actualiza anterior.siguiente y siguiente.anterior
│ └─ O(1) si ya tienes el nodo (vs. O(n) en lista simple)
└─ Búsqueda
├─ Desde cabeza (si el dato está cerca del inicio)
└─ Desde cola (si está cerca del final)

✅ Ventajas
├─ Recorrido en ambos sentidos
├─ Eliminación eficiente (sin recorrer toda la lista)
└─ Ideal para:
├─ Historial de navegación
├─ Funciones "Rehacer/Deshacer"
└─ Algoritmos como LRU Cache

❌ Desventajas
├─ Mayor uso de memoria (por puntero anterior)
└─ Complejidad en implementación
