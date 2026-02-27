<p align="center">
  <img src="images/logo-blanco.png" 
       alt="Logotipo EchoNow" 
       width="150">
</p>  

# Documentación EchoNow

EchoNow es una aplicación de comunicación en tiempo real que permite a los usuarios
crear canales de voz y texto, gestionar notificaciones y realizar llamadas.
Este documento describe la arquitectura, funcionalidades actuales y futuras
mejoras del proyecto.   
## Licencia

Esta obra está bajo una licencia Reconocimiento-Compartir bajo la misma licencia 3.0 España de Creative Commons. Para ver una copia de esta licencia, visite [Licencia CC](http://creativecommons.org/licenses/by-sa/3.0/es/) o envíe una carta a Creative Commons, 171 Second Street, Suite 300, San Francisco, California 94105, USA.  

## Índice de Contenido
1. [Introducción y Justificación](#introducción-y-justificación)
	1. [Memoria Inicial](#memoria-inicial)
	2. [Estudio del Sector](#estudio-del-sector)
	3. [Análisis de Viabilidad](#análisis-de-Viabilidad)
	4. [Herramientas y Tecnologías](#herramientas-y-tecnologías)
2. [Definición del Sistema](#Definición-del-Sistema)
	1.  [Objetivos del Proyecto](#Objetivos-del-Proyecto)
		1. [Objetivo General](#objetivo-general)
		2. [Objetivos Funcionales](#objetivos-funcionales)
	2. Definiciones de Actores
	3. Especificación Funcional
		1. Diagrama de Casos de Uso 
		2. Tablas de especificación de Casos de Uso
	4. Requisitos del Sistema (SRS)
	      	1. Requisitos Funcionales (RF).
	      	2. Requisitos No Funcionales (RNF).
	      	3. Requisitos de Información (IRQ - Persistencia).  
	5. Normativa y Legislación.   
3. [Diseño Tecnológico y Arquitectura](Diseño_Tecnológico_Arquitectura.md)
	1. Stack Tecnológico  
	2. Arquitectura del Software  
	3.  Diseño de Datos  
	4. Diseño de Interfaz  
4. [Planificación y Metodología](Planificación_Metodologia.md)  
	1. Metodología de Trabajo  
	2. Planificación Temporal (Gantt)  
	3. Guion de Trabajo  
5. [Desarrollo e Implementación](Desarrollo_Implementacion.md)
	1. Organización real del trabajo  
	2. Estructura del Proyecto  
	3. Aspectos relevantes de la codificación  
	4. Despliegue  
6. [Pruebas y Control de Calidad](Pruebas_Control_Calidad.md)
	1. Plan de Pruebas  
	2. Registro de Incidencias  
	3. Validación de Requisitos  
7. [Conclusiones y Futuro](Conclusiones_Futuro.md)
	1. Grado de cumplimiento de objetivos.  
	2. Dificultades y aprendizaje personal.  
	3. Posibles mejoras y líneas futuras del proyecto.  
8. [Referencias y bibliografía](Referencias_bibliografía.md)
9. [Glosario de Términos y Acrónimos](#glosario-de-términos-y-acrónimos)
10. [Anexos](Anexos.md)
	1. Manual de instalación  
	2. Manual de usuario  
	3. Documentación complementaria digital  
	4. Anexos técnicos y documentales  

---
## Índice de Figuras  

---  

## Índice de Tablas

---

## Identificación del Proyecto  

**Autor:** Antonio José Blázquez Jiménez
**Ciclo:**  Desarrollo de Aplicaciones Web  
**Responsable:** Serafina Martín Marcos  
**Institución:** I.E.S. VENANCIO BLANCO, SALAMANCA

---  

# Introducción y Justificación

En este primer entregable sentaré las bases de todo el desarrollo. Justificaré el "qué", el "por qué" y el "cómo" de mi proyecto. El documento cubrirá los siguientes **5 puntos clave**

## Memoria Inicial 
**Idea del proyecto💡:**  
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

## Justificación  
EchoNow soluciona problemas complejos a la hora de comunicarse con otros individuos gracias a su interfaz simple, su gran intuición para acceder a paneles de navegación y sobre todo por su simpleza, ya que EchoNow une todas las herramientas imprescindibles para un mejor espacio de trabajo / ocio.

## Oportunidad de negocio  
Las oportunidades de negocio que existe como proyecto emergente dependen mucho según el desarrollo y los caminos que tome el proyecto, ya que en principio una aplicación de comunicaciones nueva suele ser una muy buena opción para usuarios que quieran cambiar su forma de comunicación.  
Dentro del mercado nacional e internacional de las plataformas de [VOIP](#glosario-de-términos-y-acrónimos) en un principio sí que se podría contar con un hueco para nuestra aplicación, ya que tiene varios aspectos que solucionarán problemas de una gran parte de usuarios. 


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
	Al optar por una arquitectura simple y al utilizar un servidor Linux para la lógica de backend en Laravel y Vercel para el [framework](#glosario-de-términos-y-acrónimos) React se logra una infraestructura profesional con una inversión entre los **50€ y 90€**  *(Este valor puede variar según el progreso de la aplicación )*

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
	Es una aplicación para consumir [APIs](#glosario-de-términos-y-acrónimos) en vez de utilizar Postman me he decantado por esta opción ya que es de código abierto a diferencia de Postman.   
- **TablePlus**:   
	Es un interfaz para la gestión de los datos de la base de datos, también he querido usar este gestor ya que es uno de los más rápidos que existen  
	
Además de estas herramientas básicas que he nombrado también debemos de tener claro que tanto para el *frontend* como para el *backend* usaremos dependencias para un mejor funcionamiento.   

---  

# Definición del Sistema

Las funcionalidades definen las acciones y capacidades específicas que el sistema debe ejecutar para satisfacer las necesidades del usuario.  

## Objetivos del Proyecto  
 
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
| **OBJ06** | **Comunicación [VoIP](#glosario-de-términos-y-acrónimos)** | Implementación de llamadas de voz entre usuarios y en canales de servidor.    | **S:** Audio bidireccional.<br>**M:** Conexión estable sin cortes.<br>**T:** Fase 3 (Semanas 10-12).                            | Media     |
| **OBJ07** | **Gestión de Grupos**                        | Creación de salas de chat cerradas con un administrador y lista de invitados. | **S:** Creación de grupo y miembros.<br>**M:** 1 rol de administrador.<br>**T:** (Semanas 4-6).                                 | Media     |
| **OBJ08** | **Implementación [IA](#glosario-de-términos-y-acrónimos)** | Conexion a una Inteligencia artificial externa                                | **S:** Integración vía API externa.<br>**T:** (Semanas 12- Fin de proyecto).                                                    | Baja      |

---

# Glosario de Términos y Acrónimos  

Glosario dedicado a la definición y/o explicación de nuevos de *términos - acrónimos - siglas*.    

| Palabra   | Significado                                                                                                                                               |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| VOIP      | Voz sobre Protocolo de Internet                                                                                                                           |
| Framework | Conjunto estandarizado de herramientas, librerías, módulos y buenas prácticas prediseñadas que proporcionan una estructura base para desarrollar software |
| API       | (Interfaz de Programación de Aplicaciones) es un conjunto de reglas y protocolos que permite a distintas aplicaciones informáticas comunicarse            |
| IA        | Inteligencia Artificial                                                                                                                                   |

