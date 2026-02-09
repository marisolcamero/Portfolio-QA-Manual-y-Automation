# 📘 Plan de Pruebas – SauceDemo

## 1. Introducción

Este documento describe el **Plan de Pruebas** para la aplicación web **SauceDemo**, una plataforma de comercio electrónico utilizada con fines educativos para la práctica de testing de software.

El objetivo de este plan es definir el alcance, la estrategia, los recursos y los criterios necesarios para ejecutar pruebas manuales que permitan evaluar la calidad del producto desde la perspectiva del usuario final.

Proyecto	Sauce Demo - Plataforma E-commerce
URL	https://www.saucedemo.com/
Versión	1.0
Fecha	Febrero 2026
QA Engineer	Maria Soledad Camero.

## 2. Objetivo del Testing

- Verificar que las funcionalidades principales de SauceDemo funcionen de acuerdo a los requisitos esperados.
- Detectar defectos funcionales antes de la liberación.
- Validar la experiencia del usuario en los flujos críticos del sistema.
- Documentar resultados y defectos encontrados durante el proceso de testing.

---

## 3. Alcance del Testing

### ✔ Dentro del alcance
- Login de usuarios válidos e inválidos.
- Visualización del listado de productos.
- Agregado y eliminación de productos del carrito.
- Proceso de checkout.
- Finalización de compra.
- Logout del sistema.

### ❌ Fuera del alcance
- Pruebas de rendimiento y carga.
- Pruebas de seguridad avanzadas.
- Integraciones con sistemas externos.
- Pruebas en dispositivos móviles nativos.

---

## 4. Estrategia de Testing

El testing será **manual**, basado en la ejecución de casos de prueba funcionales diseñados a partir del análisis de los flujos principales del negocio.

Se utilizarán técnicas como:
- Pruebas funcionales
- Pruebas exploratorias
- Pruebas de regresión básicas
- Pruebas de humo (smoke testing)

Las pruebas se ejecutarán en ambiente web utilizando navegadores de escritorio.

---

## 5. Tipos de Prueba

- **Pruebas Funcionales**
- **Pruebas de Humo**
- **Pruebas Exploratorias**
- **Pruebas de Regresión**

---

## 6. Criterios de Entrada

- La aplicación SauceDemo se encuentra disponible y accesible.
- El entorno de pruebas es estable.
- Los casos de prueba están diseñados y aprobados.
- Se cuenta con credenciales válidas de usuario.

---

## 7. Criterios de Salida

- Todos los casos de prueba fueron ejecutados.
- Los defectos encontrados fueron documentados.
- No existen defectos críticos abiertos.
- Se generó un reporte final de pruebas.

---

## 8. Gestión de Defectos

Los defectos serán documentados indicando:
- Identificador del defecto
- Título
- Descripción
- Pasos para reproducir
- Resultado esperado
- Resultado actual
- Severidad
- Prioridad
- Evidencia visual

La documentación de defectos se realizará de forma simulada siguiendo el formato utilizado en herramientas como **Jira**.

---

## 9. Riesgos

- Cambios no documentados en la aplicación.
- Limitación del entorno de pruebas.
- Falta de datos de prueba adicionales.
- Restricciones de tiempo para la ejecución completa.

---

## 10. Herramientas Utilizadas

- Navegador Web (Chrome)
- Git / GitHub (versionado de documentación)
- Markdown para documentación
- Jira (simulado para reporte de bugs)

---

## 11. Aprobación

Este Plan de Pruebas se utiliza con fines educativos y de demostración de competencias en testing manual dentro de un portafolio profesional QA.
