# Drivers arquitectónicos

## 1. Introducción

Los drivers arquitectónicos son aquellos requisitos, atributos de calidad y restricciones que tienen una influencia significativa en las decisiones de arquitectura del sistema.

Para el marketplace de productos para mascotas se han identificado los siguientes drivers arquitectónicos.

---

## 2. Drivers arquitectónicos identificados

| ID | Driver arquitectónico | Origen | ¿Por qué influye en la arquitectura? |
|---|---|---|---|
| DA-01 | El sistema debe soportar un incremento importante de usuarios durante campañas comerciales. | AC-03 Escalabilidad | Puede influir en la estrategia de escalamiento y despliegue del sistema. |
| DA-02 | El sistema debe mantener tiempos de respuesta adecuados durante una alta concurrencia. | AC-01 Rendimiento | Puede influir en la comunicación entre componentes, procesamiento y almacenamiento. |
| DA-03 | El sistema debe proteger los datos de usuarios y operaciones de compra. | AC-04 Seguridad | Puede influir en mecanismos de autenticación, autorización y protección de datos. |
| DA-04 | El sistema debe integrarse con una pasarela de pago externa mediante una API. | RC-04 Pasarela de pago | Condiciona la forma de comunicación e integración con servicios externos. |
| DA-05 | El sistema debe utilizar una API REST para la comunicación entre frontend y backend. | RC-03 API REST | Limita las alternativas de comunicación entre las diferentes partes del sistema. |

---

## 3. Descripción de los drivers

### DA-01: Escalabilidad

El marketplace debe poder soportar un incremento considerable de usuarios, especialmente durante campañas comerciales o periodos de alta demanda.

Este driver puede influir en la forma en que se despliegue y escale la aplicación.

### DA-02: Rendimiento

El sistema debe mantener tiempos de respuesta adecuados cuando exista una gran cantidad de usuarios utilizando simultáneamente el marketplace.

Este driver puede afectar decisiones relacionadas con el procesamiento, comunicación y almacenamiento de información.

### DA-03: Seguridad

La plataforma debe proteger los datos de los usuarios y las operaciones relacionadas con las compras.

Esto influye en la implementación de mecanismos de autenticación, autorización y protección de información.

### DA-04: Integración con pasarela de pago

El sistema debe comunicarse con un servicio externo para procesar los pagos realizados por los clientes.

Esta integración condiciona la forma en que el sistema intercambiará información con servicios externos.

### DA-05: API REST

La comunicación entre el frontend y el backend deberá realizarse mediante una API REST.

Esta restricción determina la forma principal de comunicación entre la interfaz de usuario y la lógica del sistema.

---

## 4. Resumen

Los drivers arquitectónicos identificados representan los elementos que tienen mayor influencia sobre el diseño de la arquitectura del marketplace.

La escalabilidad, el rendimiento y la seguridad afectan directamente el comportamiento esperado del sistema, mientras que la API REST y la integración con la pasarela de pago condicionan la forma en que los componentes internos y externos se comunicarán.