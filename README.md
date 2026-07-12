# NEXUS-BAAS v2.0 — Orquestador Soberano de Persistencia Local

**Actividad Misión 2.0** — Unidad Curricular: **Formación Sociocrítica III**  
**PNF en Informática** — Universidad Nacional Experimental de las Telecomunicaciones e Informática (UNETI)

---

## 📋 Descripción del Proyecto

NEXUS-BAAS v2.0 (Backend As A Service) es una plataforma web progresiva que funciona como un orquestador de persistencia de datos completamente local, operando dentro del navegador del usuario. Fue diseñada bajo principios de **infraestructura inmune, soberanía tecnológica y resiliencia territorial**, permitiendo la gestión simulada de bases de datos relacionales distribuidas sin depender de servidores externos ni conexiones a Internet.

El sistema implementa un flujo completo de 6 pantallas interactivas que abarcan desde la autenticación local hasta la simulación de contingencias de red, pasando por la construcción visual de esquemas de bases de datos, control ético de arquitectura, simulación de APIs REST y consola de resiliencia.

---

## 🛠️ Lenguajes y Tecnologías Utilizadas

| Recurso | Especificación |
|---|---|
| **Lenguaje** | JavaScript (ES6+) |
| **Framework Frontend** | React 19 con componentes funcionales y Hooks (`useState`, `useEffect`, `useRef`) |
| **Lenguaje de Estilos** | CSS Modules (`*.module.css`) — sin frameworks corporativos ni Tailwind |
| **Entorno de Ejecución** | Navegador web (Chromium-based, Firefox, Edge) |
| **Persistencia** | `localStorage` del navegador (API Web Storage) |
| **Herramienta de Build** | Vite 8 |
| **Node.js** | v20+ (entorno de desarrollo) |
| **Control de Versiones** | Git |

### Metodología de Desarrollo

- **Arquitectura**: Basada en componentes funcionales de React con estado global centralizado mediante hooks de estado (`useState`). La navegación entre pantallas se controla mediante una variable de estado `screen` que determina qué componente se renderiza.
- **Persistencia**: Toda la base de datos relacional se simula y opera de forma reactiva utilizando el `localStorage` del navegador, con una estructura JSON única bajo la clave `nexus_datastore`.
- **Diseño Visual**: "Dark Mode" con paleta de colores de alto contraste: fondo `#0d1117`, contenedores `#161b22`, texto y bordes activos en cian `#00F2FE`, alertas en verde neón `#39FF14` y advertencias en naranja `#FF9F00`. Tipografía monoespaciada.
- **Estilos**: Aislamiento completo de estilos mediante CSS Modules, garantizando que no haya conflictos entre componentes y que la interfaz sea ultraligera.

---

## 🧩 ¿Qué se Programó?

Se desarrolló una aplicación web de página única (SPA) compuesta por **6 pantallas interactivas**, cada una con su propia lógica de estado, persistencia en localStorage e interfaz de usuario:

### Pantalla 1 — Autenticación Soberana
Formulario de inicio de sesión con credenciales precargadas (`demo@uneti.edu.ve` / `demo1234`), botón con estado de verificación simulado (1.5 segundos) y bloque manifiesto político-técnico con valores de infraestructura inmune.

### Pantalla 2 — Panel Central de Gestión (Dashboard)
Sidebar con lista dinámica de nodos/proyectos activos, herramientas de: Registro de Eventos (10 logs simulados de auditoría local), Métricas de Almacenamiento (conteo de tablas, registros totales y espacio estimado), Llaves Simétricas de Encriptación (generación y regeneración de token AES-256). Modal para crear nuevos nodos de persistencia local. Botón de limpieza de bases de datos usuario (preserva la base semilla). Cierre de sesión.

### Pantalla 3 — Constructor Visual de Entidades (Esquemas)
Editor de metadatos puros donde el usuario define la estructura arquitectónica de tablas y columnas (nombre, tipo VARCHAR/INTEGER/BOOLEAN, clave primaria, nullable, clave foránea con selección de tabla y campo referenciado). Creación de nuevas tablas personalizadas. Persistencia del esquema relacional en localStorage.

### Pantalla 4 — Alcabala de Control Ético y Mapeo
Diagrama de relaciones y llaves foráneas del proyecto activo. Tres checkboxes de auditoría de soberanía que deben marcarse para liberar la transición. Estado reactivo: naranja bloqueado / verde liberado.

### Pantalla 5 — Servidor de Simulación de APIs (Mock)
Lista de endpoints CRUD autogenerados por tabla (`GET`, `POST`, `PUT`, `DELETE`). Ejecución simulada con 500ms de latencia que renderiza los datos reales del localStorage en formato JSON. Resolución de claves foráneas: los registros muestran los valores display de las tablas referenciadas (ej: título del libro en lugar del ID numérico). Descarga soberana del diccionario de datos en archivo `.json` físico mediante el API Blob del navegador.

### Pantalla 6 — Consola de Resiliencia Territorial
Terminal emulada tipo Linux bash que ejecuta una cascada asíncrona de 12 eventos simulando una contingencia de desconexión internacional y el resguardo de datos en almacenamiento local. Botón de retorno seguro al panel central.

---

## 📦 Datos Semilla

La aplicación se inicializa automáticamente con una base de datos relacional de ejemplo para la **"Sistema de Gestión de Biblioteca Personal"**, que incluye:

- **10 libros** de autores latinoamericanos (Rómulo Gallegos, Gabriel García Márquez, Juan Rulfo, Jorge Luis Borges, Julio Cortázar, Mario Vargas Llosa, etc.)
- **5 usuarios** con datos de contacto y ubicación geográfica
- **12 préstamos** con fechas entre el 15 de mayo y 22 de junio de 2026, relacionando usuarios y libros mediante claves foráneas

---

## 🚀 Instrucciones de Ejecución

```bash
# Instalar dependencias
npm install

# Ejecutar en modo desarrollo
npm run dev

# Compilar para producción
npm run build

# Vista previa de la compilación
npm run preview
```

---

## 📁 Estructura del Proyecto

```
nexus_v1/
├── index.html                  # Punto de entrada HTML
├── package.json                # Dependencias y scripts
├── vite.config.js              # Configuración de Vite
├── src/
│   ├── main.jsx                # Punto de entrada React
│   ├── index.css               # Estilos globales
│   ├── App.jsx                 # Componente raíz (orquestador de pantallas)
│   ├── App.module.css          # Estilos del componente raíz
│   ├── utils/
│   │   └── datastore.js        # Inicialización, consulta y mutación de localStorage
│   └── components/
│       ├── LoginScreen.jsx / .module.css
│       ├── DashboardScreen.jsx / .module.css
│       ├── SchemaBuilderScreen.jsx / .module.css
│       ├── EthicalCheckpointScreen.jsx / .module.css
│       ├── ApiMockScreen.jsx / .module.css
│       ├── TerminalScreen.jsx / .module.css
│       ├── Modal.jsx / .module.css
│       └── ... (módulos de estilo asociados)
```

---

## 👥 Equipo de Desarrollo

Proyecto desarrollado como parte de la Unidad Curricular **Formación Sociocrítica III** del PNF en Informática, promoviendo el uso de tecnologías libres, soberanía tecnológica y arquitecturas de software resilientes para infraestructuras nacionales.
Integrantes:
Diana Sierra, Ana Contreras, Darwin Colmenares y Yolimar Ramos
