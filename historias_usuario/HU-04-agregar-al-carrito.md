# HU-04 · Agregar productos al carrito

**Prioridad:** Alta · **Puntos de historia:** 3 · **Etiquetas:** `historia-de-usuario`, `agregar-al-carrito`

## Funcionalidad

> Cada funcionalidad inicia con un flujo guiado:
>
> - **Agregar productos al carrito:** seleccionar cantidad y productos.

## Historia

> **Como** cliente de LePetitDep,  
> **quiero** seleccionar productos y cantidades y agregarlos al carrito,  
> **para** armar mi pedido antes de pagar.

## Flujo guiado

1. Selecciona la cantidad del producto
2. Pulsa **Agregar**
3. Revisa y ajusta el carrito

## Criterios de aceptación

### CA-01: Agregar producto

- **Dado que** tengo sesión iniciada y estoy en **Menú**
- **Cuando** elijo una cantidad entre 1 y 20 y pulso **Agregar**
- **Entonces** veo "<cantidad> × <producto> agregado ✔" y el contador del carrito se actualiza

### CA-02: Producto repetido

- **Dado que** el producto ya está en el carrito
- **Cuando** lo agrego otra vez
- **Entonces** se suma la cantidad (máximo 20 por producto)

### CA-03: Cantidad inválida

- **Dado que** ingreso 0, un número negativo o mayor a 20
- **Cuando** pulso **Agregar**
- **Entonces** veo "Cantidad entre 1 y 20" y no se agrega

### CA-04: Editar carrito

- **Dado que** estoy en **Carrito**
- **Cuando** cambio una cantidad o pulso ✕
- **Entonces** el subtotal, IVA 15% y total se recalculan o el producto se elimina

### CA-05: Carrito vacío

- **Dado que** no tengo productos
- **Cuando** entro a **Carrito**
- **Entonces** veo "Tu carrito está vacío." y el botón **Ir al menú**

## Notas técnicas

- El carrito se guarda por usuario en `localStorage`.
- Archivo: `js/app.js` → `vistaMenu()`, `vistaCarrito()`, `totales()`

## Definición de terminado

- [ ] Todos los criterios de aceptación se cumplen
- [ ] Probado en Chrome, Edge y Firefox
- [ ] Se ve correctamente en móvil y escritorio
- [ ] Sin errores en la consola del navegador
- [ ] README actualizado si aplica
