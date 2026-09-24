# Restricciones del sistema

## 1. Introducción

Las restricciones son condiciones que deben respetarse durante el desarrollo del marketplace y que pueden influir directamente en las decisiones de diseño y arquitectura del sistema.

---

## 2. Restricciones identificadas

| ID | Restricción | Descripción |
|---|---|---|
| RC-01 | Aplicación web | El sistema debe desarrollarse como una aplicación accesible mediante un navegador web. |
| RC-02 | Control de versiones | El código fuente debe gestionarse utilizando Git y mantenerse en un repositorio compartido. |
| RC-03 | API REST | La comunicación entre el frontend y los servicios del sistema debe realizarse mediante una API REST. |
| RC-04 | Pasarela de pago | El sistema debe integrarse con una pasarela de pago externa para procesar las operaciones de pago. |
| RC-05 | Servicio de envío | El sistema debe integrarse con un servicio externo de envío para gestionar la información relacionada con la entrega de pedidos. |

---

## 3. Descripción de las restricciones

### RC-01: Aplicación web

El marketplace deberá funcionar mediante un navegador web para permitir el acceso de los usuarios a la plataforma.

### RC-02: Control de versiones

El proyecto deberá utilizar Git para gestionar los cambios realizados durante el desarrollo.

El código y la documentación deberán mantenerse en un repositorio compartido.

### RC-03: API REST

La comunicación entre la interfaz del sistema y los servicios del backend deberá realizarse mediante una API REST.

### RC-04: Pasarela de pago

El marketplace dependerá de una pasarela de pago externa para procesar las operaciones de pago realizadas por los clientes.

### RC-05: Servicio de envío

El sistema deberá comunicarse con un servicio externo encargado de gestionar información relacionada con la entrega de los pedidos.

---

## 4. Resumen

Las restricciones identificadas establecen condiciones que deben considerarse durante el diseño de la arquitectura.

En particular, el uso de una aplicación web, una API REST y servicios externos condicionará la forma en que se organizarán y comunicarán los componentes del marketplace.