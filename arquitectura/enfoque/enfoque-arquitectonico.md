# Enfoque Arquitectónico

## 1. Enfoque seleccionado

Para la Plataforma Integral Multivendedor para la Gestión Comercial y Operativa de un Mercado de Abastos se utilizará **Clean Architecture (Arquitectura Limpia)** como enfoque arquitectónico interno.

Clean Architecture permitirá organizar las responsabilidades del sistema de forma que las reglas de negocio permanezcan independientes de frameworks, interfaces de usuario, bases de datos y servicios externos.

---

## 2. Objetivo

Separar las responsabilidades y controlar la dirección de las dependencias del sistema, manteniendo el dominio del negocio como núcleo de la solución.

Las dependencias deberán apuntar hacia las capas internas.

---

## 3. Problema que resuelve

El sistema integra múltiples módulos, como:

- Usuarios
- Comerciantes
- Puestos
- Productos
- Inventario
- Carrito multivendedor
- Pedidos
- Repartidores
- Pagos
- Delivery
- Auditoría
- Reportes

Sin una adecuada separación de responsabilidades, estos módulos podrían quedar fuertemente acoplados a tecnologías como Next.js, NestJS, PostgreSQL, Supabase o servicios externos.

Clean Architecture permite reducir este acoplamiento.

---

## 4. Capas de Clean Architecture

### 4.1 Dominio

Contiene las entidades, objetos de valor y reglas principales del negocio.

Ejemplos:

- Usuario
- Comerciante
- Puesto
- Producto
- Inventario
- Carrito
- Pedido
- Repartidor
- Pago
- Entrega

Ejemplos de reglas de negocio:

- No permitir confirmar cantidades superiores al stock disponible.
- No permitir que dos clientes reserven simultáneamente al mismo repartidor.
- Un pedido no debe continuar al proceso de compra si el pago no ha sido validado.
- Un pedido no debe marcarse como entregado sin la confirmación correspondiente.

El dominio no deberá depender de frameworks ni tecnologías externas.

---

### 4.2 Aplicación

Contiene los casos de uso que coordinan las operaciones del sistema.

Ejemplos:

- RegistrarUsuario
- AutenticarUsuario
- RegistrarProducto
- ActualizarInventario
- AgregarProductoAlCarrito
- CrearPedido
- SeleccionarRepartidor
- ValidarPago
- RegistrarCompra
- ConfirmarEntrega
- ConsultarReporte

Esta capa podrá definir interfaces o puertos necesarios para acceder a persistencia o servicios externos.

---

### 4.3 Infraestructura

Contiene las implementaciones concretas necesarias para interactuar con tecnologías externas.

Ejemplos:

- Repositorios PostgreSQL
- Supabase
- Supabase Storage
- Cloudflare R2
- Servicios de notificaciones
- Adaptadores de pagos
- Persistencia de auditoría
- Integraciones externas

La infraestructura implementará las interfaces definidas por las capas internas.

---

### 4.4 Presentación

Responsable de la interacción con los usuarios y de recibir las solicitudes.

Tecnologías:

- Next.js
- TypeScript
- Aplicación Web/PWA
- API REST

Interfaces principales:

- Marketplace
- Catálogo
- Carrito
- Seguimiento de pedidos
- Panel del comerciante
- Panel del repartidor
- Panel del administrador

La presentación enviará las solicitudes a los casos de uso de la capa de aplicación.

---

## 5. Regla de dependencias

Las dependencias deberán dirigirse hacia el núcleo del sistema.

La relación general será:

Presentación → Aplicación → Dominio

Infraestructura → Aplicación / Dominio

El dominio no deberá depender de:

- Next.js
- NestJS
- PostgreSQL
- Supabase
- Cloudflare R2
- Yape
- Plin
- servicios externos

---

## 6. Beneficios

- Facilita el mantenimiento del sistema.
- Reduce el acoplamiento entre módulos.
- Permite realizar pruebas unitarias sobre las reglas de negocio.
- Facilita cambiar tecnologías externas.
- Mejora la separación de responsabilidades.
- Permite evolucionar el sistema de manera modular.
- Mantiene las reglas principales del negocio independientes de frameworks.

---

## 7. Relación con los Drivers Arquitectónicos

Clean Architecture responde principalmente a:

- DA06 - Mantenibilidad / evolución modular.
- DA04 - Seguridad.
- DA12 - Auditoría y trazabilidad.
- DA14 - Evolución independiente de módulos.

El driver principal es **DA06 - Mantenibilidad**, debido a que se requiere modificar funcionalidades sin afectar innecesariamente otros módulos.

## 8. Diagrama del Enfoque Arquitectónico

```mermaid
flowchart TB

    subgraph PRESENTACION["PRESENTACIÓN"]
        Web["Web / PWA"]
        API["API REST"]
    end

    subgraph APLICACION["APLICACIÓN"]
        CasosUso["Casos de Uso"]
        Puertos["Interfaces / Puertos"]
    end

    subgraph DOMINIO["DOMINIO"]
        Entidades["Entidades"]
        Reglas["Reglas de Negocio"]
    end

    subgraph INFRAESTRUCTURA["INFRAESTRUCTURA"]
        PostgreSQL["PostgreSQL / Supabase"]
        Storage["Supabase Storage / Cloudflare R2"]
        Pagos["Adaptadores de Pago"]
        Notificaciones["Servicios Externos"]
    end

    Web --> API
    API --> CasosUso
    CasosUso --> Entidades
    CasosUso --> Reglas
    CasosUso --> Puertos

    PostgreSQL --> Puertos
    Storage --> Puertos
    Pagos --> Puertos
    Notificaciones --> Puertos

## 9. Diagrama de referencia de Clean Architecture
flowchart TB

    subgraph PRESENTACION["PRESENTACIÓN"]
        UI["Web / PWA"]
        API["Controladores / API REST"]
    end

    subgraph APLICACION["APLICACIÓN"]
        UC["Casos de Uso"]
        PU["Puertos / Interfaces"]
    end

    subgraph DOMINIO["DOMINIO"]
        ENT["Entidades"]
        RN["Reglas de Negocio"]
    end

    subgraph INFRA["INFRAESTRUCTURA"]
        DB["PostgreSQL / Supabase"]
        ST["Storage"]
        EXT["Servicios Externos"]
    end

    UI --> API
    API --> UC
    UC --> ENT
    UC --> RN
    UC --> PU

    DB --> PU
    ST --> PU
    EXT --> PU