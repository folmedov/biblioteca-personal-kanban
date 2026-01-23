# CU2 - Flujo de Préstamo de Libro

## Pre-condiciones

- El bibliotecario debe estar autenticado (futuro).
- El libro debe tener estado 'Disponible'.

## Flujo Principal

1. El bibliotecario ingresa el ID del Socio y el ID del Libro.
2. **Sistema valida Socio:**
   - Si el ID no existe -> Mostrar Error "Usuario no registrado".
3. **Sistema valida Libro:**
   - Recupera el objeto Libro.
   - Verifica propiedad `estado`.
   - SI `estado` != 'Disponible' -> Mostrar Error "El libro ya está prestado".
4. **Registro:**
   - Crear objeto `Préstamo` con fecha actual + fecha devolución (fecha actual + 7 días).
   - Actualizar `Libro.estado` a 'Prestado'.
5. **Salida:**
   - Mostrar confirmación con fecha de devolución.
