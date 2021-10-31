# Dominio e-commerce

## Contextos

- Tienda:
  Cada vendedor tiene una tienda en la cual expone sus productos a la venta, el vendedor tiene el control sobre el precio, la disponibilidad y/o visivilidad de sus productos y solo ellos. Este tiene una cantidad X de un producto P donde X es la disponibilidad de ese producto, tambien puede decidir si parar de vender el producto quitandole visibilidad
  Si se quiere parar de vender o `eliminar visibilidad` existen 3 formas:

  - Parar de vender (soft): Se elimina la visibilidad del producto para los compradores nuevos pero se mantiene en las wishlist de los usuarios que agregaron el producto a su lista en un tiempo menor a T. Ademas se mantienen todas las reservas asociadas a compras en estado `pending`

  - Parar de vender (medium): Se elimina la visibilidad del producto tanto en Tienda como en WishList. Solo se mantiene las reservas de asociadas a las compras en estado `pending`

  - Parar de vender (hard): Se elimina la visibilidad del producto tanto en Tienda como en WishList, ademas pasan a `fail` todas las compras con pagos asociados con estado distintos a `pending`

- Wishlist:
  En una wishlist se encuentra la lista de productos que un comprador desea comparar eventualmente, al comprador se le notifica en caso de poca disponibilidad de un producto en su wishlist al igual que un cambio de precio en el mismo.

- Compra:
  Una compra es la accion de comprar un producto, causando la disminucion de la disponibilidad del mismo. Esta puede tener distintos pagos asociados (solo uno aceptado pero puede tener mucho pagos fallidos)
  - Pago:
    Un pago es el intento de completar una compra, si el pago es aceptado la compra termina exitosamente, al contrario si es fallido se pueden seguir intentando pagos (por ahora no politica de posible fraude)
    El pago se puede realizar por diferentes pasarelas mediante el proceso descrito:
    EL cliente realiza un intento de pago para una compra, causando que tanto la compra como el pago pasen a un estado de `pending`, luego se envia este pago a la pasarela seleccionada por el comprador para procesar el pago. La pasarela pudiera devolver dos tipos de respuesta:
    - OK:
      En este caso se pasa el pago a un estado `completed` y se confirma la compra
    - Fail(Reason):
      En caso de una compra fallida se permite realizar mas intentos se pone el pago `fallido` y se mantiene la reserva en `pending`, este estado de la compra se mantendra por un tiempo T o una cantidad C de pagos fallidos, luego de esto la compra pasa a fallida y se liberan los productos para otros posibles compradores
