# ADR-001: Monolito modular

## Estado

Aceptada

## Contexto

El sistema Marketplace requiere gestionar diferentes funcionalidades como usuarios, catálogo, carrito, pedidos y pagos. Se necesita una estructura que permita organizar estas funcionalidades de manera independiente, manteniendo una solución inicialmente desplegable como una sola aplicación.

Además, el sistema debe poder evolucionar y soportar un incremento progresivo de usuarios y operaciones.

## Decisión

Se utilizará un **monolito modular** como estilo de organización principal de la aplicación.

Las funcionalidades del sistema se organizarán en módulos independientes dentro de una misma aplicación desplegable.

Los módulos principales serán:

- Usuarios
- Catálogo
- Carrito
- Pedidos
- Pagos

## Drivers arquitectónicos relacionados

- **DA-01 – Escalabilidad:** el sistema debe soportar un incremento importante de usuarios durante campañas comerciales.
- **DA-06 – Mantenibilidad / evolución modular:** el sistema debe permitir modificar funcionalidades sin afectar innecesariamente otros módulos.

## Justificación

El monolito modular permite mantener una solución relativamente sencilla de desplegar y operar, pero separando las responsabilidades funcionales en módulos.

Esta organización facilita el mantenimiento y permite que los módulos evolucionen de forma independiente dentro de la aplicación. Además, deja abierta la posibilidad de realizar una evolución futura hacia una arquitectura distribuida si las necesidades del sistema lo requieren.

## Resultado

La aplicación se implementará inicialmente como una única unidad desplegable, organizada internamente mediante módulos independientes para Usuarios, Catálogo, Carrito, Pedidos y Pagos.