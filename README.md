
# Moda Infantil — Tienda Virtual y Sistema de Gestión

## Descripción del proyecto

Moda Infantil es una aplicación web desarrollada para administrar una tienda de ropa infantil, permitiendo gestionar productos, categorías, inventario, usuarios, pedidos y ventas desde una misma plataforma.

El proyecto cuenta con una tienda virtual para los clientes y un panel administrativo privado para gestionar las operaciones del negocio.

Su objetivo es digitalizar los procesos comerciales de una tienda infantil, facilitar el control del inventario y ofrecer a los clientes una experiencia de compra moderna, sencilla y segura.

El sistema utiliza una base de datos real en Supabase y está desarrollado con tecnologías modernas de desarrollo web.

---

##  Tecnologías utilizadas

### Frontend
- React
- TypeScript
- Vite
- Tailwind CSS
- React Router
- Lucide React

### Backend y base de datos
- Supabase
- PostgreSQL
- Supabase Authentication
- Supabase Storage
- Funciones SQL (RPC)
- Row Level Security (RLS)

### Librerías adicionales
- TanStack Query
- React Hook Form
- Zod
- Recharts

### Herramientas de desarrollo
- Visual Studio Code
- Git y GitHub
- Node.js
- npm
- Supabase Dashboard

---

##  Diseño de la aplicación

Se desarrolló una identidad visual moderna, profesional y adaptada a una tienda de ropa infantil.

### Colores principales

- Rojo principal: #E53935
- Rojo oscuro: #C62828
- Blanco: #FFFFFF
- Rosa suave: #FFEBEE
- Gris claro: #F5F5F5
- Texto oscuro: #292929

### Características del diseño

- Interfaz moderna y organizada.
- Diseño adaptable a celulares, tabletas y computadores.
- Navegación intuitiva.
- Botones e iconos modernos.
- Tarjetas de productos.
- Formularios organizados.
- Mensajes de confirmación y error.
- Panel administrativo con menú lateral.
- Identidad visual uniforme.

---

#  FASE 1 — Autenticación, usuarios y seguridad

Durante la primera fase se desarrolló la estructura principal del proyecto y su conexión con Supabase.

## Funcionalidades implementadas

### Autenticación

- Registro de usuarios.
- Inicio de sesión mediante correo y contraseña.
- Cierre de sesión.
- Recuperación de contraseña.
- Gestión básica del perfil.
- Preparación de autenticación mediante Google.

### Roles de usuario

Se establecieron cinco roles:

**Administrador**
- Administración general del sistema.
- Gestión de productos e inventario.
- Gestión de empleados.
- Administración de pedidos.
- Acceso a las configuraciones autorizadas.

**Supervisor**
- Supervisión de las operaciones autorizadas.
- Consulta de productos, pedidos e inventario.

**Cajero**
- Rol preparado para operaciones de caja y ventas presenciales.

**Encargado de inventario**
- Administración autorizada de productos.
- Gestión de variantes y existencias.
- Registro de movimientos de inventario.

**Cliente**
- Acceso a la tienda virtual.
- Consulta de productos.
- Gestión del carrito.
- Consulta de sus pedidos.

### Seguridad

- Autenticación mediante Supabase Auth.
- Protección de rutas privadas.
- Control de permisos por rol.
- Políticas RLS en PostgreSQL.
- Restricción de operaciones administrativas.
- Prevención de asignación no autorizada de roles.
- Separación de credenciales públicas y secretas.

### Resultado

Se creó un panel administrativo con inicio de sesión y permisos conectados a Supabase.

---

#  FASE 2 — Productos, categorías e inventario

En esta fase se implementaron los módulos necesarios para administrar el catálogo y controlar las existencias de los productos.

## Gestión de categorías

- Crear categorías.
- Consultar categorías.
- Editar información.
- Activar y desactivar categorías.
- Eliminar categorías cuando esté permitido.
- Agregar imágenes.
- Buscar categorías.

### Categorías iniciales

- Ropa para niña.
- Ropa para niño.
- Ropa para bebé.
- Conjuntos infantiles.
- Vestidos.

## Gestión de productos

Se desarrolló un sistema CRUD para:

- Registrar productos.
- Editar productos existentes.
- Consultar información.
- Buscar por nombre o referencia.
- Organizar por categorías.
- Configurar precios.
- Registrar precios anteriores.
- Administrar imágenes.
- Activar o desactivar productos.
- Administrar variantes.
- Consultar existencias.

### Información de un producto

- Nombre.
- Descripción.
- Categoría.
- Precio de venta.
- Precio anterior.
- SKU o referencia.
- Fotografías.
- Estado de visibilidad.
- Variantes disponibles.

## Tallas y colores

Se implementó un módulo para administrar las opciones disponibles.

### Tallas

Incluye tallas infantiles como:

0-3M, 3-6M, 6-12M, 12-18M, 2, 4, 6, 8, 10, 12, 14, 16 y Única.

### Colores

Incluye amarillo, azul, blanco, gris, negro, rojo, rosa y verde.

También permite registrar nuevas tallas y colores.

## Variantes de productos

Cada producto puede tener diferentes combinaciones de talla y color.

Ejemplo:

| Producto | Talla | Color | Existencias |
|---|---|---|---|
| Camiseta infantil | 4 | Rojo | 10 |
| Camiseta infantil | 4 | Blanco | 5 |
| Camiseta infantil | 6 | Azul | 8 |

Cada combinación tiene un SKU y existencias independientes.

## Gestión de inventario

- Consultar existencias.
- Registrar entradas.
- Registrar salidas.
- Ajustar cantidades.
- Consultar movimientos.
- Identificar al responsable.
- Registrar motivos de ajustes.
- Configurar alertas por existencias bajas.
- Impedir cantidades negativas.

## Corrección realizada

Se corrigió la gestión de variantes para separar dos operaciones:

**Editar datos:** permite modificar talla, color, SKU, precio especial y alerta de existencias.

**Cambiar unidades:** permite aumentar o disminuir el inventario sin crear una nueva variante.

Los movimientos conservan su historial en Supabase.

También se corrigió la navegación del formulario de creación de productos.

---

#  FASE 3 — Tienda virtual pública

Se desarrolló la interfaz pública de Moda Infantil para que los clientes puedan explorar el catálogo.

## Página principal

La portada incluye:

- Encabezado con identidad visual.
- Menú de navegación.
- Buscador de productos.
- Secciones comerciales.
- Categorías destacadas.
- Productos nuevos.
- Productos destacados.
- Ofertas.
- Banners promocionales.
- Acceso al carrito.
- Acceso a favoritos.
- Información del almacén.
- Pie de página.

## Catálogo de productos

Los clientes pueden:

- Explorar productos disponibles.
- Buscar por nombre.
- Filtrar productos.
- Consultar categorías.
- Consultar precios.
- Visualizar fotografías.
- Acceder al detalle de cada producto.

## Detalle de producto

La página de cada producto muestra:

- Nombre.
- Descripción.
- Precio.
- Precio anterior, cuando exista.
- Fotografías.
- Tallas disponibles.
- Colores disponibles.
- Existencias de la variante.
- Opción para agregar al carrito.

## Carrito de compras

Se implementó un carrito para:

- Agregar productos.
- Seleccionar variantes.
- Modificar cantidades.
- Eliminar artículos.
- Vaciar el carrito.
- Calcular subtotales.
- Conservar temporalmente la selección en el navegador.

## Favoritos

Se agregó una sección para guardar productos favoritos y consultarlos posteriormente.

## Banners y promociones

Se preparó la administración de banners desde el panel privado.

Los banners pueden incluir:

- Imagen.
- Título.
- Descripción.
- Enlace.
- Estado.
- Orden de aparición.

## Integración con Supabase

El catálogo público consulta productos reales de la base de datos.

Los cambios de información, precios y existencias se reflejan mediante las consultas a Supabase.

---

#  FASE 4 — Pedidos, WhatsApp y envíos

Se desarrolló la estructura necesaria para registrar y administrar pedidos de clientes.

## Compra por WhatsApp

El cliente puede:

1. Seleccionar productos.
2. Agregarlos al carrito.
3. Revisar cantidades y precios.
4. Iniciar el proceso de pedido.
5. Seleccionar modalidad de entrega.
6. Completar sus datos.
7. Registrar el pedido.
8. Abrir WhatsApp con la información de la compra.

El sistema genera una referencia de pedido.

**Importante:** registrar un pedido o abrir WhatsApp no significa que el pago se haya realizado o confirmado.

## Modalidades de entrega

### Recogida en tienda
El cliente solicita recoger personalmente su pedido.

### Domicilio local
El cliente proporciona una dirección y selecciona una zona de entrega disponible.

### Envío nacional
Permite preparar envíos a diferentes ciudades de Colombia.

## Gestión de envíos

El sistema contempla:

- Dirección.
- Ciudad.
- Departamento.
- Modalidad de entrega.
- Costo de envío.
- Transportadora.
- Número de guía.
- Información de seguimiento.

Las tarifas deben configurarse con valores reales desde el panel administrativo.

## Administración de pedidos

Se implementó un módulo para consultar los pedidos y administrar sus estados.

### Estados

1. Pendiente.
2. Confirmado.
3. En preparación.
4. Enviado.
5. Entregado.
6. Cancelado.

Los cambios están sujetos a permisos y reglas de transición.

## Protección del inventario

La lógica de pedidos contempla:

- Validación de existencias.
- Reservas temporales de inventario.
- Prevención de operaciones duplicadas.
- Actualización segura de existencias.
- Registro de movimientos.
- Restauración de unidades cuando corresponda.

Las reservas temporales tienen una duración lógica de 60 minutos.

La confirmación del pedido es una operación diferente de la confirmación del pago.

---

#  ACTUALIZACIÓN 4.1 — Finalización y seguimiento

Se amplió la Fase 4 para mejorar la experiencia posterior al carrito.

## Finalización de pedidos

Se añadió el acceso:

**Carrito → Finalizar pedido por WhatsApp**

Desde el formulario, el cliente autenticado puede registrar un pedido y obtener su referencia.

Después se muestra la opción de abrir WhatsApp para contactar con la tienda.

## Mis pedidos

Los clientes registrados pueden consultar sus propios pedidos.

Cada registro permite visualizar:

- Referencia.
- Estado actual.
- Fecha.
- Productos.
- Cantidades.
- Importe.
- Estado del proceso.

## Seguimiento individual

Se incorporó una página de seguimiento que permite consultar:

- Número del pedido.
- Estado actual.
- Historial de cambios.
- Productos comprados.
- Información de entrega.
- Dirección registrada.
- Transportadora y guía, cuando estén disponibles.

## Actualización de seguimiento

La consulta se puede actualizar manualmente.

También se preparó una actualización periódica mientras el cliente permanece en la pantalla.

## Seguridad del seguimiento

Los clientes autenticados solamente pueden consultar los pedidos asociados a su propia cuenta.

El acceso al historial y a la información del cliente está protegido mediante las reglas del backend.

---

#  Estructura del proyecto

La aplicación mantiene una estructura modular para facilitar el mantenimiento y la incorporación de nuevas funciones.

moda-infantil-checkout-seguimiento/
- docs/
- public/
- scripts/
- src/
  - components/
  - pages/
  - hooks/
  - lib/
  - services/
  - styles/
  - types/
- supabase/
  - manual/
  - migrations/
- .env.example
- .gitignore
- index.html
- package.json
- README.md
- vite.config.ts
- tsconfig.json
- vercel.json

Las carpetas agrupan las interfaces, los componentes, la integración con Supabase y la lógica de cada módulo.

---

#  Instalación del proyecto

## Requisitos

- Node.js.
- npm.
- Visual Studio Code o editor equivalente.
- Cuenta y proyecto de Supabase.
- Navegador web.
- Conexión a internet.

## 1. Descargar el proyecto

Descargar o clonar el repositorio de GitHub.

Repositorio:

https://github.com/perdomojunior1703-code/tienda-moda-infantil2

## 2. Abrir la carpeta

Abrir en Visual Studio Code la carpeta que contiene `package.json`.

## 3. Instalar dependencias

Ejecutar en la terminal:

    npm install

## 4. Configurar Supabase

Crear un archivo `.env` en la raíz del proyecto.

Agregar estas variables:

    VITE_SUPABASE_URL=https://TU-PROYECTO.supabase.co
    VITE_SUPABASE_PUBLISHABLE_KEY=TU_CLAVE_PUBLICA

Reemplazar los valores de ejemplo con los datos públicos del proyecto Supabase.

**No publicar el archivo `.env` ni incluir claves secretas o `service_role` en el frontend.**

## 5. Configurar la base de datos

Las migraciones SQL se encuentran en:

    supabase/migrations/

Orden de migraciones:

1. `20261120000100_identity_and_rbac.sql`
2. `20261120000200_catalog_and_stock.sql`
3. `20261120000300_business_foundation.sql`
4. `20261120000400_storage_foundation.sql`
5. `20261120000500_admin_role_management.sql`
6. `20261120000600_phase2_catalog_operations.sql`
7. `20261120000700_phase3_public_storefront.sql`
8. `20261120000800_phase4_orders_shipping.sql`

En una instalación nueva deben aplicarse respetando las dependencias.

Si la base de datos ya está configurada, no se deben volver a ejecutar las migraciones sin revisar su estado.

## 6. Ejecutar en desarrollo

    npm run dev

Abrir la dirección indicada por Vite, normalmente:

http://localhost:5173

## 7. Compilar

    npm run build

## 8. Revisar tipos TypeScript

    npm run typecheck

---

#  Seguridad

El sistema utiliza diferentes mecanismos para proteger la información.

- Autenticación de usuarios.
- Control de roles.
- Restricción de permisos.
- Políticas RLS de Supabase.
- Protección de rutas privadas.
- Validación de formularios.
- Funciones seguras de base de datos.
- Control de operaciones de inventario.
- Restricción del acceso a pedidos privados.
- Uso de variables de entorno.

La seguridad debe verificarse mediante pruebas con distintos roles antes del despliegue definitivo.

---

#  Pruebas realizadas y pendientes

Durante el desarrollo se comprobó visualmente el funcionamiento de diferentes módulos.

### Comprobaciones realizadas

- Acceso al panel de administrador.
- Conexión del frontend con Supabase.
- Visualización de categorías.
- Visualización de tallas y colores.
- Registro de un producto.
- Aparición del producto en el catálogo.
- Visualización de variantes.
- Visualización del carrito.
- Corrección de navegación del formulario de productos.
- Preparación de la interfaz de pedidos y seguimiento.

### Pruebas pendientes de completar

- Compilación completa en el entorno definitivo.
- Registro de pedidos reales de prueba.
- Seguimiento completo del pedido.
- Validación de reservas simultáneas.
- Confirmación y cancelación de pedidos.
- Restauración de inventario.
- Pruebas de seguridad por rol.
- Pruebas de rendimiento.
- Verificación final del proceso de compra.

**El proyecto está en desarrollo y no debe considerarse listo para operaciones comerciales reales hasta completar estas pruebas.**

---

#  Próximas fases

## Fase 5 — Punto de venta (POS)

Se tiene previsto implementar:

- Ventas presenciales.
- Búsqueda de productos por código.
- Registro de varios artículos por venta.
- Métodos de pago.
- Cálculo de cambio en efectivo.
- Recibos PDF.
- Apertura y cierre de caja.
- Movimientos de caja.
- Devoluciones y cambios.
- Registro del empleado que realiza cada venta.

## Fase 6 — Dashboard y reportes

Se tiene previsto desarrollar:

- Ventas totales.
- Ganancias calculadas con costos reales.
- Estadísticas comerciales.
- Gráficos de ventas.
- Productos más vendidos.
- Categorías más vendidas.
- Clientes registrados.
- Reportes.
- Alertas de inventario.
- Configuración general del almacén.

## Fase 7 — Optimización y despliegue

- Pruebas funcionales.
- Validación de seguridad.
- Optimización del rendimiento.
- Mejoras de accesibilidad.
- Corrección de errores.
- Preparación para producción.
- Despliegue en Vercel.
- Verificación final de la aplicación.

También queda pendiente la integración de una pasarela de pagos en línea, que deberá confirmarse y configurarse antes de permitir cobros reales.

---

#  Objetivo final

El objetivo de Moda Infantil es ofrecer una solución integral para administrar una tienda de ropa infantil desde una plataforma web.

La aplicación busca reunir la gestión de productos, inventario, clientes, pedidos, ventas y reportes en un sistema conectado a una base de datos centralizada.

Se pretende facilitar el trabajo del personal del almacén, reducir errores en el inventario y mejorar la experiencia de compra de los clientes.

---

##  Estado del proyecto

**Versión:** 4.1 — Compra por WhatsApp y seguimiento

**Estado:** En desarrollo.

**Fases implementadas en código:** 1, 2, 3, 4 y actualización 4.1.

**Fases pendientes:** 5, 6 y 7.

**Frontend:** React + TypeScript + Tailwind CSS.

**Backend:** Supabase + PostgreSQL.

**Base de datos:** Supabase.

**Idioma:** Español.

**Moneda:** Peso colombiano (COP).

**Mercado principal:** Colombia.

---

##  Desarrollo

Proyecto desarrollado mediante un proceso incremental, trabajando por fases e incorporando nuevas funcionalidades y correcciones sobre la estructura existente.

El sistema continuará evolucionando hasta convertirse en una plataforma completa de comercio electrónico y administración para Moda Infantil.

**Moda Infantil — Tecnología para gestionar y hacer crecer una tienda infantil.**
