# Definición del Sistema

### Accesos Rápidos

 [Objetivos del Proyecto](Entregas/Definicion_Sistema.md#Objetivos-del-Proyecto)
		1. [Objetivo General](Entregas/Definicion_Sistema.md#objetivo-general)
		2. [Objetivos Funcionales](Entregas/Definicion_Sistema.md#objetivos-funcionales)
	2. Definiciones de Actores
	3. Especificación Funcional
		1. Diagrama de Casos de Uso 
		2. Tablas de especificación de Casos de Uso
   	3. Requisitos del Sistema (SRS)
	1. Requisitos Funcionales (RF).
	2. Requisitos No Funcionales (RNF).
	3. Requisitos de Información (IRQ - Persistencia).
4. Normativa y Legislación
## Objetivos del Proyecto

Las funcionalidades definen las acciones y capacidades específicas que el sistema debe ejecutar para satisfacer las necesidades del usuario.  
 
- ### Objetivo General

El objetivo general se podría generalizar en **5** grandes módulos

| Concepto                          | Descripción                                                                            | Análisis                                                                                                                                                                                                                       |
| --------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Mensajería en Tiempo Real**     | Sistema de chat instantáneo para usuarios, grupos y canales con persistencia de datos. | **S:** Chat de texto persistente.<br>**M:** Por la baja latencia<br>**A:** <br>**R:** Es la pieza clave de la app                                                                                                              |
| **Infraestructura y Despliegue**  | Puesta en marcha del ecosistema en servidores reales para acceso público.              | **S:** Despliegue de Backend y Frontend.<br>**M:** Tiene una Disponibilidad del 99%.<br>**A:** Ajustado al presupuesto de 50€-90€.<br>**R:**                                                                                   |
| **Gestión de Servidores y Roles** | Estructura jerárquica para comunidades con permisos de administración específicos.     | **S:** Sistema de permisos  funcional.<br>**M:** Control de acceso por canal.<br>**A:** Es alcanzable mediante Laravel <br>**R:** Prioridad para el control sobre usuarios                                                     |
| **Comunicación (VoIP)**           | Capacidad de realizar llamadas de voz entre usuarios o dentro de servidores.           | **S:** Audio bidireccional estable.<br>**M:** Claridad de voz sin cortes en redes<br>**A:**<br>**R:**                                                                                                                          |
| **Diseño de la Interfaz**         | Diseño limpio, intuitivo y enfocado en la productividad sin saturación visual.         | **S:** Interfaz responsiva con TailwindCSS.<br>**M:** Lo podremos medir con [Google Lighthouse](https://pagespeed.web.dev/?hl=es-419).<br>**A:** Desarrollo basado en componentes.<br>**R:** Facilita el uso por la aplicación |
 
  
- ### Objetivos Funcionales
  
Los  Objetivos funcionales se distribuirán de la siguiente manera:  

| ID        | MODULO                                       | Descripción                                                                   | SMART                                                                                                                           | Prioridad |
| --------- | -------------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | --------- |
| **OBJ01** | **Registro y Acceso**                        | Sistema de autenticación de usuarios para permitir el uso de la aplicación.   | **S:** Acceso con usuario/clave.<br>**M:** Validación de credenciales en DB.<br>**T:** (Semana 1).                              | Alta      |
| **OBJ02** | **Mensajería**                               | Chat de texto privado entre dos usuarios con visualización instantánea.       | **S:** Envío/recepción de texto.<br>**M:** Latencia menor a 1s.<br>**T:** (Semanas 2-4).                                        | Alta      |
| **OBJ03** | **Servidores Públicos**                      | Espacios accesibles mediante URL o invitación con múltiples canales.          | **S:** Estructura de canales independientes.<br>**M:** Soporta múltiples canales/servidor.<br>**T:** (Semanas 6-8).             | Alta      |
| **OBJ04** | **Interfaz**                                 | Panel de navegación intuitivo                                                 | **S:** Interfaz con TailwindCSS y React.<br>**M:** mínimo 90 puntos  en Lighthouse.<br>**T:** Duración del proyecto             | Alta      |
| **OBJ05** | **Roles en servidores**                      | Asignación de permisos jerárquicos a usuarios dentro de los servidores.       | **S:** Asignación de permisos específicos.<br>**M:** Niveles de jerarquía especificados por un lider<br>**T:** (Semana 8 - 10). | Media     |
| **OBJ06** | **Comunicación [VoIP](Siglas-Acronimos.md)** | Implementación de llamadas de voz entre usuarios y en canales de servidor.    | **S:** Audio bidireccional.<br>**M:** Conexión estable sin cortes.<br>**T:** Fase 3 (Semanas 10-12).                            | Media     |
| **OBJ07** | **Gestión de Grupos**                        | Creación de salas de chat cerradas con un administrador y lista de invitados. | **S:** Creación de grupo y miembros.<br>**M:** 1 rol de administrador.<br>**T:** (Semanas 4-6).                                 | Media     |
| **OBJ08** | **Implementación [IA](Siglas-Acronimos.md)** | Conexion a una Inteligencia artificial externa                                | **S:** Integración vía API externa.<br>**T:** (Semanas 12- Fin de proyecto).                                                    | Baja      |
