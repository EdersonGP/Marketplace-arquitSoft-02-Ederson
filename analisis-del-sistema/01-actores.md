# Actores del sistema

## 1. Descripción del sistema

El sistema será un **marketplace especializado en productos para mascotas**, que permitirá a diferentes vendedores (sellers) ofrecer sus productos a los clientes mediante una plataforma centralizada.

La plataforma permitirá reunir productos de diferentes vendedores en un mismo espacio, facilitando a los clientes la búsqueda y adquisición de alimentos y otros artículos para mascotas.

## 2. Actores identificados

### 2.1 Cliente

Es la persona que utiliza el marketplace para adquirir productos para sus mascotas.

Entre sus principales actividades se encuentran:

* Consultar productos disponibles.
* Buscar productos.
* Revisar información de los productos.
* Seleccionar productos.
* Agregar productos al carrito.
* Realizar compras.
* Consultar sus pedidos.

### 2.2 Seller

Es el vendedor que utiliza la plataforma para ofrecer sus productos para mascotas.

Entre sus principales actividades se encuentran:

* Registrar productos.
* Publicar productos en el marketplace.
* Actualizar información de productos.
* Administrar precios.
* Administrar stock.
* Recibir pedidos.
* Consultar sus ventas.

### 2.3 Administrador

Es el responsable de administrar y supervisar el funcionamiento general del marketplace.

Entre sus principales actividades se encuentran:

* Gestionar usuarios.
* Gestionar sellers.
* Supervisar productos.
* Gestionar categorías.
* Supervisar pedidos.
* Administrar la plataforma.

### 2.4 Área de distribución / logística

Representa el área encargada de las actividades relacionadas con la distribución de los productos vendidos.

Su participación y responsabilidades específicas deberán definirse con mayor detalle conforme se obtengan más requisitos del negocio.

## 3. Relación entre los actores

El funcionamiento general del sistema puede representarse de la siguiente manera:

```text
                         MARKETPLACE
                              │
              ┌───────────────┼───────────────┐
              │               │               │
           CLIENTE          SELLER       ADMINISTRADOR
              │               │               │
              │               │               │
          Consulta         Publica         Administra
          productos        productos       plataforma
              │               │               │
              └───────────────┼───────────────┘
                              │
                         PEDIDOS / VENTAS
                              │
                              ▼
                       DISTRIBUCIÓN
```

## 4. Resumen

El marketplace actuará como intermediario entre los clientes y diferentes sellers de productos para mascotas.

El cliente podrá consultar y adquirir productos, mientras que los sellers podrán ofrecer y administrar sus productos dentro de la plataforma. El administrador será responsable de supervisar y gestionar el funcionamiento general del sistema.
