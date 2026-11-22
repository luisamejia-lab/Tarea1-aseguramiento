# HU-01 · Registro de usuario

**Prioridad:** Alta · **Puntos de historia:** 3 · **Etiquetas:** `historia-de-usuario`, `registro-de-usuario`

## Funcionalidad

> Cada funcionalidad inicia con un flujo guiado:
>
> - **Registro de usuario:** crear cuenta con email y contraseña

## Historia

> **Como** cliente de LePetitDep,  
> **quiero** registrarme con mi email y una contraseña,  
> **para** poder realizar pedidos de café y panadería.

## Flujo guiado

1. Ingresa nombre y email
2. Crea y confirma la contraseña
3. Pulsa **Crear cuenta** y es redirigido al inicio de sesión

## Criterios de aceptación

### CA-01: Registro exitoso

- **Dado que** estoy en la pantalla de registro
- **Cuando** ingreso nombre, un email válido no registrado y una contraseña que cumple la política
- **Entonces** se crea la cuenta, veo el mensaje "¡Cuenta creada!" y soy redirigido a **Iniciar sesión**

### CA-02: Email inválido

- **Dado que** ingreso un email sin formato válido (ej. `ana@`)
- **Cuando** pulso **Crear cuenta**
- **Entonces** veo el error "Email no válido." y no se crea la cuenta

### CA-03: Contraseñas distintas

- **Dado que** la confirmación no coincide con la contraseña
- **Cuando** pulso **Crear cuenta**
- **Entonces** veo "Las contraseñas no coinciden."

### CA-04: Email duplicado

- **Dado que** el email ya está registrado
- **Cuando** pulso **Crear cuenta**
- **Entonces** veo "Este email ya está registrado."

## Notas técnicas

- La contraseña se guarda como hash SHA-256 con sal, nunca en texto plano.
- El email se normaliza a minúsculas.
- Archivo: `js/app.js` → `vistaRegistro()`

## Definición de terminado

- [ ] Todos los criterios de aceptación se cumplen
- [ ] Probado en Chrome, Edge y Firefox
- [ ] Se ve correctamente en móvil y escritorio
- [ ] Sin errores en la consola del navegador
- [ ] README actualizado si aplica

