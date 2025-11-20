---
title: "Manual Usuario Agenturi"
author: "Carlos Zárate"
date: "2025-11-20"
output:
  md_document:
    variant: markdown
    preserve_yaml: true
---

## 1. Información del Proyecto

**Nombre del Proyecto:** AGENTURI - Sistema de Gestión de Agencia
Turística\
**Nombre del Estudiante:** Carlos H. Zarate\
**Curso:** \[Por completar\]\
**Semestre:** Sexto 6to\
**Fecha:** 20 Noviembre 2025\
**Instructor:** Jaider Quintero

**Descripción Breve del Proyecto:\
**AGENTURI es un sistema integral de gestión para agencias turísticas
que permite administrar clientes, reservas, destinos turísticos, planes
de viaje, itinerarios, actividades, guías turísticos, alojamientos y
transportes.\
\
El sistema cuenta con una interfaz moderna y amigable desarrollada en
Angular con PrimeNG, conectada a un backend Django REST API.

## 2. Acceso al Sistema

### 2.1 Requisitos Previos

-   Navegador web moderno (Chrome, Firefox, Edge o Safari)

-   Conexión a internet

### 2.2 URL de Acceso al frontend

    http://localhost:4200/

### 2.3 Pantalla Principal

Al ingresar al sistema, verás la interfaz principal con:

-   **Header:** Muestra el logo y nombre "AGENTURI by CARLOS ZARATE"

-   **Menú Lateral (Aside):** Panel de navegación con todas las
    secciones del sistema.

-   **Área de Contenido:** Zona central donde se muestran las diferentes
    funcionalidades.

-   **Footer:** Información de derechos de autor del estudiante que
    desarrollo el proyecto.

## 3. Módulo de Clientes

### 3.1 Ver Listado de Clientes

**Ruta:** `/customers`

**Funcionalidad:**

-   Visualiza todos los clientes registrados en el sistema

-   Información mostrada: ID, Nombre, Apellido, Email, Teléfono

-   Tabla con paginación (5, 10, 25 o 50 registros por página)

-   Funciones de ordenamiento por columna

-   Búsqueda y filtrado de registros

-   Contador de registros totales

**Acciones disponibles:**

-   **Botón "Nuevo Cliente"** (verde, esquina superior derecha): Crear
    un nuevo cliente

-   **Icono de lápiz** (amarillo): Permite editar cliente existente

-   **Icono de basura** (rojo): Eliminar cliente

### 3.2 Crear Nuevo Cliente

**Ruta:** `/customers/new`

**Campos del formulario:**

1.  **Nombre**\* (obligatorio)

<!-- -->

    -   Tipo: Texto

    -   Ejemplo: "Juan Carlos"

    -   Mínimo 2 caracteres

2.  **Apellido**\* (obligatorio)

    -   Tipo: Texto

    -   Ejemplo: "Pérez García"

    -   Mínimo 2 caracteres

3.  **Email**\* (obligatorio)

    -   Tipo: Email

    -   Ejemplo: "<juan.perez@email.com>"

    -   Debe ser único en el sistema

4.  **Teléfono** (opcional)

    -   Tipo: Texto

    -   Ejemplo: "+57 300 123 4567"

**Botones:**

-   **Cancelar:** Regresa al listado sin guardar

-   **Guardar Cliente:** Crea el nuevo cliente (se activa solo si el
    formulario es válido)

### 3.3 Editar Cliente

**Ruta:** `/customers/edit/:id`

**Funcionalidad:**

-   Formulario precargado con los datos actuales del cliente

-   Mismos campos que en la creación

-   Validaciones en tiempo real

**Botones:**

-   **Cancelar:** Regresa al listado sin aplicar cambios

-   **Actualizar Cliente:** Guarda las modificaciones

### 3.4 Eliminar Cliente

**Proceso:**

1.  Clic en el icono de basura en el listado

2.  Aparece un cuadro de confirmación

3.  Opciones:

    -   **Cancelar:** No elimina el registro

    -   **Sí, eliminar:** Confirma la eliminación permanente

**Nota:** Esta acción no se puede deshacer.

## 4. Módulo de Reservas

### 4.1 Ver Listado de Reservas

**Ruta:** `/bookings`

**Funcionalidad:**

-   Visualiza todas las reservas del sistema

-   Información mostrada: ID, Fecha de Reserva, Cliente, Plan, Estado

-   Estados posibles:

    -   **Pendiente** (amarillo)

    -   **Pagada** (verde)

    -   **Cancelada** (rojo)

### 4.2 Crear Nueva Reserva

**Ruta:** `/bookings/new`

**Campos del formulario:**

1.  **Fecha de Reserva**\* (obligatorio)

    -   Selector de calendario

    -   Formato: DD/MM/AAAA

2.  **Cliente**\* (obligatorio)

    -   Lista desplegable con todos los clientes

    -   Muestra: Nombre completo del cliente

    -   Búsqueda integrada

3.  **Plan**\* (obligatorio)

    -   Lista desplegable con todos los planes disponibles

    -   Muestra: Nombre del plan turístico

4.  **Estado**\* (obligatorio)

    -   **Opciones**:

        -   Pendiente (valor por defecto)

        -   Pagada

        -   Cancelada

**Botones:**

-   **Cancelar:** Regresa al listado

-   **Guardar Reserva:** Crea la nueva reserva

### 4.3 Editar Reserva

**Ruta:** `/bookings/edit/:id`

**Funcionalidad:**

-   Formulario precargado con datos actuales

-   Permite modificar todos los campos

-   Útil para actualizar el estado de pago

### 4.4 Eliminar Reserva

Mismo proceso que eliminación de clientes, con confirmación obligatoria.

## 5. Módulo de Destinos

### 5.1 Ver Listado de Destinos

**Ruta:** `/destinations`

**Funcionalidad:**

-   Visualiza todos los destinos turísticos

-   Información: ID, Nombre, Ciudad, País

-   Tabla con paginación y ordenamiento

### 5.2 Crear Nuevo Destino

**Ruta:** `/destinations/new`

**Campos del formulario:**

1.  **Nombre del Destino**\* (obligatorio)

    -   Ejemplo: "Cartagena de Indias"

    -   Mínimo 2 caracteres

2.  **Ciudad** (opcional)

    -   Ejemplo: "Cartagena"

3.  **País** (opcional)

    -   Ejemplo: "Colombia"

**Botones:**

-   **Cancelar:** Regresa al listado

-   **Guardar Destino:** Crea el nuevo destino

### 5.3 Editar Destino

**Ruta:** `/destinations/edit/:id`

Similar al proceso de creación, con datos precargados.

### 5.4 Eliminar Destino

Confirmación requerida antes de eliminar.

## 6. Módulo de Alojamientos

### 6.1 Ver Listado de Alojamientos

**Ruta:** `/accommodations`

**Funcionalidad:**

-   Muestra todos los alojamientos registrados

-   Información: ID, Nombre, Tipo, Dirección, Destino

-   Relación con destinos turísticos

### 6.2 Crear Nuevo Alojamiento

**Ruta:** `/accommodations/new`

**Campos del formulario:**

1.  **Nombre**\* (obligatorio)

<!-- -->

    -    Ejemplo: "Hotel Caribe"

    -    Mínimo 2 caracteres

2.  **Tipo** (opcional)

<!-- -->

    -    Ejemplo: "Hotel", "Hostal", "Apartamento"

3.  **Dirección** (opcional)

    -   Ejemplo: "Calle 10 \# 20-30"

4.  **Destino**\* (obligatorio)

    -   Lista desplegable con destinos disponibles

    -   Búsqueda integrada

### 6.3 Editar Alojamiento

**Ruta:** `/accommodations/edit/:id`

Formulario completo con datos actuales cargados.

### 6.4 Eliminar Alojamiento

Confirmación requerida.

## 7. Módulo de Transportes

### 7.1 Ver Listado de Transportes

**Ruta:** `/transports`

**Funcionalidad:**

-   Visualiza medios de transporte disponibles

-   Información: ID, Tipo, Compañía, Destino, País

### 7.2 Crear Nuevo Transporte

**Ruta:** `/transports/new`

**Campos del formulario:**

1.  **Tipo de Transporte**\* (obligatorio)

<!-- -->

    -    Ejemplo: "Bus", "Avión", "Camión"

2.  **Compañía**\* (obligatorio)

    -   Ejemplo: "Avianca", "COPETRAN"

3.  **Destino**\* (obligatorio)

    -   Lista desplegable de destinos

### 7.3 Editar Transporte

**Ruta:** `/transports/edit/:id`

Formulario editable con validaciones.

### 7.4 Eliminar Transporte

Requiere confirmación del usuario.

## 8. Módulo de Planes Turísticos

### 8.1 Ver Listado de Planes

**Ruta:** `/plans`

**Funcionalidad:**

-   Muestra todos los planes turísticos

-   Información: ID, Nombre, Descripción, Precio Base, Destino

### 8.2 Crear Nuevo Plan

**Ruta:** `/plans/new`

**Campos del formulario:**

1.  **Nombre del Plan**\* (obligatorio)

    -   Ejemplo: "Plan Caribe Premium"

2.  **Descripción** (opcional)

<!-- -->

    -   Detalles del plan turístico

3.  **Precio Base**\* (obligatorio)

    -   Tipo: Numérico

    -   Ejemplo: 1500000

4.  **Destino**\* (obligatorio)

    -   Lista desplegable de destinos

### 8.3 Editar Plan

**Ruta:** `/plans/edit/:id`

Permite modificar todos los campos del plan.

### 8.4 Eliminar Plan

Confirmación obligatoria antes de eliminar.

## 9. Módulo de Itinerarios

### 9.1 Ver Listado de Itinerarios

**Ruta:** `/itineraries`

**Funcionalidad:**

-   Muestra los itinerarios por día

-   Información: ID, Día, Descripción, Plan Turístico

-   Identificación visual del número de día

### 9.2 Crear Nuevo Itinerario

**Ruta:** `/itineraries/new`

**Campos del formulario:**

1.  **Día**\* (obligatorio)

<!-- -->

    -    Tipo: Numérico

    -    Ejemplo: 1, 2, 3...

    -    Mínimo: 1

2.  **Descripción** (opcional)

    -   Ejemplo: "Día 1 - Llegada a Cartagena, check-in en el hotel,
        tour nocturno por el centro histórico"

    -   Campo de texto largo (hasta 5 filas)

3.  **Plan Turístico**\* (obligatorio)

    -   Lista desplegable de planes

### 9.3 Editar Itinerario

**Ruta:** `/itineraries/edit/:id`

Formulario completo editable.

### 9.4 Eliminar Itinerario

Confirmación requerida.

## 10. Módulo de Actividades

### 10.1 Ver Listado de Actividades

**Ruta:** `/activities`

**Funcionalidad:**

-   Muestra actividades asociadas a itinerarios

-   Información: ID, Nombre, Descripción, Costo Extra, Día del
    Itinerario

### 10.2 Crear Nueva Actividad

**Ruta:** `/activities/new`

**Campos del formulario:**

1.  **Nombre**\* (obligatorio)

<!-- -->

    -    Ejemplo: "Tour por la Ciudad Amurallada"

    -    Mínimo 2 caracteres

2.  **Descripción** (opcional)

    -   Detalles de la actividad

    -   Campo de texto largo

3.  **Costo Extra**\* (obligatorio)

    -   Tipo: Numérico

    -   Valor mínimo: 0

    -   Ejemplo: 50000

4.  **ID del Itinerario**\* (obligatorio)

    -   Tipo: Numérico

    -   Ejemplo: 1

**Nota:** En versiones futuras se implementará un selector desplegable
para el itinerario.

### 10.3 Editar Actividad

**Ruta:** `/activities/edit/:id`

Formulario editable con validaciones.

### 10.4 Eliminar Actividad

Confirmación obligatoria.

## 11. Módulo de Guías Turísticos

### 11.1 Ver Listado de Guías

**Ruta:** `/guides`

**Funcionalidad:**

-   Visualiza todos los guías registrados

-   Información: ID, Nombre, Teléfono, Idioma, Plan Asignado

### 11.2 Crear Nuevo Guía

**Ruta:** `/guides/new`

**Campos del formulario:**

1.  **Nombre Completo**\* (obligatorio)

    -   Ejemplo: "Juan Carlos Pérez"

    -   Mínimo 2 caracteres

2.  **Teléfono**\* (obligatorio)

    -   Ejemplo: "+57 300 123 4567"

3.  **Idioma**\* (obligatorio)

    -   Ejemplo: "Español", "Inglés", "Francés"

4.  **Plan Asignado**\* (obligatorio)

    -   Lista desplegable de planes disponibles

### 11.3 Editar Guía

**Ruta:** `/guides/edit/:id`

Formulario completo editable.

### 11.4 Eliminar Guía

Requiere confirmación.

## 12. Navegación del Sistema

### 12.1 Menú Lateral

El menú lateral está organizado jerárquicamente:

**Clientes**

-   Ver Clientes

-   Nuevo Cliente

**Reservas**

-   Ver Reservas

-   Nueva Reserva

**Destinos**

-   Ver Destinos

-   Nuevo Destino

-   **Alojamientos** (submenú)

    -   Ver Alojamientos

    -   Nuevo Alojamiento

-   **Transportes** (submenú)

    -   Ver Transportes

    -   Nuevo Transporte

**Planes Turísticos**

-   Ver Planes

-   Nuevo Plan

-   **Itinerarios** (submenú)

    -   Ver Itinerarios

    -   Nuevo Itinerario

-   **Actividades** (submenú)

    -   Ver Actividades

    -   Nueva Actividad

-   **Guías** (submenú)

    -   Ver Guías

    -   Nuevo Guía

### 12.2 Navegación Rápida

-   Clic en cualquier elemento del menú para acceder directamente

-   El menú se mantiene visible en todo momento

-   Resaltado visual de la sección activa

## 13. Funcionalidades Comunes

### 13.1 Tablas de Datos

Todas las tablas del sistema incluyen:

-   **Paginación:** Control inferior para navegar entre páginas

-   **Selector de registros por página:** 5, 10, 25 o 50

-   **Ordenamiento:** Clic en encabezados de columna

-   **Contador de registros:** Muestra rango actual y total

-   **Mensajes informativos:** Cuando no hay datos

### 13.2 Formularios

Características comunes:

-   **Campos obligatorios:** Marcados con asterisco rojo (\*)

-   **Validación en tiempo real:** Mensajes de error debajo de cada
    campo

-   **Validación al enviar:** Previene envío de formularios inválidos

-   **Botones deshabilitados:** Durante procesamiento de datos

-   **Indicadores de carga:** Spinner animado

### 13.3 Notificaciones

El sistema muestra notificaciones para:

-   **Éxito:** Operaciones completadas correctamente (verde)

-   **Error:** Problemas durante operaciones (rojo)

-   **Advertencia:** Validaciones o información importante (amarillo)

-   **Información:** Mensajes generales (azul)

Las notificaciones aparecen en la esquina superior derecha y se cierran
automáticamente.

### 13.4 Confirmaciones

Acciones destructivas (eliminar) requieren:

1.  Cuadro de diálogo modal

2.  Mensaje descriptivo de la acción

3.  Botones claros:

    -   Cancelar (gris)

    -   Confirmar/Eliminar (rojo)

## 14. Mejores Prácticas de Uso

### 14.1 Gestión de Clientes

-   Verifica que el email sea único antes de crear un cliente

-   Mantén actualizada la información de contacto

-   Usa el buscador de la tabla para encontrar clientes rápidamente

### 14.2 Creación de Reservas

-   Asegúrate de que el cliente y el plan existan previamente

-   Registra la reserva inmediatamente después de confirmarla con el
    cliente

-   Actualiza el estado de "Pendiente" a "Pagada" al recibir el pago

### 14.3 Configuración de Destinos

-   Crea primero los destinos antes de añadir alojamientos o transportes

-   Incluye información completa (ciudad y país) para mejor organización

-   Agrupa alojamientos y transportes por destino

### 14.4 Diseño de Planes Turísticos

**Orden recomendado:**

1.  Crear el destino turístico

2.  Crear el plan asociado al destino

3.  Crear los itinerarios día por día para el plan

4.  Añadir actividades específicas a cada itinerario

5.  Asignar guías al plan

### 14.5 Gestión de Itinerarios y Actividades

-   Numera los días secuencialmente (1, 2, 3...)

-   Describe claramente las actividades de cada día

-   Indica costos adicionales de actividades opcionales

-   Asegúrate de que cada actividad esté vinculada al itinerario
    correcto

## 15. Solución de Problemas Comunes

**Tip:** Revisar la consola del servidor Backend. Los diferentes codigos
de error en las peticiones pueden dar una idea de cual es el origen del
problema.

### 15.1 No puedo crear una reserva

**Problema:** El botón "Guardar Reserva" está deshabilitado\
**Solución #1:** Verifica que hayas completado todos los campos
obligatorios (marcados con \*)\
**Solución #2:** Verifica el servicio del componente y la forma en la
que genera la comunicacion con el backend ( Json )

### 15.2 Error al eliminar un registro

**Problema:** Aparece un error al intentar eliminar\
**Solución #1:** El registro puede estar relacionado con otros datos.
Ejemplo: No puedes eliminar un destino si tiene planes asociados.\
**Solución #2:** Verifica el servicio del componente y la forma en la
que genera la comunicacion con el backend ( Json )

### 15.3 No veo datos en una tabla

**Problema:** La tabla aparece vacía\
**Solución:**

-   Verifica que haya datos creados previamente

-   Revisa la conexión con el servidor backend, servicios, serializador
    y modelos.

-   Recarga la página (F5)

### 15.4 El formulario no se envía

**Problema:** Clic en "Guardar" no hace nada\
**Solución:**

-   Revisa los mensajes de error en rojo bajo los campos

-   Completa todos los campos obligatorios

-   Verifica el formato correcto (email, números, etc.)

### 15.5 Lista desplegable vacía

**Problema:** Un selector no muestra opciones\
**Solución:** Primero debes crear los registros relacionados. Ejemplo:
Para crear un plan, primero necesitas tener destinos registrados.

## 16. Glosario de Términos

-   **CRUD:** Create (Crear), Read (Leer), Update (Actualizar), Delete
    (Eliminar)

-   **Cliente:** Persona que contrata servicios turísticos

-   **Reserva:** Solicitud de servicio turístico por parte de un cliente

-   **Destino:** Ubicación geográfica ofrecida como destino turístico

-   **Plan:** Paquete turístico que incluye servicios y actividades

-   **Itinerario:** Cronograma día a día de un plan turístico

-   **Actividad:** Evento específico dentro de un itinerario

-   **Guía:** Persona encargada de acompañar y orientar a los turistas

-   **Alojamiento:** Lugar de hospedaje (hotel, hostal, apartamento)

-   **Transporte:** Medio de desplazamiento disponible en un destino

## 17. Contacto y Soporte

Para asistencia técnica o consultas sobre el uso del sistema:

**Desarrollador:** DEV-Gordon\
**Proyecto:** Agenturi-Django\
**Repositorio:** [GitHub -
Agenturi-Django](https://github.com/DEV-Gordon/Agenturi-Django)

**Reporte de problemas:**

-   Utiliza el sistema de issues en GitHub

-   Proporciona capturas de pantalla cuando sea posible

-   Describe detalladamente los pasos para reproducir el problema

## Anexo A: Capturas de Pantalla del Sistema

### A.1 Pantalla Principal

![](images/clipboard-1354995127.png)

### A.2 Módulo de Clientes

#### Listado de Clientes

![](images/clipboard-169551307.png)

#### Crear Cliente

![](images/clipboard-504459406.png)

#### Editar Cliente

![](images/clipboard-2930930835.png)

#### Confirmación de Eliminación

![](images/clipboard-2489379958.png)

### A.3 Módulo de Reservas

#### Listado de Reservas

![](images/clipboard-1929083710.png)

#### Crear Reserva

![](images/clipboard-1239341992.png)

#### Editar Cliente

![](images/clipboard-3882661023.png)

#### Confirmación de Eliminación

![](images/clipboard-3291070661.png)

#### A.4 Módulo de Destinos

#### Listado de Destinos

![](images/clipboard-2329242334.png)

#### Crear Destino

![](images/clipboard-2286594714.png)

#### Editar destino

![](images/clipboard-3352232464.png)

#### Confirmacion de eliminacion

![](images/clipboard-3369004084.png)

### A.5 Módulo de Alojamientos

#### Listado de Alojamientos

![](images/clipboard-139368755.png)

#### Crear Alojamiento

![](images/clipboard-4177713557.png)

#### Editar Alojamiento

![](images/clipboard-2223947274.png)

#### Confirmacion de eliminacion

![](images/clipboard-1420874380.png)

### A.6 Módulo de Transportes

#### Listado de Transportes

![](images/clipboard-636316740.png)

#### Crear Transporte

![](images/clipboard-2838452817.png)

#### Editar Transporte

![](images/clipboard-665114446.png)

#### Confirmacion de eliminacion

![](images/clipboard-905844318.png)

### A.7 Módulo de Planes

#### Listado de Planes

![](images/clipboard-593603758.png)

#### Crear Plan

![](images/clipboard-2931047891.png)

#### Editar Plan

![](images/clipboard-3360082482.png)

#### Confirmacion de Eliminacion

![](images/clipboard-3425056503.png)

### A.8 Módulo de Itinerarios

#### Listado de Itinerarios

![](images/clipboard-4194532754.png)

#### Crear Itinerario

![](images/clipboard-1398862640.png)

#### editar Itinerarios

![](images/clipboard-2587097102.png)

#### Confirmacion de eliminacion

![](images/clipboard-3016271109.png)

### A.9 Módulo de Actividades

#### Listado de Actividades

![](images/clipboard-318842488.png)

#### Crear Actividad

![](images/clipboard-3291722970.png)

#### Editar Actividades

![](images/clipboard-3448565119.png)

#### Confirmacion de eliiminacion

![](images/clipboard-3696159078.png)

### A.10 Módulo de Guías

#### Listado de Guías

![](images/clipboard-3805352017.png)

#### Crear Guía

![](images/clipboard-1962758053.png)

#### Editar guias

![](images/clipboard-972351918.png)

#### confirmacion de eliminacion

![](images/clipboard-1478232984.png)

### A.11 Elementos de UI Comunes

#### Notificaciones

![](images/clipboard-2738867805.png)

![](images/clipboard-1234736359.png)

![](images/clipboard-3029661052.png)
