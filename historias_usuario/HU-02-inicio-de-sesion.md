# HU-02 · Inicio de sesión

**Prioridad:** Alta · **Puntos de historia:** 3 · **Etiquetas:** `historia-de-usuario`, `inicio-de-sesion`

## Funcionalidad

> Cada funcionalidad inicia con un flujo guiado:
>
> - **Inicio de sesión:** acceso seguro con validación.

## Historia

> **Como** cliente de LePetitDep,  
> **quiero** iniciar sesión de forma segura con mi email y contraseña,  
> **para** acceder a mi carrito y a mis pedidos.

## Flujo guiado

1. Ingresa email y contraseña
2. El sistema valida las credenciales
3. Accede al menú con su sesión activa

## Criterios de aceptación

### CA-01: Acceso correcto

- **Dado que** tengo una cuenta registrada
- **Cuando** ingreso email y contraseña correctos
- **Entonces** veo "¡Bienvenido/a, <nombre>!" y soy llevado al **Menú**

### CA-02: Credenciales incorrectas

- **Dado que** ingreso un email o contraseña erróneos
- **Cuando** pulso **Ingresar**
- **Entonces** veo el mensaje genérico "Email o contraseña incorrectos." sin revelar cuál dato falló

### CA-03: Rutas protegidas

- **Dado que** no he iniciado sesión
- **Cuando** intento abrir Carrito, Pago o Mis pedidos
- **Entonces** soy redirigido a **Iniciar sesión**

### CA-04: Cerrar sesión

- **Dado que** tengo la sesión iniciada
- **Cuando** pulso **Salir**
- **Entonces** la sesión se cierra y vuelvo a **Iniciar sesión**

## Notas técnicas
- Archivo: `js/app.js` → `vistaLogin()`, `router()`

## Definición de terminado

- [ ] Todos los criterios de aceptación se cumplen
- [ ] Probado en Chrome, Edge y Firefox
- [ ] Se ve correctamente en móvil y escritorio
- [ ] Sin errores en la consola del navegador
- [ ] README actualizado si aplica
