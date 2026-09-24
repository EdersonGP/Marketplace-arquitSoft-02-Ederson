# Arquitectura inicial del sistema

## 1. Introducción

La arquitectura inicial del marketplace se organizará utilizando una arquitectura de tres capas.

Esta organización permite separar las responsabilidades del sistema y facilita su comprensión, mantenimiento y evolución.

---

## 2. Arquitectura en tres capas

### 2.1 Capa de Presentación

Esta capa representa la parte del sistema con la que interactúan los usuarios.

Permitirá el acceso al marketplace mediante una aplicación web y se comunicará con la lógica del sistema mediante una API REST.

Sus principales responsabilidades son:

- Mostrar la interfaz del marketplace.
- Permitir la interacción de clientes, sellers y administradores.
- Recibir las solicitudes realizadas por los usuarios.
- Enviar las solicitudes hacia la lógica de negocio.
- Mostrar las respuestas obtenidas del sistema.

---

### 2.2 Capa de Lógica de Negocio

Esta capa contiene las reglas y procesos principales del marketplace.

Los módulos iniciales identificados son:

- Usuarios.
- Sellers.
- Catálogo.
- Carrito.
- Pedidos.

#### Usuarios

Gestionará la información y operaciones relacionadas con los usuarios de la plataforma.

#### Sellers

Gestionará la información de los vendedores que participan en el marketplace.

#### Catálogo

Gestionará los productos disponibles para los clientes.

#### Carrito

Gestionará los productos que el cliente selecciona antes de realizar una compra.

#### Pedidos

Gestionará la creación, consulta y procesamiento de los pedidos realizados por los clientes.

---

### 2.3 Capa de Datos

Esta capa será responsable del almacenamiento y consulta de la información utilizada por el marketplace.

La base de datos almacenará información relacionada con:

- Usuarios.
- Sellers.
- Productos.
- Carritos.
- Pedidos.
- Información necesaria para el funcionamiento del sistema.

---

## 3. Flujo entre capas

La comunicación general del sistema se realizará de la siguiente manera:

Presentación
↓
Lógica de Negocio
↓
Datos

La capa de presentación recibe las interacciones de los usuarios y las envía a la lógica de negocio.

La lógica de negocio procesa las operaciones correspondientes y utiliza la capa de datos cuando necesita almacenar o consultar información.

---

## 4. Responsabilidad de cada capa

| Capa | Pregunta que responde |
|---|---|
| Presentación | ¿Cómo interactúa el usuario con el sistema? |
| Lógica de negocio | ¿Qué hace el sistema? |
| Datos | ¿Dónde se almacena la información? |

---

## 5. Resumen

La arquitectura inicial divide el marketplace en tres capas principales para separar las responsabilidades del sistema.

La capa de presentación gestiona la interacción con los usuarios, la capa de lógica de negocio contiene las funcionalidades principales del marketplace y la capa de datos se encarga del almacenamiento de información.

---

## 6. Diagrama de arquitectura

```mermaid
flowchart TD

%% =========================
%% ACTORES
%% =========================
subgraph ACTORES["ACTORES"]
    Cliente["Cliente"]
    Seller["Seller"]
    Admin["Administrador"]
end

%% =========================
%% PRESENTACIÓN
%% =========================
subgraph PRESENTACION["PRESENTACIÓN"]
    Web["Aplicación Web → API REST"]
end

%% =========================
%% LÓGICA DE NEGOCIO
%% =========================
subgraph NEGOCIO["LÓGICA DE NEGOCIO"]
    Usuarios["Usuarios"]
    Sellers["Sellers"]
    Catalogo["Catálogo"]
    Carrito["Carrito"]
    Pedidos["Pedidos"]
end

%% =========================
%% DATOS
%% =========================
subgraph DATOS["DATOS"]
    BD["Base de datos"]
end

%% =========================
%% SISTEMAS EXTERNOS
%% =========================
subgraph EXTERNOS["SISTEMAS EXTERNOS"]
    Pago["Pasarela de pago"]
    ERP["ERP"]
    Envio["Servicio de envío"]
end

%% =========================
%% FLUJO PRINCIPAL
%% =========================
ACTORES --> PRESENTACION
PRESENTACION --> NEGOCIO
NEGOCIO --> DATOS

%% Integraciones
DATOS -->|"integraciones"| EXTERNOS

%% =========================
%% DISTRIBUCIÓN HORIZONTAL
%% =========================
Cliente ~~~ Seller
Seller ~~~ Admin

Usuarios ~~~ Sellers
Sellers ~~~ Catalogo
Catalogo ~~~ Carrito
Carrito ~~~ Pedidos

Pago ~~~ ERP
ERP ~~~ Envio

%% =========================
%% ESTILOS
%% =========================
style ACTORES fill:#222,stroke:#fff,stroke-width:2px,color:#fff
style PRESENTACION fill:#222,stroke:#fff,stroke-width:2px,color:#fff
style NEGOCIO fill:#222,stroke:#fff,stroke-width:2px,color:#fff
style DATOS fill:#222,stroke:#fff,stroke-width:2px,color:#fff
style EXTERNOS fill:#222,stroke:#fff,stroke-width:2px,color:#fff

style Cliente fill:#222,stroke:#fff,color:#fff
style Seller fill:#222,stroke:#fff,color:#fff
style Admin fill:#222,stroke:#fff,color:#fff
style Web fill:#222,stroke:#fff,color:#fff

style Usuarios fill:#222,stroke:#fff,color:#fff
style Sellers fill:#222,stroke:#fff,color:#fff
style Catalogo fill:#222,stroke:#fff,color:#fff
style Carrito fill:#222,stroke:#fff,color:#fff
style Pedidos fill:#222,stroke:#fff,color:#fff

style BD fill:#222,stroke:#fff,color:#fff

style Pago fill:#222,stroke:#fff,color:#fff
style ERP fill:#222,stroke:#fff,color:#fff
style Envio fill:#222,stroke:#fff,color:#fff