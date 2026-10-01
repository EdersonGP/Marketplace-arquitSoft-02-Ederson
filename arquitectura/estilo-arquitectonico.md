## Imagen del estilo arquitectónico

flowchart TD

    A["Cliente / Comerciante / Repartidor / Administrador"]
    B["Aplicación Web / PWA<br/>Next.js + TypeScript"]
    C["API REST<br/>NestJS + TypeScript"]

    subgraph M["MONOLITO MODULAR"]
        U["Usuarios"]
        P["Productos"]
        I["Inventario"]
        CA["Carrito"]
        PE["Pedidos"]
        R["Repartidores"]
        PA["Pagos"]
        D["Delivery"]
    end

    DB["PostgreSQL / Supabase"]
    EXT["Servicios externos"]

    A --> B
    B --> C
    C --> U
    C --> P
    C --> I
    C --> CA
    C --> PE
    C --> R
    C --> PA
    C --> D

    U --> DB
    P --> DB
    I --> DB
    CA --> DB
    PE --> DB
    R --> DB
    PA --> DB

    PA -.-> EXT