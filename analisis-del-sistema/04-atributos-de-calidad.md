# Atributos de calidad

## 1. Introducción

Los atributos de calidad describen cómo debe comportarse el sistema, además de las funcionalidades que debe proporcionar.

Para el marketplace de productos para mascotas se consideran especialmente importantes el rendimiento, la disponibilidad, la escalabilidad, la seguridad y la mantenibilidad.

---

## 2. Atributos de calidad identificados

| ID | Atributo de calidad | Escenario de calidad |
|---|---|---|
| AC-01 | Rendimiento | Las consultas de productos, operaciones del carrito y pedidos deben responder rápidamente incluso cuando exista una alta cantidad de usuarios concurrentes. |
| AC-02 | Disponibilidad | El sistema debe permanecer disponible para que los clientes, sellers y administradores puedan realizar sus operaciones cuando lo necesiten. |
| AC-03 | Escalabilidad | El sistema debe poder soportar un incremento de usuarios, productos, sellers y solicitudes sin afectar significativamente su funcionamiento. |
| AC-04 | Seguridad | Los datos de los usuarios, cuentas, productos, pedidos y operaciones de compra deben estar protegidos frente a accesos no autorizados. |
| AC-05 | Mantenibilidad | El sistema debe estar organizado de manera que permita realizar cambios, correcciones y nuevas funcionalidades sin afectar innecesariamente otros componentes. |

---

## 3. Descripción de los atributos

### AC-01: Rendimiento

El marketplace debe responder de manera adecuada ante las solicitudes realizadas por los usuarios.

Esto incluye principalmente:

- Búsqueda de productos.
- Consulta de información de productos.
- Operaciones del carrito.
- Consulta y generación de pedidos.

El rendimiento cobra mayor importancia cuando existen varios usuarios utilizando la plataforma simultáneamente.

### AC-02: Disponibilidad

El marketplace debe mantenerse disponible para permitir que los usuarios puedan acceder y realizar sus operaciones.

Una interrupción del sistema podría impedir que los clientes realicen compras o que los sellers administren sus productos y pedidos.

### AC-03: Escalabilidad

El sistema debe ser capaz de soportar el crecimiento del marketplace.

Este crecimiento puede producirse por:

- Mayor cantidad de clientes.
- Mayor cantidad de sellers.
- Mayor cantidad de productos.
- Mayor cantidad de pedidos.
- Incremento de solicitudes simultáneas.

### AC-04: Seguridad

La plataforma debe proteger la información almacenada y las operaciones realizadas por los usuarios.

Se debe evitar que usuarios no autorizados puedan acceder o modificar información que no les corresponde.

### AC-05: Mantenibilidad

La organización del sistema debe facilitar la realización de cambios y correcciones.

Una adecuada separación de responsabilidades permitirá modificar una funcionalidad sin afectar innecesariamente otras partes del marketplace.

---

## 4. Resumen

Los atributos de calidad identificados influyen directamente en las futuras decisiones arquitectónicas del sistema.

Especialmente, el rendimiento, la escalabilidad y la seguridad serán importantes para soportar múltiples usuarios, proteger la información y mantener un funcionamiento adecuado del marketplace.