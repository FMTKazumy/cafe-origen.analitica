BITACORA Mini reto 1 | Semana 1 | día 1 | 20/11/2026

**Diccionario de datos (ventas):**
Cada registro del arreglo ventas representa una venta individual con 7 propiedades:
- id (number): Número identificador único de la venta (del 1 al 12).
- fecha (string): Fecha en que se hizo la venta en formato "AAAA-MM-DD".
- cliente (string): Código que identifica al cliente (ej. "C01", "C02").
- producto (string): Nombre del café o accesorio vendido con su presentación.
- ciudad (string): Ciudad donde se realizó la compra.
- cantidad (number): Cantidad de unidades vendidas en esa factura.
- precio (number): Valor unitario de cada producto en pesos (sin puntos ni comas).

**Casos borde detectados en los datos:**
1. Ciudad escrita en minúscula en el registro id 5 ("medellín" en vez de "Medellín"):
   - Decisión: Antes de filtrar o agrupar por ciudad, convertir los textos con .toLowerCase() (o unificar la primera letra en mayúscula) para que el programa no cuente "Medellín" y "medellín" como dos ciudades diferentes.

2. Venta con cantidad 0 en el registro id 8 ("Origen Huila 500 g", cantidad: 0):
   - Decisión: Tenerlo en cuenta al calcular totales o promedios; si se buscan ventas reales, filtrar que cantidad > 0 para que una compra en 0 no afecte los conteos.

3. Clientes y productos repetidos en varias filas (ej. el cliente "C01" aparece 3 veces y "Origen Huila 500 g" aparece 4 veces):
   - Decisión: No contar el largo del arreglo (.length) como si fueran clientes o productos únicos; usar estructuras para agrupar o evitar duplicados cuando se pidan totales por cliente o producto.

4. Índices de JavaScript vs posición humana:
   - Decisión: Como en JS los arreglos arrancan en 0, el primer elemento es ventas[0], el último es ventas[ventas.length - 1] y el cuarto registro de la tabla está en ventas[3].
    