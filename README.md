# 🚀 NEXUS-BAAS v2.0
### Client-Side Database Orchestrator & API Mocking Engine

> Una arquitectura de persistencia de datos que opera íntegramente en el navegador, eliminando la dependencia de servidores backend.

![React 19](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite 8](https://img.shields.io/badge/Vite-8-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![LocalStorage](https://img.shields.io/badge/Storage-LocalStorage-FF7A00?style=for-the-badge&logo=html5&logoColor=white)

---

## 🌐 Demo en Vivo y Recursos

- 🚀 **Despliegue en producción**: [nexus-baas-caja-pandora.netlify.app](https://nexus-baas-caja-pandora.netlify.app/)
- 📹 **Documentación del flujo y arquitectura**: [Ver Video Explicativo](https://drive.google.com/file/d/1GSHplP2jl3ZQSh4pryfonppCWrrK1j-G/view)
- 💻 **Repositorio**: [github.com/darwinjcn/nexus-bass-caja-pandora](https://github.com/darwinjcn/nexus-bass-caja-pandora)

---

## 📋 Descripción del Proyecto

**NEXUS-BAAS** (Backend as a Service) es un *Proof of Concept (PoC)* de una plataforma web progresiva que funciona como un orquestador de persistencia de datos del lado del cliente. En lugar de depender de un servidor externo o una base de datos en la nube, el sistema crea, gestiona y simula una **base de datos relacional completa** operando 100% dentro del navegador del usuario mediante `localStorage`.

El proyecto demuestra cómo se puede construir un flujo de desarrollo backend completo (**autenticación**, **definición de esquemas**, **mapeo relacional** y **consumo de APIs REST**) en un entorno aislado (Edge/Client-side), ideal para prototipados rápidos, desarrollo offline, o aplicaciones que requieran máxima privacidad de datos (*Zero-Knowledge*).

---

## 📸 Flujo de la Aplicación (UI/UX)

El sistema está diseñado bajo una arquitectura **SPA (Single Page Application)** con una estética *"Dark Mode"* de alto contraste orientada a terminales de desarrollo.

| Módulo de Autenticación | Panel de Control (Dashboard) |
| :---: | :---: |
| ![Autenticación](./assets/login-screen.png) | ![Dashboard](./assets/dashboard-screen.png) |

| Auditoría de Eventos (Logs) | Métricas de Almacenamiento |
| :---: | :---: |
| ![Logs](./assets/logs-screen.png) | ![Métricas](./assets/metrics-screen.png) |

| Motor de Simulación API REST | Editor Visual de Entidades (DDL) |
| :---: | :---: |
| ![API Mock](./assets/api-mock-screen.png) | ![Editor Esquema](./assets/schema-builder-screen.png) |

> 💡 *Nota: Reemplaza las rutas `./assets/...` con los nombres reales de tus capturas de pantalla en la carpeta `assets/`.*

---

## 🛠️ Stack Tecnológico

| Recurso | Especificación |
| :--- | :--- |
| **Lenguaje** | **JavaScript (ES6+)** |
| **Frontend** | **React 19** (Arquitectura basada en componentes funcionales y Hooks: `useState`, `useEffect`, `useRef`) |
| **Estilos** | **CSS Modules** (`*.module.css`) — Arquitectura libre de dependencias (*Zero CSS Frameworks*) |
| **Persistencia** | **localStorage** (Web Storage API) simulando un motor relacional reactivo bajo la clave `nexus_datastore` |
| **Build Tool** | **Vite 8** |
| **Entorno** | Navegadores modernos (Chromium-based, Firefox, Edge) / Node.js v20+ |

---

## 🏗️ Arquitectura y Decisiones de Diseño

- **Gestión de Estado**: Se utilizó un enrutamiento interno basado en el estado de React (variable `screen`) en lugar de librerías externas como *React Router*, manteniendo el *bundle* extremadamente **ligero y optimizado**.
- **Motor de Datos**: El archivo `datastore.js` actúa como un **ORM/Controlador básico** que abstrae la lectura/escritura de JSON en el `localStorage`, permitiendo operaciones tipo **CRUD** y resolución de claves foráneas en tiempo de ejecución.
- **Diseño UI**: Interfaz tipo *"IDE/Terminal"* utilizando una paleta de colores oscura (`#0d1117`), con acentos en **cian neón** (`#00F2FE`) para estados activos y **verde neón** (`#39FF14`) para outputs exitosos.

---

## 🧩 Módulos Principales Desarrollados

- 🔐 **Auth Module**: Sistema de inicio de sesión local con validación de credenciales contra el *datastore* y simulación de latencia de red (1.5s).
- 📊 **Dashboard & Telemetría**: Panel centralizado mostrando nodos activos, logs de auditoría del sistema, **métricas en tiempo real** (conteo de tablas, registros, peso en KB) y gestión de tokens de encriptación simulados.
- 🗄️ **Schema Builder (DDL Client)**: Interfaz para definir la estructura arquitectónica de la base de datos directamente en el navegador (creación de tablas, asignación de tipos de datos `VARCHAR`/`INTEGER`/`BOOLEAN`, definición de *Primary Keys* y *Foreign Keys*).
- ⚡ **API Mocking Engine**: Generador automático de *endpoints* REST (`GET`, `POST`, `PUT`, `DELETE`) por cada tabla creada. Incluye simulación de latencia (500ms), **resolución de relaciones** (mostrar el nombre de un autor en lugar de su ID) y exportación del diccionario de datos a un archivo `.json` descargable.
- 🛡️ **Resilience Console**: Emulador de terminal *Bash* que ejecuta un script asíncrono de 12 pasos, demostrando cómo la aplicación asegura los datos ante una simulación de desconexión de red.

---

## 🚀 Ejecución Local

Sigue estos pasos para levantar el proyecto en tu entorno de desarrollo:

```bash
# 1. Clonar el repositorio
git clone https://github.com/darwinjcn/nexus-bass-caja-pandora.git

# 2. Navegar al directorio del proyecto
cd nexus-bass-caja-pandora

# 3. Instalar dependencias
npm install

# 4. Levantar servidor de desarrollo
npm run dev

# 5. Compilar para producción
npm run build
```

---

## 📁 Estructura del Proyecto

```
nexus-bass-caja-pandora/
├── index.html                  # Punto de entrada HTML
├── package.json                # Dependencias y scripts
├── vite.config.js              # Configuración de Vite
├── assets/                     # Recursos estáticos (Capturas de pantalla)
├── src/
│   ├── main.jsx                # Punto de entrada React
│   ├── index.css               # Estilos globales y reset
│   ├── App.jsx                 # Componente raíz (Orquestador de rutas)
│   ├── App.module.css          # Estilos del componente raíz
│   ├── utils/
│   │   └── datastore.js        # Abstracción de la base de datos en localStorage
│   └── components/
│       ├── LoginScreen.jsx
│       ├── DashboardScreen.jsx
│       ├── SchemaBuilderScreen.jsx
│       ├── EthicalCheckpointScreen.jsx
│       ├── ApiMockScreen.jsx
│       ├── TerminalScreen.jsx
│       └── ... (Módulos CSS asociados)
```

---

## 📜 **Licencia**

Este proyecto es un *Proof of Concept* desarrollado con fines educativos y de investigación. **No está diseñado para uso en producción** sin adaptaciones adicionales.

> ⚠️ **Advertencia**: El uso de `localStorage` como base de datos tiene limitaciones (ej. 5MB por dominio, solo datos en formato string). Para aplicaciones reales, considera bases de datos como **IndexedDB** o soluciones *offline-first* como **PouchDB**.

---

## 🤝 **Contribuciones**

Las contribuciones son bienvenidas. Para colaborar:
1. Haz un *fork* del repositorio.
2. Crea una rama para tu funcionalidad (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz *commit* (`git commit -m "Añade nueva funcionalidad"`).
4. Envía un *Pull Request* a la rama `main`.

---

## 📞 **Contacto**

Para preguntas o sugerencias, abre un *issue* en el [repositorio](https://github.com/darwinjcn/nexus-baas-caja-pandora/issues) o contacta al equipo.

---

**Desarrollado con 💚 por el equipo de NEXUS-BAAS**