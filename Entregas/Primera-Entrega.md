# Análisis, Propuesta y Estudio de Viabilidad

En este primer entregable sentaré las bases de todo el desarrollo. Justificaré el "qué", el "por qué" y el "cómo" de mi proyecto. El documento cubrirá los siguientes **5 puntos clave**

### Accesos Rápidos

- [Memoria Inicial](#memoria-inicial)
- [Estudio del Sector](#estudio-del-sector)
- [Análisis de Viabilidad](#análisis-de-viabilidad)
- [Herramientas y Tecnologías](#herramientas-y-tecnologías)
- [Guion de Trabajo](#guion-de-trabajo)
- [Definición de objetivos y funcionalidades (SMART)](#definición-de-objetivos-y-funcionalidades-smart)
	- [Objetivo General](#objetivo-general)
	- [Objetivos Funcionales](#objetivos-funcionales)

---
## Memoria Inicial 
1. **Idea del proyecto💡:**  
	En primer lugar EchoNow es una aplicación dedicada a la comunicación entre los usuarios a tiempo real.
	Es una aplicación minimalista que contiene lo esencial para poder mantener conversación con todo tipo de usuarios, grupos de usuarios o servidores, donde deberemos de estar registrados para poder hacer uso de la aplicación. La aplicación en principio contara con **2 principales formas de comunicación**
	- **Comunicación Escrita ✏️**:  
		Nos podremos comunicar con otros usuario vía texto, como si fuese la típica conversación que tenemos con un dispositivo móvil. Este apartado no contara con latencia entre mensajes, esto quiere decir que los mensajes se mostraran de manera instantánea y sin necesidad de refrescar el servicio. Evidentemente la latencia de los mensajes dependerá del tiempo de conexión de cada usuarios.  
		  
	- **Comunicación Oral 🔊**:  
		Además los usuarios podrán tener acceso a llamadas y diálogos mediante los servicios de la aplicación. Mas tarde veremos las opciones que tenemos en este apartado de poder crear llamadas con usuarios grupos o servidores.  
		
	Por otro lado la aplicación **podrá conectarse de 3 formas distintas** estas formas de conexión estan íntimamente ligadas con las formas de comunicación, de manera que las **3** formas de conexión que existen deberían de poder hacer uso de las **2 comunicaciones** existentes.  
	- **Entre Usuarios 👤:**  
		La conexión entre usuarios es muy simple, se establecería un canal / chat donde solamente 2 usuarios puedan dialogar en ese mismo contexto.  

	- **Mediante Grupos 👥:**
		<a id="mediante-grupos"></a>
		La conexión mediante grupos funciona de manera similar a la anterior nombrada, con la diferencia de que en vez de poder funcionar con **2 usuarios** únicamente, este normalmente contará con un número definido de usuarios. Además para formar parte de un grupo el anfitrión o administrador del grupo *(normalmente el fundador del grupo)* deberá de invitarte para poder acceder al grupo.
		
	- **Mediante Servidores 🌐:**
		La conexión mediante servidores funciona de manera simular a los [grupos](#mediante-grupos) la única diferencia es que cualquier persona con una invitación o a través de un link de tipo *URL* podría acceder y comenzar a dialogar. Además un servidor puede contar con varios canales *un canal es lo mismo que una conversación* estos canales estarán aislados unos de otros donde no los mensajes que se manden por cada canal serán independientes entre canales. Otra de las diferencias es que los los canales serán manejados mediante roles. Los cuales estarán directamente vinculados con cada usuario del servidor. Mas tarde hablaremos sobre ellos
	
2. **Justificación**  
	EchoNow soluciona problemas complejos a la hora de comunicarse con otros individuos gracias a su interfaz simple, su gran intuición para acceder a paneles de navegación y sobre todo por su simpleza, ya que EchoNow une todas las herramientas imprescindibles para un mejor espacio de trabajo / ocio.

3. **Oportunidad de negocio**  
	Las oportunidades de negocio que existe como proyecto emergente dependen mucho según el desarrollo y los caminos que tome el proyecto, ya que en principio una aplicación de comunicaciones nueva suele ser una muy buena opción para usuarios que quieran cambiar su forma de comunicación.  
	Dentro del mercado nacional e internacional de las plataformas de [VOIP](Siglas-Acronimos.md) en un principio sí que se podría contar con un hueco para nuestra aplicación, ya que tiene varios aspectos que solucionarán problemas de una gran parte de usuarios.  


## Estudio del Sector  

1. **Aplicaciones similares:**   
	Las aplicaciones más famosas similares a EchoNow serían las siguientes: **Discord, WhatsApp, Telegram, TeamSpeak, Instagram, Signal, Slack, Microsoft Teams** entre otras.   
	
2. **Necesidades actuales de los usuarios:** 
	Tras analizar aplicaciones como Discord, WhatsApp o Slack, se detectan las siguientes necesidades no completamente cubiertas:  
	- **Interfaz más simple y minimalista**, sin funciones innecesarias que saturen al usuario.  
	- **Unificación de los servicios** entre chat privado, grupos y servidores
	- **Mejor organización de conversaciones** mediante canales estructurados. *(únicamente en servidores)*  
	- **Equilibrio entre uso profesional y personal**, sin estar enfocada exclusivamente a uno de los dos ámbitos.  

## Análisis de Viabilidad  

1. **Análisis Técnico:**   
	La respuesta breve es **NO**.
	EchoNow no se podrá desarrollar al completo en los limites temporales establecidos debido a que es una aplicación muy ambiciona y con muchas funcionalidades por implementar. Sin embargo la gran mayoría de funcionalidad pensada en un principio **SI** se podrá completar dentro de los limites.   
	Más tarde nos dedicaremos a explicar las funcionalidades técnicas del desarrollo y quedará mucho mas claro el porque necesitamos más duración de desarrollo para completarlo.   
2. **Análisis Económico:**    
	Al optar por una arquitectura simple y al utilizar un servidor Linux para la lógica de backend en Laravel y Vercel para el [framework](Siglas-Acronimos.md) React se logra una infraestructura profesional con una inversión entre los **50€ y 90€**  *(Este valor puede variar según el progreso de la aplicación )*

## Herramientas y Tecnologías

Antes de empezar me gustaría detallar que nuestra aplicación consistirá en un proyecto separado mediante dos repositorios, uno dedicado a la parte del Backend y otro repositorio para el Frontend.    

Los lenguajes con los que se desarrollara el software serán **Laravel** para el Backend donde actuará como servidor, *(Será el repositorio que tengamos alojado en un servidor Linux)*. Por otro utilizaremos la librería **React**, para la parte del Frontend, también deberemos de mencionar el framework **Tailwind** el lenguaje de CSS.  

Como motor de base de datos utilizaremos **PostgresSQL**  

Para la mensajería instantánea deberemos de usar algún tipo de **WebHooks**.  

Además utilizaremos algunas herramientas como por ejemplo:  
- **GitHub Actions:**   
	Lo utilizaremos para la ejecución de tareas a la hora de realizar cambios en ramas, *pull requests*, issues, todo tipo de automatización con el repositorio.   
- **Github Projects:**   
	Lo uso para programarme las tareas que debo de seguir y tener un mayor  control de la aplicación, aquí tendré un proyecto para cada repositorio, para poder separar las tareas correctamente
- **Bruno:**   
	Es una aplicación para consumir [APIs](Siglas-Acronimos.md) en vez de utilizar Postman me he decantado por esta opción ya que es de código abierto a diferencia de Postman.   
- **TablePlus**:   
	Es un interfaz para la gestión de los datos de la base de datos, también he querido usar este gestor ya que es uno de los más rápidos que existen  
	
Además de estas herramientas básicas que he nombrado también debemos de tener claro que tanto para el *frontend* como para el *backend* usaremos dependencias para un mejor funcionamiento.   

## Guion de Trabajo

## Definición de objetivos y funcionalidades (SMART)

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
  
  No he puesto el tiempo porque no sabemos cuando va a durar cada parte del desarrollo
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
