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

* Un flujo de reservas claro y ordenado
* Verificación de turnos por WhatsApp (OTP)
* Recordatorios automáticos para reducir ausencias
* Mayor control y visibilidad del negocio
* Gestión centralizada de especialistas, servicios y disponibilidad

---

## ✨ Funcionalidades principales

### 👥 Sistema multi-rol (4 roles)

* **Superadmin**: gestión global de la plataforma — negocios, usuarios, planes, logs y configuraciones
* **Admin**: administración completa del negocio propio
* **Especialista**: agenda y servicios asignados por el admin
* **Cliente**: reserva autogestionada e historial de turnos

### ⚙️ Funcionalidad core

* Reserva de turnos online con portal público por negocio
* Verificación OTP por WhatsApp al confirmar la reserva
* Recordatorios automáticos por WhatsApp (24h y 1h antes del turno)
* Gestión de servicios y especialistas
* Calendario interactivo con vista de turnos y bloqueos de agenda
* Bloqueos manuales de días completos o rangos horarios
* Métodos de pago: efectivo o transferencia bancaria (con CBU/Alias configurable)
* Señas configurables por servicio
* Notificaciones internas de nuevos turnos
* Exportación de clientes a CSV
* Sistema de planes con límites por negocio (Trial y Pro)
* Métricas y dashboard por negocio
* Auto-registro de negocios y formulario de solicitud de demo

---

## 📸 Capturas de pantalla

### 🌐 Landing pública

Vista inicial donde el cliente conoce el negocio y puede solicitar una demo o registrarse.

![Landing](assets/images/landing/landing-1.png)
![Landing](assets/images/landing/landing-2.png)
![Landing](assets/images/landing/landing-3.png)
![Landing](assets/images/landing/landing-4.png)
![Landing](assets/images/landing/landing-5.png)
![Landing](assets/images/landing/landing-6.png)
![Landing](assets/images/landing/landing-7.png)

---

### 📲 Flujo de reserva

Proceso simple e intuitivo para sacar un turno en pocos pasos.

![Servicio](assets/images/proceso-cliente/1.servicio.png)
![Especialista](assets/images/proceso-cliente/2.especialista.png)
![Fecha](assets/images/proceso-cliente/3.fecha.png)
![Hora](assets/images/proceso-cliente/4.hora.png)
![Método de pago (efectivo / transferencia)](assets/images/proceso-cliente/5.metodo-pago.png)
![Confirmación](assets/images/proceso-cliente/6.confirmar.png)
![Datos del Cliente](assets/images/proceso-cliente/7.datos-clientes.png)
![Reserva Realizada](assets/images/proceso-cliente/9.reservado.png)

---

### 👤 Panel del cliente

Gestión de turnos e historial.

![Turnos cliente](assets/images/cliente/3.turnos.png)

---

### 🧑‍💼 Panel admin / especialista

Control completo del negocio, agenda y servicios.

![Pagina de Login](assets/images/admin-especialista/1.login.png)
![Dashboard](assets/images/admin-especialista/2.dashboard.png)
![Dashboard](assets/images/admin-especialista/3.dashboard2.png)
![Calendario](assets/images/admin-especialista/4.calendario.png)
![Servicios](assets/images/admin-especialista/5.servicios.png)
![Especialistas](assets/images/admin-especialista/6.especialistas.png)
![Clientes](assets/images/admin-especialista/7.clientes.png)
![Perfil](assets/images/admin-especialista/10.perfil.png)

---

## 🛠 Stack tecnológico

* **Backend**: PHP 8.2 con arquitectura MVC propia (sin frameworks)
* **Base de datos**: MariaDB / MySQL
* **Frontend**: Bootstrap 5, Bootstrap Icons, jQuery, SweetAlert2, FullCalendar

### 🔌 Integraciones activas

* **WhatsApp via Twilio**: verificación OTP al reservar y recordatorios automáticos
* **Email via PHPMailer**: recuperación de contraseña

### ⚙️ Infraestructura

* Apache + XAMPP
* Cron jobs (recordatorios, backups, rotación de logs, optimización de BD)
* Sistema de logs y monitoreo
* Configuración segura por entorno

---

## 🧠 Visión general de la arquitectura

Turnerito está construido sobre una arquitectura MVC propia, con:

* Separación clara de responsabilidades
* Control de acceso basado en roles
* Aislamiento multi-tenant (todas las queries filtran por negocio)
* Validación y sanitización segura de datos
* Servicios modulares para integraciones externas

> Los detalles internos de arquitectura e implementación se mantienen
> privados de forma intencional.

---

## 📈 Estado del proyecto

✅ Sistema funcional
✅ Plataforma multi-rol lista para producción
✅ Multi-tenant activo (múltiples negocios independientes)
🔒 Código fuente principal privado

Este repositorio público se utiliza para:

* Presentación del producto
* Documentación general
* Roadmap y comunicación
* Visibilidad externa del proyecto

---

## 🛣️ Roadmap (público)

### V1 — Implementado ✅
* Portal de reservas público por negocio
* Verificación OTP por WhatsApp
* Recordatorios automáticos de turnos
* Panel admin completo con calendario interactivo
* Sistema de planes y gestión desde superadmin
* Landing pública con solicitud de demo y auto-registro

### V2 — Próximamente 🚧
* Integración MercadoPago (pagos online)
* Mejora del flujo de onboarding
* Dashboard de analíticas avanzadas

---

## 📬 Contacto

¿Te interesa Turnerito, una demo o colaborar en el proyecto?

🌐 **[turneritoapp.com](https://turneritoapp.com/)**
📧 **[turnerito.app@gmail.com](mailto:turnerito.app@gmail.com)**
📱 **[+54 351 530-3017](https://wa.me/543515303017)**

---

© Turnerito App — Todos los derechos reservados
