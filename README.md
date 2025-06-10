# SoftwareFinal
📊 Sistema de Estadísticas para Proyectos Académicos
Este proyecto forma parte del curso Software 2 y consiste en la implementación de un microservicio independiente que permite visualizar estadísticas de proyectos académicos (postulados, aprobados, rechazados, terminados) mediante gráficos de barras y pastel. La solución aplica principios modernos de diseño y arquitectura de software orientados a la industria.

📌 Requisito Funcional Principal
YO COMO coordinador NECESITO visualizar gráficas estadísticas en barras y pastel sobre cantidad de proyectos postulados, aprobados, rechazados y terminados en un período académico PARA tener un control estadístico.

⚙️ Tecnologías Utilizadas
Backend: 
1. Java 17
2. Spring Boot 3.x
3. Maven
4. PostgreSQL (persistencia en un microservicio)
5. H2 / SQLite (bases en memoria para otros microservicios)
6. JWT / Keycloak (autenticación y autorización)
7. Docker & Docker Compose

Frontend:
1. ReactJS
2. Chart.js / Recharts (visualización de gráficos)
3. Axios (comunicación HTTP)
4. Context API + Hooks

Otros:
1. API Gateway (opcional)
2. Swagger/OpenAPI (documentación de APIs)
3. Lombok (reducción de boilerplate)
4. MapStruct (mapeo de DTOs)
5. ModelMapper / JPA

🧱 Arquitectura del Proyecto
Este sistema adopta la arquitectura hexagonal (puertos y adaptadores) con orientación a Domain-Driven Design (DDD), separando claramente la lógica del dominio de los detalles de infraestructura y frameworks.

Componentes clave:
Capa de Dominio: Entidades, agregados y lógica de negocio.

Puertos (Interfaces): Contratos de entrada y salida.

Adaptadores:
1. Entrada: Controladores REST (Spring Boot)
2. Salida: Persistencia con JPA, Repositorios PostgreSQL / H2

Infraestructura: Configuración de seguridad, autenticación JWT, Docker, etc.

🧩 Se aplican al menos seis patrones de diseño a lo largo del sistema, incluyendo:
1. Singleton
2. Strategy
3. Adapter
4. Factory Method
5. Repository
6. Builder

🔐 Seguridad
El sistema implementa autenticación y autorización basada en JWT, con dos esquemas disponibles:
1. Manual: Generación y validación de tokens directamente desde el backend.
2. Integración con Keycloak: Gestión externa de identidad. Spring Boot valida los tokens emitidos.

🐳 Dockerización
Todos los microservicios están dockerizados y orquestados mediante Docker Compose. Un microservicio principal (estadísticas) persiste datos usando PostgreSQL con un volumen Docker que asegura durabilidad.
Los otros microservicios utilizan bases de datos en memoria (H2 o SQLite) para facilitar desarrollo y pruebas.

📁 Estructura del Repositorio
bash
Copiar
Editar
📦 stats-project/
├── api-gateway/              # API Gateway (opcional)
├── statistics-service/       # Microservicio con lógica de dominio (arquitectura hexagonal)
│   ├── domain/
│   ├── application/
│   ├── infrastructure/
│   └── adapters/
├── auth-service/             # Autenticación (manual o Keycloak)
├── frontend/                 # Aplicación React
├── docker-compose.yml
├── README.md
└── docs/
    └── arquitectura.pdf      # Documento final con la arquitectura del sistema
    
📄 Documentación Técnica
La documentación detallada de la arquitectura, decisiones de diseño, diagrama de despliegue, modelos de dominio y flujos de autenticación se encuentra a continuación:
https://docs.google.com/document/d/1fAb68_fE2BmldnjrMkHxUDUPMghQMMlG/edit

👨‍💻 Créditos
Desarrollado por estudiantes del curso Ingeniería de Software 2
Universidad del Cauca - Departamento de Ingeniería de Sistemas
Semestre 2025-I

