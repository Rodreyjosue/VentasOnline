# PROGRAMACIÓN 2 - PROYECTO FINAL
## Documentación del Proyecto: Sistema de Ventas Online

Este proyecto consiste en el desarrollo de un sistema de ventas en línea utilizando **Java 17**, **Spring Framework**, **React** y **MongoDB**. A continuación se presentan dos secciones clave: el **Manual de Usuario**, dirigido a los usuarios finales, y el **Manual Técnico**, para desarrolladores y personal técnico.

---

## Manual de Usuario

El **Manual de Usuario** guía a los usuarios finales en el uso de las funcionalidades clave del sistema de ventas online.

### Registro de Usuarios
- Los usuarios pueden registrarse como clientes o administradores, ingresando información básica como **nombre**, **correo electrónico** y **contraseña**.
- Una vez registrado, el usuario tendrá acceso a las funcionalidades del sistema.

![image](https://github.com/user-attachments/assets/602d5710-18ea-4e75-b367-d9344826b35b)

![image](https://github.com/user-attachments/assets/57b1f116-69f2-4d4e-bace-58dec9305838)


### Inicio de Sesión
- Los usuarios pueden iniciar sesión con sus credenciales para acceder a su perfil y funcionalidades personalizadas.

![image](https://github.com/user-attachments/assets/540ef9c6-0332-4b16-9fd0-4b6fd79f0910)


### Gestión del Carrito de Compras
- Los clientes pueden **agregar productos al carrito**, revisar su contenido, modificar las cantidades y proceder al pago.

![image](https://github.com/user-attachments/assets/40b68c00-b24b-42e3-a599-6b01a3c65ea1)

![image](https://github.com/user-attachments/assets/151adfc3-3f32-40d7-b379-41a20a3b0fa1)


### Opciones de Pago
- El sistema permite pagos mediante **tarjetas de crédito/débito** y **depósitos**. También puede incluir la opción de **PayPal**.

![image](https://github.com/user-attachments/assets/42471c9e-3e23-490e-a5d8-32d916f638dc)


### Historial de Transacciones
- Los usuarios pueden consultar su historial de compras, con detalles de cada transacción realizada

![image](https://github.com/user-attachments/assets/7ed986a0-02cc-4705-a2c3-9e4c9964d475)

### Reportes para Administradores
- Los administradores tienen acceso a reportes, tales como:
  - **Existencia de Artículos**: Búsqueda de artículos por ID y detalles de inventario.
  - **Pedidos y Ventas**: Reportes filtrables por ID de transacción.
  - **Histórico de Transacciones**: Filtro de transacciones por ID de cliente.

![image](https://github.com/user-attachments/assets/262962c2-86f8-4248-b6c3-c3cc9c5ae86c)

![image](https://github.com/user-attachments/assets/045547ba-b3c9-47df-a62c-fbc43f5b82de)


---

## Manual Técnico

Este manual abarca la **configuración técnica y funcionalidad** del sistema, diseñado como una **API RESTful** con **Spring Framework** en el backend y una **aplicación en React** para el frontend.

### Requisitos Técnicos
- **Java 17**
- **Spring Framework**
- **MongoDB**
- **React**
- **Node.js** y **npm** (para la gestión del frontend)

### Arquitectura del Sistema

#### Backend
1. **Controladores**: Gestionan peticiones HTTP para funcionalidades de **mantenimiento y reportes**.
2. **Servicios**: Procesan reglas de negocio como **creación, edición y eliminación de empresas, contactos, categorías y artículos**.
3. **Repositorios**: Interactúan con MongoDB para la persistencia de datos.

#### Frontend
1. **Componentes React**: Interfaz de usuario organizada en componentes modulares, incluyendo administración y vista de cliente.
2. **Bootstrap** y **react-icons**: Utilizados para estilizar la interfaz y mejorar la experiencia del usuario.

### Configuración del Entorno de Desarrollo
1. **Instalación de MongoDB**: Configuración de la base de datos con colecciones de empresas, categorías, artículos, usuarios y transacciones.
2. **Configuración de Variables de Entorno**: En el archivo `.env`, especificar los parámetros de conexión para MongoDB y ajustes del servidor.
3. **Instalación de Dependencias**: Ejecute `npm install` para el frontend y `mvn install` para el backend.

### Estructura de Colecciones en MongoDB
- **Empresas**: Incluye nombre, contacto y datos relevantes.
- **Categorías y Subcategorías**: Relacionadas jerárquicamente para la creación de artículos.
- **Artículos**: Incluye detalles de **stock, marca** y referencias de **categorías y subcategorías**.
- **Usuarios**: Almacena información de inicio de sesión y roles.
- **Pedidos y Movimientos**: Guarda transacciones para la generación de reportes.

### Generación de Reportes
1. **Función PDF**: Exporta reportes visualizados en el sistema mediante bibliotecas de generación de PDF.
2. **Filtrado de Reportes**: Configurado en el frontend y enviado como parámetros al backend para consultas en MongoDB.

### Seguridad y Roles de Usuario
1. **Roles de Usuario**: `Cliente` con acceso limitado y `Administrador` con acceso completo.
2. **Autenticación**: Manejo de sesiones mediante **tokens de acceso** en rutas protegidas.

### Configuración del Entorno

Asegúrese de tener instalados:
- **Java 17**
- **MongoDB**
- Un IDE compatible (ej. Visual Stucio Code o IntelliJ).

### Despliegue del Sistema

1. **Clonar el repositorio** desde GitHub.
2. **Configurar `application.properties`** con los parámetros de conexión a MongoDB:
   ```properties
   spring.application.name=ventas_online
    spring.data.mongodb.uri=mongodb+srv://grupoproyectofinalpruebas:HNCVX96fpICJQK3R@ventasonline.gtvpi.mongodb.net/VentasOnline?retryWrites=true&w=majority
    server.port=8080
   ```
3. **Ejecutar el backend** con el comando:
   ```bash
   mvn spring-boot:run
   ```
4. **Ejecutar el frontend** con:
   ```bash
   npm start
   ```

### Pruebas Funcionales
- Se recomienda el uso de **Postman** para pruebas de las APIs, verificando la creación, lectura, actualización y eliminación (CRUD) de usuarios, productos y pedidos.
