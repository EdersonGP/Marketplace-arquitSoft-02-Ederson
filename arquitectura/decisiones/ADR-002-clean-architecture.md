# ADR-002: Clean Architecture

## Estado

Aceptada

## Contexto

El sistema Marketplace contiene diferentes funcionalidades y debe mantener separadas las reglas del negocio de los detalles tecnológicos.

Se requiere una estructura que facilite el mantenimiento del sistema y permita modificar tecnologías externas sin afectar innecesariamente las reglas principales del negocio.

## Decisión

Se utilizará **Clean Architecture** como enfoque arquitectónico interno.

La solución organizará las responsabilidades en las siguientes capas:

- Dominio
- Aplicación
- Presentación
- Infraestructura

Las dependencias deberán dirigirse hacia las capas internas, manteniendo el dominio independiente de frameworks, bases de datos y servicios externos.

## Driver arquitectónico relacionado

- **DA-06 – Mantenibilidad / evolución modular**

## Justificación

Clean Architecture permite separar las reglas del negocio de los detalles tecnológicos. Esto facilita realizar cambios en la interfaz, persistencia o servicios externos sin modificar innecesariamente las reglas principales del sistema.

También favorece la separación de responsabilidades y facilita las pruebas de las reglas de negocio.

## Resultado

El sistema contará con una organización interna basada en Clean Architecture, manteniendo las reglas del negocio independientes de las tecnologías externas.