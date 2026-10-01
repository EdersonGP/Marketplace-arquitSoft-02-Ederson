# ADR-003: Estrategia de caché

## Estado

Aceptada

## Contexto

El Marketplace puede recibir una cantidad elevada de consultas simultáneas, especialmente sobre información de productos y catálogo.

Las consultas repetitivas a la fuente de datos pueden afectar el rendimiento del sistema cuando aumenta la cantidad de usuarios.

## Decisión

Se utilizará una **estrategia de caché** para almacenar temporalmente información de consulta frecuente.

Inicialmente, la caché podrá utilizarse principalmente para información del catálogo y productos que no requiera actualización constante.

## Driver arquitectónico relacionado

- **DA-02 – Rendimiento**

## Justificación

La utilización de caché permite reducir consultas repetitivas a la fuente de datos y disminuir el tiempo necesario para responder determinadas solicitudes.

La caché se utilizará como mecanismo complementario y no reemplazará la fuente principal de información.

## Resultado

Las consultas frecuentes podrán ser atendidas mediante una capa de caché, reduciendo la carga sobre la fuente de datos y contribuyendo a mantener tiempos de respuesta adecuados.