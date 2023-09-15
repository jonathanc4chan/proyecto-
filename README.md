# proyecto-
+---------------------------------+
|           Fabrica               |
+---------------------------------+
| +create() : void                |
+---------------------------------+
        ^
        |
        | 
        |
+---------------------------------+
|            silla               |
+---------------------------------+
| -estilo : String               |
| -color : String                |
| -material : String             |
+---------------------------------+
| +silla(estilo: String,         |
|        color: String,          |
|        material: String)       |
| +create() : void               |
+---------------------------------+
        ^
        |
        | 
        |
+---------------------------------+
|            mesas               |
+---------------------------------+
| -estilo : String               |
| -color : String                |
| -material : String             |
+---------------------------------+
| +mesa(estilo: String,          |
|        color: String,          |
|        material: String)       |
| +create() : void               |
+---------------------------------+

+---------------------------------+
|             venta               |
+---------------------------------+
| -nombre producto : String      |
| -precio : double               |
| -fecha de entrega : String     |
| -nombre de cliente : String    |
| -nit : String                  |
| -numero de venta : String      |
+---------------------------------+
| +venta(nombre de producto:stirn|
|       precio: double,          |
|   fecha de entrega: String,    |
|    nombre de cliente: String,  |
|       nit: String,             |
|   numero de venta: String)     |
| +mostrar info ventas() : void  |
+---------------------------------+

+---------------------------------+
|     fabrica de muebles           |
+---------------------------------+
| +crear muebles(estilo: String,  |
|                  color: String, |
|                material: String)|
+---------------------------------+
        ^
        |
        | 
        |
+---------------------------------+
|        silla fabrica             |
+---------------------------------+
| +crear muebles  (estilo: String, |
|                  color: String,  |
|                 material: String)|
+---------------------------------+
        ^
        |
        | 
        |
+---------------------------------+
|        mesa fabrica             |
+---------------------------------+
| +crearmuebles(estilo  : String, |
|                  color: String, |
|                material: String)|
+---------------------------------+
