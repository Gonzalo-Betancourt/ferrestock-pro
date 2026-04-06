# Modelo de Datos Principal

El modelo de datos refleja de manera digital el sistema de ordenamiento físico existente en la ferretería de barrio.

## Entidades Principales

**1. Estanteria**
Representa el mueble, rack, pasillo o cajonera física donde se ubican los productos.
- `id` (PK)
- `nombre_identificador` (ej. "Pasillo Tornillos" o "Cajonera Principal")
- `filas` (cantidad de niveles de altura de la estantería)
- `columnas` (cantidad de divisiones horizontales por nivel)

**2. Producto**
Representa el artículo o familia de artículos de la ferretería.
- `id` (PK)
- `nombre_descriptivo` (ej. "Clavo de 2.5 pulgadas", "Bisagra pequeña")
- `visual_id` / `icono` (ruta, color o representación iconográfica crítica para el reconocimiento)
- `stock_actual` (Cantidad presente)
- `stock_minimo` (Límite visual para alerta en semáforo)

**3. Coordenadas**
Pivote que asocia un Producto con una Estantería para determinar su ubicación espacial real.
- `id` (PK)
- `estanteria_id` (FK -> Estanteria)
- `producto_id` (FK -> Producto)
- `fila_posicion` (Posición vertical X dentro de la estantería)
- `columna_posicion` (Posición horizontal Y dentro de la estantería)
