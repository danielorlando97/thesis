# Dominio Almacenes

## Contextos

- Almacenes:

  Un almacén es un conjunto de productos, de los cuales se conoce un precio ponderado, un cantidad máximo, minima y actual. Para un almacen y un producto dados se define, el precio ponderado como precio actual del producto y se calcula según el contexto en el que dicho producto entra al almacen. La cantidad max y min son medidas de control de la necesidad de producto del almacen. Y la cantidad actual es la cantidad actual de producto en el almacen

  Un almacén se subdivide en otros almacén de manera jerárquica y arbolea.
  Todos los almacenes se clasifican en tres categorias, en principio no desjuntas (Almacen, Centro de Elaboración, Punto de Venta)

  El flujo de los productos entre los distintos almacenes se registran rigurosamente, y se conoce como movimientos de almacén. De los mismo se conoce la cantidad y el producto que se mueve y al menos un almacen, ya sea de origen o de destino. Dichos movimientos se distinguen según su naturaleza y concepto:

  - Entrada:
    - Carga Inicial: Proceso de configuración del estado inicial de los almacenes, autoconfirmado
    - Compra: Procesos de compra de los productos, incluye el costo del mismo y el proveedor, necesita confirmacion de un usuario superior al que lo solicita
  - Salida:
    - Venta: Proceso inherente a los "Puntos de ventas", autoconfirmado
    - Rotura o Desperdicio: Proceso de salida, necesita confirmacion de un superior
  - Transferencia:
    - Entre almacenes: Movimiento donde existen almacenes de origen y destino, necesita confirmacion del receptor de la llegada
    - Elaboración: Proceso inherente a los "Centros de Elaboración". Proceso multimovimento, con la salida de uno o mas productos del almacen entran al mismo uno o mas productos procesados, autoconfirmado.

- Contabilidad

  El libro de cuentas del centro, donde todo centro de costo (Almacenes) tienen varias cuentas (una por cada producto) y se registran los movimientos contables entre estos centros de costos, cada movimiento responde al menos dos linea del libro de cuentas. Cada una de estas lineas responden a la acreditacion o debito en cada una de las cuentas que intervienen en el movimiento contable.

  Las cuentas pueden ser de dos tipos de debito o de credito, y segun su tipo se define su comportamiento en un movimiento contable:

  - Cuentas de tipo debito:
    - Si se le debita x cantidad, la cuenta aumenta su valor en x
    - Si se le acredita x cantidad, la cuenta disminuye su valor en x
  - Cuenta de tipo credito:
    - Si se le debita x cantidad, la cuenta disminuye su valor en x
    - Si se le acredita x cantidad, la cuenta aumenta su valor en x
