# 🗓️ Turnerito

**Turnerito** es un sistema web **multi-tenant** de gestión y reserva de turnos
diseñado para negocios de servicios como barberías, peluquerías, centros de
estética y profesionales independientes.

Cada negocio opera bajo su propio portal público (`/{negocio}/reservar`) y cuenta con
panel de administración propio, calendario interactivo y automatizaciones activas.

---

## 🎯 ¿Qué problema resuelve Turnerito?

Muchos pequeños y medianos negocios todavía gestionan sus turnos de forma
manual a través de WhatsApp, Instagram o en agenda física.

Turnerito permite:

* Un flujo de reservas claro, ordenado y 100% online
* Verificación de identidad por WhatsApp (OTP) sin registro previo del cliente
* Recordatorios automáticos para reducir ausencias
* Mayor control y visibilidad del negocio
* Gestión centralizada de especialistas, servicios y disponibilidad

---

## ✨ Funcionalidades principales

### 👥 Sistema multi-rol (4 roles)

| Rol | Alcance |
|---|---|
| **Superadmin** | Gestión global de la plataforma: negocios, usuarios, planes, logs y respaldos |
| **Admin** | Administración completa del negocio propio |
| **Especialista** | Agenda personal, servicios asignados y disponibilidad |
| **Cliente** | Reserva autogestionada e historial de turnos |

---

### 📲 Flujo de reserva del cliente

1. Accede al portal público del negocio (`/{negocio}/reservar`)
2. Elige uno o más servicios (si el negocio habilitó la opción multi-servicio)
3. Selecciona especialista, fecha y horario disponible
4. Elige método de pago (efectivo o transferencia bancaria)
5. Ingresa nombre y número de WhatsApp
6. Recibe un código OTP por WhatsApp para confirmar la reserva
7. Recibe recordatorios automáticos 24h y 1h antes del turno

El sistema detecta si el cliente ya tiene sesión activa y le permite confirmar directamente sin volver a ingresar su número.

---

### ⚙️ Funcionalidad core

**Reservas y agenda**
* Portal público de reservas por negocio con URL personalizada
* Verificación OTP por WhatsApp al confirmar (sin registro previo)
* Recordatorios automáticos por WhatsApp (24h y 1h antes del turno)
* Reserva de **múltiples servicios** en un mismo turno (configurable por el admin)
* Bloqueos manuales de agenda (días completos o franjas horarias específicas)
* Completado automático de turnos pasados vía cron

**Pagos**
* Métodos de pago: efectivo en el turno o transferencia bancaria
* Datos bancarios (CBU / Alias) configurables por especialista o de forma centralizada por el negocio
* Señas configurables por servicio (monto porcentual, obligatoria u opcional)
* Historial de pagos con filtros y exportación

**Calendario interactivo (panel admin/especialista)**
* Motor de calendario propio (CSS Grid + JavaScript), sin dependencias externas
* Vistas disponibles: semana, día, lista y mes
* Vista mes powered by FullCalendar (carga bajo demanda)
* Soporte completo de dark mode reactivo
* Adaptación automática a mobile (vista lista por defecto en pantallas pequeñas)

**Gestión del negocio**
* Dashboard con métricas, historial paginado y ordenable por columnas
* Gestión de servicios, especialistas, clientes y disponibilidad horaria
* Asignación de servicios a especialistas
* Importación masiva de datos vía CSV o Excel (wizard guiado de 4 pasos: servicios → especialistas → asignaciones → horarios)
* Exportación de clientes a CSV
* Notificaciones internas de nuevas reservas en el panel
* Configuración de anticipación mínima/máxima para reservar y política de cancelación
* Activación/desactivación de funcionalidades por negocio (feature flags)

**Seguridad**
* Content Security Policy (CSP) con nonces por request
* Rate limiting en verificación OTP
* Protección CSRF en todos los formularios y endpoints
* Validación y sanitización de todas las entradas
* Sistema de auditoría de acciones por usuario, rol y negocio

**Plataforma y operaciones**
* Sistema de planes (Trial, Pro, Business) con feature flags y límites configurables
* Panel superadmin con 14 módulos: negocios, usuarios, planes, pagos, auditoría, logs, respaldos y más
* Sistema de logs por categoría con rotación automática
* Backups automáticos de base de datos con descarga desde el panel
* Cron jobs: recordatorios WhatsApp, completado de turnos, backups, rotación de logs, optimización de BD

---

## 📦 Planes

| | Trial | Pro |
|---|---|---|
| Especialistas | hasta 2 | ilimitados |
| Servicios | hasta 5 | ilimitados |
| Reservas online | ✅ | ✅ |
| Verificación OTP WhatsApp | ❌ | ✅ |
| Recordatorios automáticos | ❌ | ✅ |

---

## 🛠 Stack tecnológico

| Capa | Tecnología |
|---|---|
| **Backend** | PHP 8.2 — arquitectura MVC propia (sin frameworks) |
| **Base de datos** | MariaDB / MySQL |
| **Frontend** | Bootstrap 5.3.3, Bootstrap Icons, SweetAlert2 |
| **Calendario** | Motor propio (CSS Grid + JS) + FullCalendar (solo vista mes) |
| **Servidor** | Apache (XAMPP en desarrollo, Linux en producción) |

### 🔌 Integraciones

| Integración | Uso |
|---|---|
| **Twilio / WhatsApp** | Código OTP de verificación al reservar + recordatorios automáticos |
| **PHPMailer** | Recuperación de contraseña por email |

### ⚙️ Infraestructura

* Cron jobs automatizados: recordatorios WhatsApp, completado de turnos, backups, rotación de logs, optimización de BD
* Sistema de logs con niveles (info, warning, error) y rotación por tamaño/fecha
* Auditoría de acciones trazable por usuario, rol y negocio
* Configuración por entorno separada del código fuente

---

## 🧠 Arquitectura

Turnerito está construido sobre una arquitectura MVC propia con:

* Separación clara entre controladores, modelos, vistas y servicios
* Control de acceso basado en roles (RBAC) verificado en cada capa
* Aislamiento multi-tenant: todas las consultas filtran por `negocio_id`
* Feature flags por plan y por negocio con límites configurables
* Servicios desacoplados para integraciones externas (WhatsApp, Email)
* CSP estricto con nonces dinámicos por request (sin `unsafe-inline`)

> Los detalles internos de implementación se mantienen privados de forma intencional.

---

## 📸 Capturas de pantalla

### 🌐 Landing pública

![Landing](assets/images/landing/landing-1.png)
![Landing](assets/images/landing/landing-2.png)
![Landing](assets/images/landing/landing-3.png)
![Landing](assets/images/landing/landing-4.png)
![Landing](assets/images/landing/landing-5.png)
![Landing](assets/images/landing/landing-6.png)
![Landing](assets/images/landing/landing-7.png)

---

### 📲 Flujo de reserva

![Servicio](assets/images/proceso-cliente/1.servicio.png)
![Especialista](assets/images/proceso-cliente/2.especialista.png)
![Fecha](assets/images/proceso-cliente/3.fecha.png)
![Hora](assets/images/proceso-cliente/4.hora.png)
![Método de pago](assets/images/proceso-cliente/5.metodo-pago.png)
![Confirmación](assets/images/proceso-cliente/6.confirmar.png)
![Datos del cliente](assets/images/proceso-cliente/7.datos-clientes.png)
![Reserva realizada](assets/images/proceso-cliente/9.reservado.png)

---

### 👤 Panel del cliente

![Turnos cliente](assets/images/cliente/3.turnos.png)

---

### 🧑‍💼 Panel admin / especialista

![Login](assets/images/admin-especialista/1.login.png)
![Dashboard](assets/images/admin-especialista/2.dashboard.png)
![Dashboard](assets/images/admin-especialista/3.dashboard2.png)
![Calendario](assets/images/admin-especialista/4.calendario.png)
![Servicios](assets/images/admin-especialista/5.servicios.png)
![Especialistas](assets/images/admin-especialista/6.especialistas.png)
![Clientes](assets/images/admin-especialista/7.clientes.png)
![Perfil](assets/images/admin-especialista/10.perfil.png)

---

## 📈 Estado del proyecto

✅ Sistema funcional y en uso  
✅ Multi-tenant activo (múltiples negocios independientes)  
✅ Reserva de múltiples servicios implementada  
🔒 Código fuente principal privado

Este repositorio público se utiliza para:

* Presentación del producto
* Documentación general
* Roadmap y comunicación
* Visibilidad externa del proyecto

---

## 🛣️ Roadmap

### V1 — Implementado ✅

* Portal de reservas público por negocio con URL personalizada
* Verificación OTP por WhatsApp (sin registro previo del cliente)
* Recordatorios automáticos de turnos por WhatsApp
* Panel admin/especialista completo con calendario interactivo propio
* Bloqueos de agenda, gestión de servicios y especialistas
* Métodos de pago: efectivo y transferencia bancaria con CBU/Alias
* Señas configurables por servicio
* Reserva de múltiples servicios en un mismo turno
* Importación masiva de datos desde CSV o Excel
* Sistema de planes (Trial y Pro) con feature flags
* Panel superadmin completo (14 módulos)
* Sistema de auditoría, logs con rotación y backups automáticos
* Dark mode en todos los paneles
* Landing pública con solicitud de demo y auto-registro de negocios

### V2 — En planificación 🚧

* Pagos online integrados
* App mobile (PWA)
* Integración con Google Calendar
* Dashboard de analíticas avanzadas
* Reserva en cascada (múltiples servicios con distintos especialistas en secuencia)
* Módulo de fidelización y cupones de descuento

---

## 📬 Contacto

¿Te interesa Turnerito, una demo o colaborar en el proyecto?

🌐 **[turneritoapp.com](https://turneritoapp.com/)**  
📧 **[turnerito.app@gmail.com](mailto:turnerito.app@gmail.com)**  
📱 **[+54 351 530-3017](https://wa.me/543515303017)**

---

© Turnerito App — Todos los derechos reservados
