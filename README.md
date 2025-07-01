# MultiSport Arena - Sistema de Reservas Deportivas

Sistema web para la gestión y reserva de canchas deportivas (Fútbol, Tenis y Pádel) desarrollado con Flask y dockerizado para fácil despliegue.

## 🏟️ Características

- **Reserva de canchas**: Sistema de reservas por horarios para diferentes deportes
- **Gestión de usuarios**: Registro, login y roles (Cliente/Administrador)
- **Panel administrativo**: ABM completo de usuarios, canchas y reservas
- **Sistema de pagos simulado**: Validación de tarjetas para completar reservas
- **Interfaz responsive**: Diseño adaptable con Bootstrap
- **Base de datos SQLite**: Persistencia de datos integrada

## 🚀 Instalación y Ejecución con Docker

### Prerrequisitos
- Docker Desktop instalado en tu sistema
- Git (para clonar el repositorio)

### Pasos de instalación

1. **Clonar el repositorio**
   \`\`\`bash
   git clone <url-del-repositorio>
   cd MultiSport-Arena
   \`\`\`

2. **Crear directorio para datos persistentes**
   \`\`\`bash
   mkdir data
   \`\`\`

3. **Construir y ejecutar con Docker Compose**
   \`\`\`bash
   # Construir la imagen
   docker-compose build
   
   # Ejecutar el contenedor
   docker-compose up
   \`\`\`

4. **Acceder a la aplicación**
   - Abrir navegador en: \`http://localhost:5000\`


## 👥 Usuarios por Defecto

### Usuario Cliente
- **Email**: \`juan@example.com\`
- **Contraseña**: \`contrasena123\`
- **Permisos**: Hacer reservas, ver mis reservas

### Usuario Administrador
- **Email**: \`admin@example.com\`
- **Contraseña**: \`admin123\`
- **Permisos**: Acceso completo al panel ABM

## 💳 Datos de Prueba para Pagos

El sistema incluye un simulador de pagos. Usa estos datos para testing:

### Tarjeta VISA
- **Número**: \`4111 1111 1111 1111\`
- **Vencimiento**: \`12/25\`
- **CVC**: \`123\`

### Tarjeta MasterCard
- **Número**: \`5555 5555 5555 4444\`
- **Vencimiento**: \`06/26\`
- **CVC**: \`456\`

> ⚠️ **Nota**: El sistema de pagos es solo una simulación. No se procesan pagos reales.

## 🎯 Cómo Usar la Aplicación

### Para Clientes:

1. **Registro/Login**
   - Crear cuenta nueva o usar credenciales de prueba
   - Acceder desde el ícono de usuario en la esquina superior derecha

2. **Hacer una Reserva**
   - Seleccionar tipo de deporte en la página principal
   - Elegir fecha y horario disponible (verde = disponible)
   - Completar datos de pago simulado
   - Confirmar reserva

3. **Ver Mis Reservas**
   - Acceder desde el menú "Mis Reservas"
   - Ver historial de reservas realizadas

### Para Administradores:

1. **Acceder al Panel ABM**
   - Login con credenciales de administrador
   - Usar el menú "Panel ABM"

2. **Gestión de Usuarios**
   - Ver todos los usuarios registrados
   - Cambiar roles (Cliente ↔ Administrador)

3. **Gestión de Canchas**
   - Crear nuevas canchas
   - Modificar canchas existentes
   - Eliminar canchas
   - Establecer precios

4. **Gestión de Reservas**
   - Ver todas las reservas del sistema
   - Eliminar reservas si es necesario

## 🏗️ Estructura del Proyecto

\`\`\`
MultiSport-Arena/
├── app.py                 # Aplicación principal Flask
├── Dockerfile            # Configuración Docker
├── docker-compose.yml    # Orquestación de contenedores
├── requirements.txt      # Dependencias Python
├── controlador/          # Lógica de autenticación
├── modelo/              # Modelos de datos y BD
├── static/              # Archivos estáticos (CSS, JS, imágenes)
├── templates/           # Plantillas HTML
└── data/               # Base de datos persistente (creado automáticamente)
\`\`\`

## 🔧 Tecnologías Utilizadas

- **Backend**: Flask (Python)
- **Base de Datos**: SQLite
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Contenedores**: Docker & Docker Compose
- **Autenticación**: Werkzeug Security

## 📱 Funcionalidades Principales

### Sistema de Reservas
- Calendario interactivo por deporte
- Estados visuales: Disponible (verde), Reservado (rojo), Pasado (gris)
- Validación de horarios y fechas
- Integración con sistema de pagos simulado

### Panel Administrativo
- CRUD completo para usuarios, canchas y reservas
- Control de roles y permisos
- Estadísticas y gestión centralizada

### Seguridad
- Autenticación basada en sesiones
- Validación de permisos por rol
- Protección de rutas administrativas
