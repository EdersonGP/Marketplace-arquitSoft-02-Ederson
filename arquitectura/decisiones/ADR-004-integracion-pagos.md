# ADR-004: Integración de pagos mediante interfaces y adaptadores

## Estado

Aceptada

## Contexto

El Marketplace necesita integrarse con una pasarela de pago externa para procesar las compras realizadas por los clientes.

La lógica principal del sistema no debe depender directamente de un proveedor específico de pagos.

## Decisión

La integración con la pasarela de pago se realizará mediante **interfaces y adaptadores**.

Los casos de uso relacionados con pagos utilizarán un contrato definido por la aplicación, mientras que la comunicación concreta con la pasarela externa será implementada mediante un adaptador.

## Driver arquitectónico relacionado

- **DA-04 – Integración con pasarela de pago**

## Justificación

La utilización de interfaces y adaptadores permite desacoplar los casos de uso del proveedor externo de pagos.

De esta manera, la lógica del negocio no necesita conocer los detalles específicos de la pasarela utilizada y se facilita su sustitución o modificación.

## Resultado

El sistema contará con un contrato de pago dentro de la aplicación y un adaptador encargado de comunicarse con la pasarela externa.