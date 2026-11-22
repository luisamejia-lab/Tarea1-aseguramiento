# HU-03 · Explorar menú

**Prioridad:** Alta · **Puntos de historia:** 2 · **Etiquetas:** `historia-de-usuario`, `explorar-menu`

## Funcionalidad

> Cada funcionalidad inicia con un flujo guiado:
>
> - **Explorar menú:** ver lista de cafés, precios y descripciones.

## Historia

> **Como** cliente de LePetitDep,  
> **quiero** ver la lista de cafés y productos de panadería con precios y descripciones,  
> **para** decidir qué quiero pedir.

## Flujo guiado

1. Elige una categoría (Todos, Café, Panadería)
2. Revisa nombre, descripción y precio de cada producto

## Criterios de aceptación

### CA-01: Ver menú completo

- **Dado que** entro a **Menú**
- **Cuando** la página carga
- **Entonces** veo los 12 productos con imagen, nombre, descripción y precio en formato `$0.00`

### CA-02: Filtrar por categoría

- **Dado que** estoy en **Menú**
- **Cuando** pulso **Café** o **Panadería**
- **Entonces** solo veo los productos de esa categoría y el botón queda resaltado

### CA-03: Acceso sin sesión

- **Dado que** no he iniciado sesión
- **Cuando** entro a **Menú**
- **Entonces** puedo ver el catálogo, pero se me pide iniciar sesión al intentar agregar productos

## Notas técnicas

- El catálogo está en `js/data.js` (constante `MENU`).
- Archivo: `js/app.js` → `vistaMenu()`

## Definición de terminado

- [ ] Todos los criterios de aceptación se cumplen
- [ ] Probado en Chrome, Edge y Firefox
- [ ] Se ve correctamente en móvil y escritorio
- [ ] Sin errores en la consola del navegador
- [ ] README actualizado si aplica
