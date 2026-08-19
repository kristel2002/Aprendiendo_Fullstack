# Aprendiendo_Fullstack
En este repositorio intentare aprender fullstack siguiendo 
buenas practicas utilizando inteligencia artificial y lo que 
aprendido y aprendere, ya que en este mundo no dejas de aprender

El patrón clásico MVC/Arquitectura por Tipo de Archivo (controllers, models, routes, components, etc.). Para proyectos pequeños o demos funcionan bien

En proyectos reales y medianos/grandes terminan volviéndose difíciles de mantener.  Para aplicar buenas prácticas de un desarrollador Senior/Fullstack, la mejor alternativa es migrar a una Arquitectura por Módulos / Dominio (Feature-based architecture).

##  Estructura del Proyecto

```text
my-app/
├── client/                     # App de Frontend (React / Vite / Next.js)
│   ├── src/
│   │   ├── assets/             # Recursos estáticos (imágenes, fuentes, estilos globales)
│   │   ├── components/         # Componentes UI globales/reutilizables (Button, Input, Modal)
│   │   ├── config/             # Configuración de cliente (instancia Axios, constantes)
│   │   ├── hooks/              # Custom Hooks globales (useTheme, useWindowSize)
│   │   ├── modules/            #  NÚCLEO DE DOMINIO / FEATURES (Feature-Based)
│   │   │   ├── auth/           # Módulo de Autenticación
│   │   │   │   ├── components/ # Componentes exclusivos del módulo (LoginForm, RegisterForm)
│   │   │   │   ├── hooks/      # Hooks específicos (useAuth)
│   │   │   │   ├── pages/      # Páginas/Vistas del módulo (LoginPage, RegisterPage)
│   │   │   │   └── services/   # Peticiones API del módulo (authApi.ts)
│   │   │   └── products/       # Módulo de Productos
│   │   │       ├── components/ # ProductCard, ProductList
│   │   │       ├── pages/      # ProductsPage, ProductDetailPage
│   │   │       └── services/   # productApi.ts
│   │   ├── routes/             # Configuración centralizada de rutas y navegación
│   │   ├── types/              # Interfaces y tipos globales de TypeScript
│   │   ├── utils/              # Funciones auxiliares puras (formatters, validators)
│   │   ├── App.tsx             # Proveedores globales y layout base
│   │   └── main.tsx            # Punto de entrada de React
│   ├── .env.example            # Variables de entorno requeridas para el cliente
│   └── package.json
│
├── server/                     # App de Backend (Node.js / Express / Fastify)
│   ├── src/
│   │   ├── config/             # Configuración del servidor (variables env, conexión a DB)
│   │   ├── middlewares/        # Middlewares globales (Auth guard, Error handling, Rate limiting)
│   │   ├── modules/            #  NÚCLEO DE DOMINIO / FEATURES (Feature-Based)
│   │   │   ├── auth/           # Lógica del módulo de autenticación
│   │   │   │   ├── auth.controller.ts # Manejo de Request/Response
│   │   │   │   ├── auth.routes.ts     # Definición de endpoints
│   │   │   │   ├── auth.schema.ts     # Validaciones de entrada (Zod / Joi)
│   │   │   │   └── auth.service.ts    # Lógica de negocio e integración
│   │   │   └── users/          # Lógica del módulo de usuarios
│   │   │       ├── user.controller.ts
│   │   │       ├── user.model.ts      # Modelo de base de datos (Prisma / Mongoose / ORM)
│   │   │       ├── user.routes.ts
│   │   │       └── user.service.ts
│   │   ├── utils/              # Helpers compartidos (logger, token generator)
│   │   ├── app.ts              # Configuración de Express/Fastify
│   │   └── server.ts           # Inicialización y escucha del servidor
│   ├── .env.example            # Variables de entorno requeridas para el servidor
│   └── package.json
│
├── .gitignore                  # Archivos excluidos del control de versiones
└── README.md
