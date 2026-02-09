# 🐞 BUG-002 – El orden de productos no se mantiene al navegar

## ID
BUG-002

## Título
El orden seleccionado de productos no se mantiene al volver al listado

## Módulo
Listado de Productos

## Entorno
- Aplicación: SauceDemo
- URL: https://www.saucedemo.com/
- Navegador: Chrome
- Versión: Web
- Fecha: Febrero 2026

## Precondiciones
- Usuario autenticado correctamente
- Usuario ubicado en la página de listado de productos

## Pasos para reproducir
1. Iniciar sesión con un usuario válido
2. En el listado de productos, seleccionar un criterio de orden (por ejemplo: Price (low to high))
3. Hacer clic en un producto para ver el detalle
4. Volver al listado de productos

## Resultado esperado
El listado debería mantener el criterio de orden previamente seleccionado.

## Resultado actual
El listado vuelve al orden por defecto, perdiendo el criterio seleccionado.

## Severidad
Baja

## Prioridad
Media

## Justificación
La severidad es baja porque no afecta la funcionalidad principal de compra.
La prioridad es media ya que impacta la experiencia del usuario y la usabilidad
del catálogo de productos.

## Evidencia
Comportamiento observado durante la navegación del usuario.
