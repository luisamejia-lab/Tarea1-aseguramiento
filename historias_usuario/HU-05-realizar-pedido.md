# HU-05 · Realizar pedido

**Prioridad:** Alta · **Puntos de historia:** 5 · **Etiquetas:** `historia-de-usuario`, `realizar-pedido`

## Funcionalidad

> Cada funcionalidad inicia con un flujo guiado:
>
> - **Realizar pedido:** confirmación, método de pago simulado y número de orden.

## Historia

> **Como** cliente de LePetitDep,  
> **quiero** confirmar mi pedido, elegir un método de pago simulado y recibir un número de orden,  
> **para** retirarlo en el local.

## Flujo guiado

1. Revisa el resumen del pedido
2. Elige hora de retiro y método de pago
3. Confirma y recibe el número de orden

## Criterios de aceptación

### CA-01: Pago con tarjeta

- **Dado que** tengo productos en el carrito y estoy en **Realizar pedido**
- **Cuando** elijo tarjeta, ingreso 16 dígitos y un CVV de 3 dígitos y confirmo
- **Entonces** tras "Procesando pago simulado…" veo un número de orden `LPD-XXXXXXXX`, la hora de retiro y el total

### CA-02: Tarjeta inválida

- **Dado que** elijo tarjeta
- **Cuando** ingreso un número sin 16 dígitos o un CVV inválido
- **Entonces** veo el error correspondiente y no se procesa el pedido

### CA-03: Pago en efectivo o transferencia

- **Dado que** elijo **Efectivo al retirar** o **Transferencia**
- **Cuando** confirmo
- **Entonces** no se piden datos de tarjeta y se genera el número de orden

### CA-04: Confirmación previa

- **Dado que** completé el formulario
- **Cuando** pulso **Confirmar y pagar**
- **Entonces** se me pide confirmar el total antes de procesar

### CA-05: Carrito tras el pedido

- **Dado que** el pedido se confirmó
- **Cuando** vuelvo al **Carrito**
- **Entonces** el carrito está vacío y el pedido aparece en **Mis pedidos**

## Notas técnicas

- No se realiza ningún cobro real. Tarjeta de prueba: `1111 2222 3333 4444`, CVV `123`.
- El botón de pagar se deshabilita mientras se procesa para evitar pedidos duplicados.
- Archivo: `js/app.js` → `vistaCheckout()`, `vistaConfirmacion()`

## Definición de terminado

- [ ] Todos los criterios de aceptación se cumplen
- [ ] Probado en Chrome, Edge y Firefox
- [ ] Se ve correctamente en móvil y escritorio
- [ ] Sin errores en la consola del navegador
- [ ] README actualizado si aplica
