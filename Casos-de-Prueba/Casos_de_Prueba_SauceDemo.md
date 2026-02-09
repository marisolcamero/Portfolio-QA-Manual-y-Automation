# 🧪 Casos de Prueba - Sauce Demo

## Información del Proyecto
- **Aplicación:** Sauce Demo
- **URL:** https://www.saucedemo.com/
- **Versión:** 1.0
- **Fecha:** Febrero 2026
- **QA Engineer:** [Tu Nombre]

---

## 📋 Índice de Casos de Prueba

1. [Login de usuarios válidos e inválidos](#1-login-de-usuarios-válidos-e-inválidos) (6 casos)
2. [Visualización del listado de productos](#2-visualización-del-listado-de-productos) (4 casos)
3. [Agregado y eliminación de productos del carrito](#3-agregado-y-eliminación-de-productos-del-carrito) (5 casos)
4. [Proceso de checkout](#4-proceso-de-checkout) (5 casos)
5. [Finalización de compra](#5-finalización-de-compra) (3 casos)
6. [Logout del sistema](#6-logout-del-sistema) (3 casos)

**Total de Casos de Prueba:** 26

---

## 1. Login de usuarios válidos e inválidos

### CP-01: Login con credenciales válidas

**Objetivo:** Verificar que un usuario puede iniciar sesión con credenciales válidas.

**Prioridad:** Alta

**Precondiciones:**
- Navegador abierto en https://www.saucedemo.com/
- Usuario no autenticado

**Datos de prueba:**
- Usuario: `standard_user`
- Password: `secret_sauce`

**Pasos:**
1. Ingresar "standard_user" en el campo Username
2. Ingresar "secret_sauce" en el campo Password
3. Hacer clic en el botón "Login"
4. Verificar la URL de destino
5. Verificar que se muestra el inventario de productos

**Resultado esperado:**
- El sistema redirige a `/inventory.html`
- Se muestra el título "Products"
- Se visualizan los productos del inventario
- El icono del carrito está visible en la esquina superior derecha

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-02: Login con password inválido

**Objetivo:** Verificar que el sistema rechaza un intento de login con password incorrecta.

**Prioridad:** Alta

**Precondiciones:**
- Navegador abierto en la página de login
- Usuario no autenticado

**Datos de prueba:**
- Usuario: `standard_user`
- Password: `password_incorrecta`

**Pasos:**
1. Ingresar "standard_user" en el campo Username
2. Ingresar "password_incorrecta" en el campo Password
3. Hacer clic en el botón "Login"
4. Verificar que aparece un mensaje de error
5. Verificar que no se redirige a otra página

**Resultado esperado:**
- Se muestra el mensaje de error: "Epic sadface: Username and password do not match any user in this service"
- El usuario permanece en la página de login
- Los campos no se limpian automáticamente
- Aparece un ícono de error (X) en rojo

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-03: Login con usuario inexistente

**Objetivo:** Verificar que el sistema rechaza credenciales de un usuario que no existe.

**Prioridad:** Alta

**Precondiciones:**
- Navegador abierto en la página de login
- Usuario no autenticado

**Datos de prueba:**
- Usuario: `usuario_inexistente_123`
- Password: `secret_sauce`

**Pasos:**
1. Ingresar "usuario_inexistente_123" en el campo Username
2. Ingresar "secret_sauce" en el campo Password
3. Hacer clic en el botón "Login"
4. Verificar el mensaje de error mostrado
5. Verificar que permanece en la página de login

**Resultado esperado:**
- Se muestra el mensaje: "Epic sadface: Username and password do not match any user in this service"
- El usuario permanece en la página de login
- No se permite el acceso al sistema
- El botón de cerrar error (X) está presente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-04: Login con campos vacíos

**Objetivo:** Verificar que el sistema valida campos obligatorios en el formulario de login.

**Prioridad:** Media

**Precondiciones:**
- Navegador abierto en la página de login
- Campos de login vacíos

**Datos de prueba:**
- Usuario: (vacío)
- Password: (vacío)

**Pasos:**
1. Dejar el campo Username vacío
2. Dejar el campo Password vacío
3. Hacer clic en el botón "Login"
4. Verificar el mensaje de validación

**Resultado esperado:**
- Se muestra el mensaje: "Epic sadface: Username is required"
- No se permite el login
- El formulario mantiene el foco
- Aparece indicador visual de error

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-05: Login con usuario bloqueado (locked_out_user)

**Objetivo:** Verificar que un usuario bloqueado no puede acceder al sistema.

**Prioridad:** Alta

**Precondiciones:**
- Navegador abierto en la página de login
- Usuario no autenticado

**Datos de prueba:**
- Usuario: `locked_out_user`
- Password: `secret_sauce`

**Pasos:**
1. Ingresar "locked_out_user" en el campo Username
2. Ingresar "secret_sauce" en el campo Password
3. Hacer clic en el botón "Login"
4. Verificar el mensaje de error específico
5. Confirmar que no se permite el acceso

**Resultado esperado:**
- Se muestra el mensaje: "Epic sadface: Sorry, this user has been locked out."
- El acceso es denegado
- El usuario permanece en la página de login
- Se muestra el icono de error

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-06: Validación de mensaje de error

**Objetivo:** Verificar que los mensajes de error son claros y se pueden cerrar.

**Prioridad:** Media

**Precondiciones:**
- Navegador en página de login
- Mensaje de error visible (provocado por credenciales inválidas)

**Pasos:**
1. Provocar un error de login (usar credenciales inválidas)
2. Verificar que aparece el mensaje de error
3. Localizar el botón de cerrar error (X)
4. Hacer clic en el botón X
5. Verificar que el mensaje desaparece

**Resultado esperado:**
- El mensaje de error es visible y legible
- El botón X está presente en el contenedor del error
- Al hacer clic en X, el mensaje desaparece
- El formulario queda limpio y listo para reintentar

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 2. Visualización del listado de productos

### CP-07: Visualizar lista de productos

**Objetivo:** Verificar que el inventario de productos se muestra correctamente.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado como `standard_user`
- Navegación en la página de inventario

**Pasos:**
1. Iniciar sesión con credenciales válidas
2. Verificar la carga de la página de productos
3. Contar el número de productos mostrados
4. Verificar que cada producto tiene imagen, nombre, descripción y precio
5. Verificar que cada producto tiene el botón "Add to cart"

**Resultado esperado:**
- Se muestran 6 productos en total
- Cada producto incluye:
  - Imagen del producto
  - Nombre del producto
  - Descripción
  - Precio en formato $X.XX
  - Botón "Add to cart"
- El layout es consistente para todos los productos

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-08: Visualizar detalle de un producto

**Objetivo:** Verificar que se puede acceder al detalle de un producto específico.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- En la página de inventario con productos visibles

**Pasos:**
1. Identificar un producto en la lista (ej: "Sauce Labs Backpack")
2. Hacer clic en el nombre o imagen del producto
3. Verificar la redirección a la página de detalle
4. Verificar la información mostrada
5. Verificar la presencia del botón "Back to products"

**Resultado esperado:**
- Se redirige a `/inventory-item.html?id=X`
- Se muestra imagen ampliada del producto
- Se muestra nombre, descripción completa y precio
- Botón "Add to cart" está disponible
- Botón "Back to products" permite volver al inventario

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-09: Ordenar productos por nombre

**Objetivo:** Verificar que el filtro de ordenamiento por nombre funciona correctamente.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- En la página de inventario

**Pasos:**
1. Localizar el dropdown de ordenamiento (Product Sort Container)
2. Hacer clic en el dropdown
3. Seleccionar "Name (A to Z)"
4. Verificar el orden de los productos
5. Cambiar a "Name (Z to A)"
6. Verificar el nuevo orden

**Resultado esperado:**
- **A to Z:** Los productos se ordenan alfabéticamente ascendente
  - Primer producto: "Sauce Labs Backpack"
- **Z to A:** Los productos se ordenan alfabéticamente descendente
  - Primer producto: "Test.allTheThings() T-Shirt (Red)"
- El orden se aplica inmediatamente sin recargar la página

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-10: Ordenar productos por precio

**Objetivo:** Verificar que el filtro de ordenamiento por precio funciona correctamente.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- En la página de inventario

**Pasos:**
1. Abrir el dropdown de ordenamiento
2. Seleccionar "Price (low to high)"
3. Verificar que el primer producto es el más barato
4. Verificar que el último producto es el más caro
5. Cambiar a "Price (high to low)"
6. Verificar el orden inverso

**Resultado esperado:**
- **Low to High:** Productos ordenados por precio ascendente
  - Precio más bajo primero ($7.99)
- **High to Low:** Productos ordenados por precio descendente
  - Precio más alto primero ($49.99)
- Los precios están correctamente ordenados
- El ordenamiento es estable y consistente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 3. Agregado y eliminación de productos del carrito

### CP-11: Agregar un producto al carrito

**Objetivo:** Verificar que se puede agregar un producto al carrito de compras.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Carrito vacío (badge sin número o en 0)
- En la página de inventario

**Pasos:**
1. Verificar que el badge del carrito está vacío o en 0
2. Seleccionar un producto (ej: "Sauce Labs Backpack")
3. Hacer clic en el botón "Add to cart"
4. Verificar el cambio en el botón
5. Verificar el badge del carrito

**Resultado esperado:**
- El botón cambia de "Add to cart" a "Remove"
- El badge del carrito muestra "1"
- El badge es visible en rojo
- El producto queda marcado como agregado

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-12: Agregar múltiples productos

**Objetivo:** Verificar que se pueden agregar varios productos al carrito.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Carrito vacío
- En la página de inventario

**Pasos:**
1. Agregar el primer producto al carrito
2. Verificar que el badge muestra "1"
3. Agregar un segundo producto
4. Verificar que el badge muestra "2"
5. Agregar un tercer producto
6. Verificar que el badge muestra "3"
7. Hacer clic en el icono del carrito
8. Verificar que los 3 productos están en el carrito

**Resultado esperado:**
- El badge incrementa correctamente: 1 → 2 → 3
- Todos los botones cambian a "Remove"
- Al abrir el carrito, se muestran los 3 productos
- Cada producto mantiene su nombre, precio y cantidad

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-13: Eliminar producto desde carrito

**Objetivo:** Verificar que se puede eliminar un producto desde la página del carrito.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Al menos un producto en el carrito
- Navegación en la página del carrito (`/cart.html`)

**Pasos:**
1. Agregar un producto al carrito
2. Hacer clic en el icono del carrito
3. Verificar que el producto está listado
4. Hacer clic en el botón "Remove" del producto
5. Verificar que el producto desaparece
6. Verificar el badge del carrito

**Resultado esperado:**
- El producto se elimina de la lista del carrito
- El badge del carrito disminuye en 1
- Si era el único producto, el badge desaparece
- El mensaje "QTY" y "DESCRIPTION" siguen visibles aunque el carrito esté vacío

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-14: Eliminar producto desde la lista

**Objetivo:** Verificar que se puede eliminar un producto desde la página de inventario.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- Al menos un producto agregado al carrito
- Navegación en la página de inventario

**Pasos:**
1. Agregar un producto al carrito (botón cambia a "Remove")
2. Verificar el badge del carrito (muestra el número)
3. Hacer clic en el botón "Remove" desde la lista de productos
4. Verificar que el botón vuelve a "Add to cart"
5. Verificar el badge del carrito
6. Ir al carrito y verificar que el producto no está

**Resultado esperado:**
- El botón vuelve a "Add to cart"
- El badge del carrito disminuye en 1
- El producto ya no aparece en el carrito
- La acción se refleja inmediatamente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-15: Validar cantidad de productos en carrito

**Objetivo:** Verificar que el badge del carrito refleja correctamente la cantidad de productos.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- Carrito vacío

**Pasos:**
1. Verificar que el badge está oculto o en 0
2. Agregar 3 productos diferentes
3. Verificar que el badge muestra "3"
4. Eliminar 1 producto
5. Verificar que el badge muestra "2"
6. Agregar 2 productos más
7. Verificar que el badge muestra "4"
8. Ir al carrito y contar manualmente los productos

**Resultado esperado:**
- El badge siempre refleja el número exacto de productos
- El conteo es preciso: 0 → 3 → 2 → 4
- El número en el badge coincide con los productos en `/cart.html`
- El badge es visible cuando hay productos, oculto cuando está vacío

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 4. Proceso de checkout

### CP-16: Acceder al checkout

**Objetivo:** Verificar que se puede acceder al proceso de checkout desde el carrito.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Al menos un producto en el carrito
- Navegación en la página del carrito

**Pasos:**
1. Agregar al menos un producto al carrito
2. Hacer clic en el icono del carrito
3. Verificar que se muestra el botón "Checkout"
4. Hacer clic en el botón "Checkout"
5. Verificar la redirección a la página de información

**Resultado esperado:**
- Se redirige a `/checkout-step-one.html`
- Se muestran 3 campos de formulario:
  - First Name
  - Last Name
  - Zip/Postal Code
- Se muestra el botón "Continue"
- Se muestra el botón "Cancel"

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-17: Checkout con datos válidos

**Objetivo:** Verificar que se puede completar el paso 1 del checkout con información válida.

**Prioridad:** Alta

**Precondiciones:**
- Usuario en la página de checkout step one
- Al menos un producto en el carrito

**Datos de prueba:**
- First Name: `Juan`
- Last Name: `Pérez`
- Zip/Postal Code: `1234`

**Pasos:**
1. Ingresar "Juan" en First Name
2. Ingresar "Pérez" en Last Name
3. Ingresar "1234" en Zip/Postal Code
4. Hacer clic en el botón "Continue"
5. Verificar la redirección a checkout step two

**Resultado esperado:**
- Se redirige a `/checkout-step-two.html`
- Se muestra el resumen de la compra con:
  - Lista de productos
  - Payment Information
  - Shipping Information
  - Price Total (Item total, Tax, Total)
- Botones "Cancel" y "Finish" están presentes

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-18: Checkout con campos obligatorios vacíos

**Objetivo:** Verificar que el sistema valida campos obligatorios en el checkout.

**Prioridad:** Alta

**Precondiciones:**
- Usuario en la página de checkout step one

**Pasos:**
1. Dejar el campo First Name vacío
2. Completar Last Name con "Pérez"
3. Completar Zip/Postal Code con "1234"
4. Hacer clic en "Continue"
5. Verificar el mensaje de error

**Resultado esperado:**
- Se muestra el mensaje: "Error: First Name is required"
- No se avanza al siguiente paso
- El formulario mantiene los datos ingresados en los otros campos
- Se muestra un indicador visual de error

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-19: Validación de mensajes de error

**Objetivo:** Verificar que cada campo obligatorio muestra su mensaje de error específico.

**Prioridad:** Media

**Precondiciones:**
- Usuario en checkout step one

**Pasos:**
1. **Escenario 1:** Dejar First Name vacío → Click Continue
   - Verificar mensaje: "Error: First Name is required"
2. **Escenario 2:** Dejar Last Name vacío → Click Continue
   - Verificar mensaje: "Error: Last Name is required"
3. **Escenario 3:** Dejar Zip/Postal Code vacío → Click Continue
   - Verificar mensaje: "Error: Postal Code is required"
4. Verificar que cada error se puede cerrar con el botón X

**Resultado esperado:**
- Cada campo vacío genera su mensaje específico
- Los mensajes son claros y descriptivos
- El botón X cierra el mensaje de error
- La validación ocurre al hacer clic en Continue

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-20: Cancelar checkout y volver al carrito

**Objetivo:** Verificar que se puede cancelar el checkout en cualquier paso.

**Prioridad:** Media

**Precondiciones:**
- Usuario en checkout step one o step two
- Al menos un producto en el carrito

**Pasos:**
1. Navegar al checkout step one
2. Hacer clic en el botón "Cancel"
3. Verificar la redirección
4. Verificar que los productos siguen en el carrito
5. Repetir desde checkout step two

**Resultado esperado:**
- **Desde step one:** Redirige a `/cart.html`
- **Desde step two:** Redirige a `/inventory.html`
- Los productos permanecen en el carrito
- El badge mantiene el número de productos
- No se pierde información del carrito

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 5. Finalización de compra

### CP-21: Finalizar compra correctamente

**Objetivo:** Verificar que se puede completar el proceso de compra end-to-end.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Al menos un producto en el carrito
- Información de checkout completada

**Pasos:**
1. Agregar productos al carrito
2. Ir al checkout
3. Completar información personal (First Name, Last Name, Zip)
4. Click en "Continue"
5. Revisar el resumen en checkout step two
6. Verificar los totales (Item total + Tax = Total)
7. Hacer clic en el botón "Finish"
8. Verificar la página de confirmación

**Resultado esperado:**
- Se redirige a `/checkout-complete.html`
- Se muestra el mensaje "Thank you for your order!"
- Se muestra un ícono de confirmación (check verde)
- Se muestra mensaje: "Your order has been dispatched, and will arrive just as fast as the pony can get there!"
- Botón "Back Home" está presente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-22: Validar mensaje de compra exitosa

**Objetivo:** Verificar que los mensajes de confirmación son claros y correctos.

**Prioridad:** Media

**Precondiciones:**
- Compra finalizada exitosamente
- Usuario en la página de checkout complete

**Pasos:**
1. Completar una compra
2. En la página de confirmación, verificar:
   - Header "Thank you for your order!"
   - Texto descriptivo sobre el envío
   - Imagen/icono de confirmación
   - Botón "Back Home"

**Resultado esperado:**
- Header: "Thank you for your order!"
- Mensaje: "Your order has been dispatched, and will arrive just as fast as the pony can get there!"
- Imagen de confirmación (pony delivery) visible
- Botón "Back Home" funcional

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-23: Validar limpieza del carrito post-compra

**Objetivo:** Verificar que el carrito se vacía automáticamente después de finalizar la compra.

**Prioridad:** Alta

**Precondiciones:**
- Compra completada exitosamente
- Usuario en página de confirmación

**Pasos:**
1. Completar una compra con 3 productos
2. En la página de confirmación, verificar el badge del carrito
3. Hacer clic en "Back Home"
4. Verificar la página de inventario
5. Hacer clic en el icono del carrito
6. Verificar que el carrito está vacío

**Resultado esperado:**
- El badge del carrito desaparece o muestra "0"
- Todos los botones vuelven a "Add to cart"
- Al abrir el carrito, no hay productos listados
- El estado del carrito se resetea completamente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 6. Logout del sistema

### CP-24: Logout desde menú

**Objetivo:** Verificar que el usuario puede cerrar sesión correctamente.

**Prioridad:** Alta

**Precondiciones:**
- Usuario autenticado
- Navegación en cualquier página del sistema

**Pasos:**
1. Hacer clic en el botón del menú hamburguesa (☰)
2. Verificar que el menú lateral se abre
3. Verificar las opciones del menú
4. Hacer clic en "Logout"
5. Verificar la redirección

**Resultado esperado:**
- El menú lateral se despliega de izquierda a derecha
- Opciones visibles: All Items, About, Logout, Reset App State
- Al hacer clic en "Logout", redirige a la página de login
- URL es `/` o `/index.html`
- Los campos de login están vacíos

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-25: Validar acceso denegado post-logout

**Objetivo:** Verificar que después del logout no se puede acceder a páginas protegidas.

**Prioridad:** Alta

**Precondiciones:**
- Usuario previamente autenticado
- Logout realizado correctamente

**Pasos:**
1. Realizar logout
2. Verificar que se redirige al login
3. Intentar acceder a `/inventory.html` manualmente (modificando URL)
4. Intentar acceder a `/cart.html` manualmente
5. Verificar el comportamiento del sistema

**Resultado esperado:**
- Intentar acceder a `/inventory.html` redirige al login
- Intentar acceder a `/cart.html` redirige al login
- No se puede acceder a páginas protegidas sin autenticación
- El sistema protege todas las rutas internas

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

### CP-26: Logout y navegación con botón "back"

**Objetivo:** Verificar que el botón "back" del navegador no permite regresar después del logout.

**Prioridad:** Media

**Precondiciones:**
- Usuario autenticado
- Navegación en página de inventario

**Pasos:**
1. Estar autenticado en la página de inventario
2. Realizar logout
3. Verificar que redirige al login
4. Hacer clic en el botón "back" del navegador
5. Verificar el comportamiento

**Resultado esperado:**
- Al hacer clic en "back", el sistema debería:
  - Redirigir nuevamente al login, O
  - Mostrar la página anterior pero sin acceso a funcionalidad (sin sesión)
- No se debe permitir interacción con páginas protegidas
- La sesión está cerrada correctamente

**Estado:** [ ] Pendiente | [ ] Pasó | [ ] Falló

---

## 📊 Resumen de Casos de Prueba

| Módulo | Total Casos | Prioridad Alta | Prioridad Media |
|--------|-------------|----------------|-----------------|
| Login | 6 | 4 | 2 |
| Visualización de productos | 4 | 1 | 3 |
| Carrito | 5 | 3 | 2 |
| Checkout | 5 | 3 | 2 |
| Finalización | 3 | 2 | 1 |
| Logout | 3 | 2 | 1 |
| **TOTAL** | **26** | **15** | **11** |

---

## 📝 Notas para Ejecución

### Usuarios de Prueba Disponibles:
- `standard_user` - Usuario estándar (funciona correctamente)
- `locked_out_user` - Usuario bloqueado
- `problem_user` - Usuario con problemas de UI
- `performance_glitch_user` - Usuario con problemas de performance
- `error_user` - Usuario que genera errores
- `visual_user` - Usuario para pruebas visuales

**Password para todos:** `secret_sauce`

### Consideraciones:
- Ejecutar casos en orden para validar el flujo completo
- Limpiar el carrito entre ejecuciones
- Utilizar diferentes navegadores (Chrome, Firefox, Safari)
- Documentar screenshots de los defectos encontrados
- Verificar responsive design en móviles

---

## 🐛 Template de Reporte de Defectos

Cuando encuentres un bug, documéntalo así:

**ID Defecto:** BUG-XXX  
**Título:** [Descripción breve del problema]  
**Severidad:** Crítica | Alta | Media | Baja  
**Prioridad:** Alta | Media | Baja  
**Caso de Prueba:** CP-XX  
**Pasos para reproducir:**
1. [Paso 1]
2. [Paso 2]
3. [Paso 3]

**Resultado esperado:** [Qué debería pasar]  
**Resultado actual:** [Qué está pasando]  
**Evidencia:** [Screenshot o video]  
**Navegador/SO:** [Chrome 120 / Windows 11]

---

**Preparado por:** [Tu Nombre]  
**Última actualización:** Febrero 2026
