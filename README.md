# G4 - CPD para una red social orientada a productos de supermercado.

### Integrantes del grupo:
- Daniel Pablo Dumea
- Jordi Escriva Montaner
- Ivan Catala Prats
  

# Índice


-[1. Introducción](#Introducción)  
## 2. Objetivos del Proyecto  
## 3. Requisitos  
### 3.1 Requisitos Funcionales  
### 3.2 Requisitos No Funcionales  

## 4. Análisis de Requisitos  
### 4.1 Requisitos de Hardware  
### 4.2 Requisitos de Software  
### 4.3 Requisitos de Red  
### 4.4 Capacidades Técnicas Necesarias  
### 4.5 Ejemplo de Escenario de Uso  

## 5. Cronograma del Proyecto  

## 6. Asignación de Roles y Responsabilidades  
### 6.1 Roles del Equipo  
### 6.2 Dinámica entre Roles  
### 6.3 Actividades del Proyecto  

## 7. Identificación de Recursos Necesarios  
### 7.1 Recursos Humanos  
### 7.2 Costes de Hardware  
### 7.3 Costes de Software  
### 7.4 Costes de Red  
### 7.5 Costes de Infraestructura y Mantenimiento  
### 7.6 Estimación Financiera  

## 8. Evaluación de Riesgos y Planificación de Contingencias  
### 8.1 Identificación de Riesgos  
### 8.2 Evaluación de los Riesgos  
### 8.3 Plan de Contingencias  
### 8.4 Protocolos de Actuación  

## 9. Diseño de la Arquitectura del Sistema  
### 9.1 Segmentación por VLANs  
### 9.2 Conectividad y Flujo de Datos  
### 9.3 Seguridad y Respaldo  
### 9.4 Servidores  
### 9.5 Almacenamiento  
### 9.6 Infraestructura Adicional  
### 9.7 Mecanismos de Redundancia  
### 9.8 Herramientas de Virtualización  
### 9.9 Contratación de Servicios AWS S3  
### 9.10 Dispositivos Utilizados  

## 10. Diseño de la Seguridad del Sistema  
### 10.1 Medidas de Protección  
### 10.2 Protección contra Amenazas Internas  
### 10.3 Respuesta ante Ciberataques  
### 10.4 Políticas de Seguridad  
### 10.5 Políticas de Protección de Datos  
### 10.6 Seguridad en Dispositivos Móviles  

## 11. Diseño del Plan de Recuperación ante Desastres  
### 11.1 Estrategia de Copias de Seguridad  
### 11.2 Almacenamiento de Copias  
### 11.3 Restauración de Sistemas y Datos  
### 11.4 Mecanismos de Redundancia  
### 11.5 Documentación y Pruebas Regulares  

## 12. Manual del Usuario del CPD  
### 12.1 Acceso al Sistema  
### 12.2 Uso de Recursos del CPD  
### 12.3 Resolución de Problemas  

## 13. Guía de Administración del CPD  
### 13.1 Gestión de Servidores  
### 13.2 Gestión de Red  
### 13.3 Seguridad del CPD  
### 13.4 Procedimientos de Recuperación  
### 13.5 Documentación y Auditorías  

## 14. Instalación del Servidor  
### 14.1 Instalación de RAID 5 por Software  
### 14.2 Creación de Usuarios para Trabajadores  
### 14.3 Instalación de Aomei Backupper Server y Copia del Disco del Sistema  
### 14.4 Restauración de la Copia de Seguridad del Sistema  
### 14.5 Ubuntu Server  
### 14.6 Romper el RAID y Recuperarlo  

 


   
## Introducción

**CPD PARA UNA RED SOCIAL PARA PRODUCTOS DE SUPER MERCADO**  

Este trabajo consiste en un proyecto de gestión de un CPD virtual que estará dedicado exclusivamente a alojar la red social para la comparación de precios de supermercados, proporcionado los recursos informáticos necesarios para garantizar su escalabilidad, seguridad y disponibilidad.  

En el CPD se encargará de almacenar toda la información de la red social más todos los datos que pasen por la red es decir los usuarios, productos, imágenes, precios, ubicaciones de los supermercados. 

1. **Objetivos<a name="_page2_x69.00_y348.00"></a> del Proyecto**
- **Garantir la disponibilidad y escalabilidad de la aplicación** 
- Hay que asegurar que la aplicación esté disponible 24/7 para todos los usuarios. 
- Tenemos que aumentar la capacidad sobre si crece el número de usuarios de la aplicación.  
- Implementar un sistema de monitoreo para detectar y resolver problemas antes de que lleguen al usuario. 
- Usaremos también servicios en la nube para tener una alta confiabilidad que así nos pueda asegurar un tiempo de actividad casia del 100%.  
- Podemos utilizar contendedores Docker para poder escalar rápidamente de los servicios. 
- **Seguridad de los datos**  

  Es para poder proteger los datos de accesos no autorizados y manipulaciones indebidas. 

- Vamos a implementar los protocolos SSL/TLS para así encriptar todas las comunicaciones entre los usarios y el servidor. Para poder garantir que la información transmitida como los datos personales, fotos y ubicaciones no sean interceptados por terceros para hacer el mal.  
- Configuraremos automáticamente redirecciones de HTTP a HTTPS para evitar accesos inseguros  
- Vamos a cumplir las regulaciones de protección de datos como el GDPR, para garantizar la confianza de los usuarios por proporcionar una aplicación segura, transparente y con su privacidad.  
- **Asegurar la integridad y actualización de la información** 

  Para garantizar la integridad de los datos almacenados para que no sean alterados de manera que no esté autorizada y que los usuarios suban por ejemplo precios que no son coherentes.  

- Implementar reglas de validación para garantizar que los datos ingresados por los usuarios o empresas externas sean correctos y consistentes.  
- Tener un sistema de control de versiones para los datos de forma que si hay alguna actualización o cambio que registrado así podemos revertir a versiones anteriores si fuera necesario de la aplicación.  
- Mantener un registro detallado de todas las modificaciones en la red social, incluyendo quién realizó el cambio, cuándo y qué información se ha modificado.   
- Implementar controles de acceso basados en roles para poder asegurar que solo los usuarios que estén autorizados puedan modificar ciertos datos.  
- **Proporcionar una alta disponibilidad y recuperación delante desastres**  

  Podemos implementar una infraestructura que este distribuida en múltiples zonas de disponibilidad como servicios en la nube. Para poder garantizar la disponibilidad de la red social.  

  Almacenar copias de seguridad de la aplicación por si hay algún problema poder tener los datos almacenados y no perder la información.  

2. **Requisitos<a name="_page3_x69.00_y542.00"></a> Funcionales**
- **Gestión de usuarios de la aplicación** 
- Que se puedan registrar y autentificar en la aplicación, tener una gestión de diferentes roles como (admin, usuario), también añadir una funcionalidad para que los usuarios puedan editar su perfil y así añadir los productos de los supermercados a la red social.  
- **Gestión de los productos** 
- Posibilidad de editar la información de los productos existentes. 
- Funcionalidad para eliminar productos obsoletos o descontinuados. 
- Tener categorías para los productos y una mejor gestión y búsqueda.  
- **Gestión de precios**  
- Mantenimiento de un registro de cambios de precios a lo largo del tiempo. 
- Implementación de promociones y descuentos en los precios de los productos. 
- **Gestión de imágenes de los productos**  
- Permitir a todos los usuarios poder subir imágenes de los productos. 
- Posibilidad de editar o reemplazar las imágenes de los productos. 
- Los administradores puedan eliminar imágenes obsoletas o incorrectas. 
- **Gestión de localización de los supermercados** 
- Permitir a los administradores registrar la ubicación de los supermercados. 
- Funcionalidad para que los usuarios puedan buscar supermercados por ubicación. 

<a name="_page4_x69.00_y365.00"></a>**1.4 Requisitos No Funcionales**

- **Escalabilidad**  
- Posibilidad de poder aumentar la cantidad de usuarios y así el volumen de datos generados y almacenados. 
- Si fuera necesario implementar escalado horizontal y vertical en el cpd para aumentar con más servidores si fuera necesario. 
- **Rendimiento**  
- Hay que asegurar que las operaciones de carga y actualización de precios se realicen en tiempos de respuesta aceptables, incluso en picos de carga altos.  
- Tener optimizado las consultad a la base de datos para asegurar una rápida recuperación de la información. 
- **Seguridad y privacidad**  
- Tener los datos protegidos de todos los usuarios, con la encriptación para tener una mayor seguridad. 
- Que la aplicación (red social) cumpla con las normativas de protección de datos aplicables. 
- **Alta disponibilidad**  
- Implementar sistemas redundantes y mecanismos de tolerancia a fallos para asegurar la disponibilidad continua del servicio. 
- **Mantenibilidad** 
- Tener una serie de copias de seguridad diarias que serían las incrementales y una vez a la semana que fuera una copia de seguridad completa que se guardaría en un servidor aparte cerca de nuestro cpd para tener mayor respaldo. 
2. **Análisis<a name="_page5_x69.00_y171.00"></a> de requisitos**

Nuestro CPD no requerirá una gran cantidad de hardware ni de última generación, ya que la red social en la que nos enfocaremos está en proceso de darse a conocer y aún no cuenta con muchos usuarios simultáneamente. Si en el futuro logra ganar popularidad, entonces consideraremos añadir más hardware y potencia.

Analizaremos las necesidades de hardware, software y red.

**FUNCIONES DEL CPD** 

1. **Requisitos<a name="_page5_x69.00_y339.00"></a> de Hardware**

Nuestro CPD no requerirá una gran cantidad de hardware ni de última generación, ya que la red social en la que nos enfocaremos está en proceso de darse a conocer y aún no cuenta con muchos usuarios simultáneamente. Si en el futuro logra ganar popularidad, entonces consideraremos añadir más hardware y potencia.

- **Procesamiento:** 
- Servidores capaces de manejar imágenes subidas por usuarios y procesar búsquedas rápidas.
- Capacidad para reconocer las imágenes. 
- CPU con al menos 8 núcleos por servidor. 
- **Memoria RAM:** 
- 32 GB por servidor como comienzo, escalable según los usuarios.
- **Almacenamiento:** 
- Almacenamiento inicial de 5 TB para imágenes y datos.
- Crecimiento estimado de 10 TB en el primer año dependiendo del éxito de la plataforma. 
- Discos SSD para acceso rápido a imágenes y datos.
2. **Requisitos<a name="_page5_x69.00_y666.00"></a> de Software**
- **Sistema Operativo:** 
- Windows Server 2022 
- **Bases de Datos:** 
- Para usuarios, productos y precios utilizaremos MySQL, para imágenes utilizaremos NoSQL. 
- **Seguridad:** 
- Certificados SSL/TLS para proteger las comunicaciones.
- Cifrado de contraseñas y datos sensibles.
3. **Requisitos<a name="_page6_x69.00_y242.00"></a> de Red**
- **Conectividad:** 
- Alto ancho de banda para manejar el tráfico de imágenes, búsquedas concurrentes. 
- Iniciamos con 1 Gbps escalable a 10 Gbps, dependiendo de los usuarios concurrentes y el tráfico de imágenes de la red social.
- **Infraestructura de la red:** 
- Balanceadores de carga para distribuir el tráfico entre múltiples servidores. 
- **Disponibilidad:** 
- Sistema de recuperación ante fallos para garantizar un servicio continuo.
- **Seguridad de la Red:** 
- Firewall. 
- Usaremos VLANs para aislar cada zona. 
- Acceso remoto seguro a la red de administración mediante VPN.
- Protección DDoS. 

**FUNCIONES DE LA RED SOCIAL** 

4. **Capacidades<a name="_page6_x69.00_y575.00"></a> Técnicas Necesarias**
- **Usuarios concurrentes:** 
- Estimación inicial de 1000 usuarios activos a la vez.
- Escalabilidad para poder llegar a soportar hasta 10000 usuarios a la vez en nuestra red social. 
- **Gestión de Imágenes:** 
- Sistema que permita almacenar, procesar y mostrar imágenes con rapidez. 
- **Actualización en tiempo real:** 
- Servicios en tiempo real para actualizar precios de productos en el mismo momento. 
5. **Ejemplo<a name="_page7_x69.00_y115.00"></a> de un posible escenario para el uso de la red social**
- **Subida de foto:** 
- El usuario sube una imagen del producto y el sistema identifica de qué tipo de producto se trata. 
- La foto y la información del precio se almacenan en la base de datos. 
- **Búsqueda de Precios:** 
- La red social responde con dos imágenes: una que muestra el precio más bajo del producto de la misma marca y otra que presenta un producto de una marca diferente, pero a un precio más bajo.
- **Actualización de precios:** 
- Si un usuario encuentra un precio más bajo para el producto, puede cambiarlo y actualizarlo automáticamente en la base de datos. 

<a name="_page7_x69.00_y436.00"></a>**3 Cronograma del proyecto**  



|||**Tiempo** |||
| :- | :- | - | :- | :- |
|**Personas** |Actividades |Empieza |Acaba |Tareas Acabadas |
|Jordi** |1\.Definicion de los objetivos del proyecto |09/01/2025 |16/01/2025 |x |
|Dani** |2\.Anlisis de requisitos |09/01/2025 |13/01/2025 |x |
|Ivan,Jordi,Dani** |3\.Elaboracion del cronograma del proyecto |09/01/2025 |||
|Ivan** |4\.Assignació de roles y responsabilidad planificación |09/01/2025 |13/01/2025 |x |
|Jordi** |5\.Identificacion de recursos necesarios |13/01/2025 |18/01/2025 |x |
|Dani** |6\.Avaluación de riesgos y |13/01/2025 |18/01/2025 |x |
||planificación de contingencias  ||||
| :- | :- | :- | :- | :- |
|Ivan** |7\.Revisión y aprobación del plan de proyecto |09/01/2025 |||
<a name="_page8_x69.00_y142.00"></a>**4. Asignación de roles y responsabilidades**

**Líder:** 

En nuestro grupo hemos llegado a la conclusión de que Dani será el líder y se encarga de organizar las tareas del grupo y será el portavoz. En la plataforma trello se pondrá de administrador y desde ahí organizará las tareas, las horas, designará a cada cual su tarea y supervisará cada tarea al ser concluida.

En la Plataforma trello tenemos toda la planificación del proyecto desde ahí plateamos las actividades y desde ahí podemos organizarlas por: hechas no hechas y en proceso, también tenemos un índice donde tenemos todas las tareas presentes. El grupo elegirá dos actividades que serán designadas a un miembro para hacer y será el responsable de sus tareas, luego el grupo lo evaluará y el líder tendrá la última palabra, después a la hora de exponer debatiremos como lo estructuraremos y como lo presentaremos.

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%201.png)

1. **Los<a name="_page8_x69.00_y630.00"></a> Roles del equipo**

**-El líder**, que es Dani 

**Su responsabilidad es:** 

- **Liderazgo estratégico:** Define objetivos, planifica el proyecto y asegura el cumplimiento de metas. 
- **Coordinación del equipo:** Supervisa las tareas diarias, asigna responsabilidades y garantiza que el flujo de trabajo sea eficiente.
- **Análisis y requisitos:** Recopila y documenta las necesidades de los stakeholders, transformándolas en especificaciones claras.
- **Comunicación externa:** Actúa como portavoz, reportando avances y resultados a los interesados. 
- **Resolución de conflictos:** Facilita la colaboración y soluciona problemas dentro del equipo. 

**-El implementador**, que es Jordi  

**Su responsabilidad es:** 

- **Desarrollo técnico:** Diseña, implementa y optimiza las soluciones técnicas necesarias. 
- **Soporte técnico:** Identifica y soluciona problemas técnicos que surjan durante el desarrollo del proyecto. 
- **Pruebas y validaciones:** Asegura que las soluciones implementadas funcionen correctamente. 
- **Documentación técnica:** Registra configuraciones, desarrollos y ajustes realizados. 

**-Responsable de calidad y operaciones,** que es Iván 

**Su responsabilidad es:** 

- **Gestión operativa:** Monitorea el cumplimiento de las actividades según el plan del líder. 
- **Control de calidad:** Realiza pruebas para verificar que los entregables cumplan con los estándares requeridos.
- **Gestión de recursos:** Coordina materiales, herramientas y logística necesarios para el proyecto. 
- **Apoyo en documentación:** Colabora con el líder para documentar avances y resultados. 
2. **Dinámica<a name="_page9_x69.00_y665.00"></a> entre roles**
- **Líder:** 

  Define y prioriza tareas, además de monitorear su progreso.

  Supervisa el trabajo del técnico y el responsable de calidad, alineándolos con los objetivos del proyecto. 

  Comunica los avances y toma decisiones clave en base a reportes del equipo.

- **Especialista Técnico:** 

  Se concentra en el desarrollo y ejecución técnica de las soluciones, asegurándose de que sean funcionales y eficientes.

- **Responsable de Calidad:** 

  Da soporte al líder, asegurándose de que las tareas se completen a tiempo y que los entregables cumplan con los estándares de calidad.

  Gestiona los recursos necesarios para el equipo técnico.

3. **El<a name="_page10_x69.00_y463.00"></a> Trabajo se basa en 7 actividades:** 

**Actividad 1** 

**Definición de los objetivos del proyecto-** aquí vamos a explicar la empresa que vamos a hacer: de que va a tratar el proyecto, para que vaya a servir el cpd, como se va a organizar, que va a mejorar o para que vaya a servir y que impacto va a tener. 

Act1 se Encarga Jordi 

**Actividad 2** 

**Análisis de requisitos-** aquí vamos a hacer una estimación de que tipo de maquinaria y software vamos a necesitar, también vamos a pensar que tipo de medidas de seguridad vamos a tener como por ejemplo alarmas de fuego, extintores, cámaras de seguridad, que tipo de refrigeración necesitan los cpd etc. También vamos a pensar donde tendremos nuestras instalaciones y como serán, también pensaremos nuestros trabajadores que tipo de estudios necesitan y como deben trabajar.

Act2 se encarga Dani  

**Actividad 3** 

**Elaboración del cronograma del proyecto-** Aquí vamos a organizar un croquis de cómo nos vamos a organizar, por ejemplo: Que hemos hecho en un día quien lo ha hecho y fechas y horas y una pequeña valoración del resultado. 

Act3 se encarga Ivan,Jordi,Dani 

**Actividad 4** 

**Asignación de roles i responsabilidades-** Este punto habla de que se va a hacer y de los roles de cada uno. 

Se Encarga Ivan 

**Actividad 5** 

**Identificación de recursos necesarios-** Aquí vamos a ver que material necesitamos que productos de que clase y de qué tipo de material y vamos a crear un presupuesto de empresa a ver cuál sería el total. 

Act5 se encarga Jordi 

**Actividad 6** 

**Evaluación de riesgos i planificación de contingencias-** Aquí hablaremos de como afectara negativamente el cpd y los riesgos laborales, por ejemplo: como afectar negativamente el medioambiente o de que peligros pueden a ver trabajando en el cpd que tipo de vestimenta necesitan los trabajadores. 

Act6 se encarga Dani 

**Actividad 7** 

**Revisión i aprobación del plan de proyecto-** Aquí hablaremos y valoraremos como es el estado del producto y si procedemos a la ejecución.

Act7 se encarga Dani 

<a name="_page11_x69.00_y601.00"></a>**5 identificación de recursos necesarios.**

Determinar la disponibilidad de recursos:

Para poder crear este proyecto lo vamos a hacer 3 persona que serían Dani, Iván y Jordi. Para poder gestionar la aplicación de la red social del supermercado.  

Esto sería un resumen de los recursos necesarios que creemos que serían necesarios para el CPD 

1. **Recursos<a name="_page12_x69.00_y73.00"></a> Humanos** 



|Rol  |Responsabilidad |<p>Cantida</p><p>d </p>|Disponibilidad  |Precio Estimad o |<p>Observacio</p><p>nes </p>|
| - | - | - | - | :-: | - |
|Administras sistemas  |Configurar y mantener servidores |1 |Media |1,700€ por persona |Clave para asegurar estabilidad del CPD |
|Desarrollad or web ||1 |Media |1,700€ por persona |Trabajar en srpints |
|Gestor de Proyectos |Planificación seguimiento y reportes  |1 |Media |1,700€ por persona |Asegurar el cumplimie nto de plazos y objetivos |

2. **Costes<a name="_page12_x69.00_y547.00"></a> de Hardware**  



|**Componente** |**Especificaciones** |**Cantidad** |**Precio unitario** |**Precio total estimado** |
| - | - | - | :- | :- |
|Servidores |CPU: 8 núcleos, 24 GB RAM, 5 TB SSD |2 |5,000€  |10,000€ |
|Almacenamiento SSD |SSD de 5 TB |4 |1,500€ |6,000€ |
|Backup Externo |Dispositivo NAS para copias de seguridad |2 |2,500€ |5,000€ |
|Redundancia UPS |Suministro de energía  |1 |800€ |800€  |

3. **Costes<a name="_page13_x69.00_y101.00"></a> de Software** 



|**Software** |**Licencias** |**Cantidad** |**Precio unitario** |**Precio total estimado** |
| - | - | - | :- | :- |
|Sistema Operativo |Windows Server 22 |2 |0 |Software de pago  |
|Base de Datos MySQL |Licencia Enterprise |1 |500€ |500€ |
|Base de Datos NoSQL |MongoDB |1 |0 |Edición comunitaria gratuita |
|Certificado SSL |Certificado de Seguridad |1 |150€  |150€  |

Hemos elegido Windows Server 22 para gestionar el CPD por sus características y que utiliza una interfaz gráfica que es más intuitiva que Linux que sería por comandos. Además, tiene unos paquetes de Microsoft que nos pueden ayudar a la gestión del CPD Las licencias necesarias de Windows las cubre la empresa de la aplicación del supermercado dependiendo la que utilizaremos tendrá un coste. 

Vamos a utilizar MongoDB para el almacenamiento de imágenes dentro de la aplicación del supermercado es una decisión estratégica que nos permite ofrecer un servicio rápido, seguro y escalable. Con el uso de GridFS, la arquitectura flexible y la alta disponibilidad de nuestro CPD, podemos asegurar una experiencia de usuario óptima y una gestión eficiente de las imágenes. 

- MongoDB permite guardar imágenes y metadatos en un mismo documento, evitando la necesidad de múltiples bases de datos como en SQL.
4. **Costes<a name="_page13_x69.00_y575.00"></a> de Red** 



|**Componente** |**Especificaciones**||**Cantidad** |**Precio** |**Precio total** |
| - | - | :- | - | - | - |
|||||**unitario** |**estimado** |
|Router |Compatible con ||1 |1,000€ |1,000€ |
|Empresarial |1Gbps/10 Gbps |||||
|Switch |24 Puertos con ||1 |800€ |800€ |
|Administrable |VLAN |||||
|Balanceador de |Hardware ||1 |2,500€ |2,500€ |
|Carga |dedicado para |||||
||distribuir tráfico |||||
|Firewall Empresarial |Seguridad avanzada contra amenazas |1  |1,500€ |1,500€ ||
|Acceso VPN |Licencias para usuarios |1 |200€ |200€ ||

Vamos a utilizar un balanceador de carga físico por un mayor rendimiento, tener menor latencia y menor uso de CPU en los servidores. También nos garantiza más rendimiento, fiabilidad y escalabilidad en comparación a una solución con software. A pesar de que una solución basada en software puede ser viable en algunos casos, en nuestro contexto empresarial y técnico, el coste-beneficio de un dispositivo físico justifica plenamente la inversión 

5. **Costes<a name="_page14_x69.00_y333.00"></a> de Infraestructura y Mantenimiento**



|**Elementos** |**Descripción** |**Frecuencia** |**Precio total estimado** |**Observaciones** |
| - | - | - | :- | - |
|Hosting |Inicial de CPD virtual |Mensual |300€ |Escalabilidad hasta 10 Gbps |
|Dominio |Nombre de la red social |Anual |20€  |Precio estimado para un dominio .com |
|Energía eléctrica |Costo operativo de servidores |Mensual |200€ |24/7 en funcionamiento |
|Renovación Certificado SSL |Proteger la red |Anual |150€ |Mantener la comunicación segura |
|Actualizaciones de Software |Mantenimien to y actualización |Mensual |100€ |Optimizaciones periódicas |
|Ordenadores |3 equipos para la administraci ón |Anual |3,000€ |Los equipos tienen una vida útil de 3 a 5 años antes de necesitar sustituciones |

6. **Estimación<a name="_page14_x69.00_y711.00"></a> Financiera**  



|Categoría |Coste Total Estimado €  |
| - | - |
|Infraestructura  |3\.800€  |
| - | - |
|Hardware  |21\.800€ |
|Software  |650€ |
|Red |6\.000€ |
|Recursos Humanos |5\.100€ |
|`                                                                         `Total |`  `37.350€ |

<a name="_page15_x69.00_y167.00"></a>**6. Evaluación de riesgos y planificación de contingencias** 

En este punto, vamos a identificar los posibles riesgos que podrían afectar al CPD y a desarrollar estrategias para prevenir que estos riesgos se materialicen.

1. **Identificación<a name="_page15_x69.00_y273.00"></a> de riesgos** 
- **Riesgos técnicos:**  
- Sobrecarga del sistema debido al aumento inesperado de usuarios.
- Perdida de datos por errores en el almacenamiento o fallos en las copias de seguridad. 
- **Riesgos de seguridad:** 
- Ataques de tipo DDoS, phishing o inyecciones SQL que puedan afectar la plataforma. 
- Fuga de datos personales de nuestros usuarios registrados.
- **Riesgos operativos:** 
- Retrasos en la configuración del CPD. 
- Falta de capacidad en el personal.
- **Riesgos financieros:** 
- Sobrecostos en el presupuesto estimado del proyecto.
2. **Evaluación<a name="_page15_x69.00_y548.00"></a> de los riesgos** 

Vamos a evaluar diferentes riesgos en una tabla identificando el impacto, probabilidad y el nivel de riesgo que supone, todo en una escala de bajo, medio y alto.



|**Riesgo** ||**Impacto** |**Probabilidad** |**Nivel de Riesgo** |
| - | :- | - | - | - |
|Sobrecarga del Sistema  ||Alto |Medio |Alto |
|Perdida de datos ||Alto |Bajo |Medio |
|Ciberataques ||Alto |Alto |Alto |
|Fuga datos personales ||Alto |Medio |Alto |
|Retrasos en la configuración ||Medio |Medio |Medio |
|Sobrecostos de presupuestos||Alto |Bajo |Medio |

3. **Plan<a name="_page16_x69.00_y73.00"></a> de contingencias** 
- **Riesgos técnicos:**  
  - **Sobrecarga del sistema:** Vamos a implementar un balanceador de carga para prevenir este problema.  
  - **Pérdida de datos:** Se configurarán copias de seguridad automáticas que se realizarán de forma completa cada semana y de manera incremental cada día que se guardarán en un NAS externo. Además, contaremos con un plan para almacenar datos en la nube.
- **Riesgos de seguridad:**  
  - **Ciberataques:** Instalaremos un firewall físico y estaremos monitorizando el tráfico de la red utilizando diversas herramientas. Además, utilizaremos VPN para accesos remotos seguros.
  - **Fuga de datos personales:** Implementaremos cifrado de datos en tránsito, como SSL, y restringiremos el acceso a la información mediante un riguroso control de acceso.
- **Riesgos operativos:**  
- **Retrasos en la configuración del CPD:**  Crearemos un cronograma detallado que incluya hitos y responsables asignados, además de realizar reuniones semanales para monitorear el progreso.
- **Falta de capacidad en el personal:** Organizaremos talleres y sesiones 

  de capacitación para el equipo técnico, así como academias de inglés para facilitar la comunicación con usuarios que no dominen el idioma.

- **Riesgos financieros:**  
- **Sobrecostos:**  Destinaremos un 20% del presupuesto inicial para cubrir posibles sobrecostos.
4. **Protocolos<a name="_page16_x69.00_y538.00"></a> de actuación** 

Para el tema de monitorización vamos a utilizar Prometheus ya que es más escalable y optimizado para entornos en la nube y obtiene métricas en tiempo real. 

- **Ante grandes fallos:** 
1. Detección y Notificación del problema 
1. Diagnóstico y evaluación 
1. Respuesta y Solución 
1. Verificación y Restauración 
1. Informe y Prevención 
**Página 17 de 17  Daniel Dumea, Ivan Catalá, Jordi Escriva**

1. Segmentación<a name="_page2_x69.00_y693.00"></a> por VLAN’s 
- **VLAN 10 – Usuarios internos** 
- Contiene las estaciones de trabajo con direcciones en el rango 192.168.10.X 
- Se conectan a los switches de red para acceder a los servicios del CPD.
- **VLAN 20 Administración y Operaciones:** 
- Incluye equipos administrativos con direcciones en 192.168.20.X
- Tienen acceso restringido a ciertos servicios. 
- **VLAN 30 – Infraestructura del CPD:** 
- Aloja los servidores y dispositivos de almacenamiento.
- Incluye el Servidor Controlador Principal, el Servidor de Aplicaciones y Bases de Datos, y el Servidor de Respaldo que está ubicado en un diferente lugar. 
- Integra sistemas como NAS y SAI para garantizar la continuidad del servicio. 
2. Conectividad<a name="_page3_x69.00_y304.00"></a> y Flujo de Datos 
- Un switch principal se encarga de interconectar las VLANs.
- El tráfico de datos fluye desde las estaciones de trabajo (VLAN 10 y VLAN 20) hacia los servidores (VLAN 30). 
- Existe un enlace a Internet a través de un router.
3. Seguridad<a name="_page3_x69.00_y436.00"></a> y Respaldo 
- **Servidor de Respaldo** para copias de seguridad y recuperación ante fallos.
- **SAI** para evitar pérdida de datos ante cortes eléctricos.
- **NAS** como almacenamiento centralizado para compartir archivos de manera eficiente. 
2. **Selección de maquinaria i software**

Primero que todo haremos una comparativa de los S.O que podemos utilizar como son el Ubuntu Server y el MS Windows Server 2022. Para saber cuál de los dos nos beneficia más a nuestro CPD para gestionarlo y ponerle las aplicaciones que sean necesarias.  

**Comparativa entre los dos sistemas operativos:** 



|**Características** |**Ubuntu Server 22.04** ||**Windows Server 2022** |
| - | - | :- | - |
|**Costo** |Es gratis de código abierto ||Tiene licencias de pago  |
|**Facilidad de uso** |Se gestiona con comandos||Tiene interfaz gráfica más |
||||amigable e intuitivo.  |
|**Compatibilidad** |Con aplicaciones web, ||Tiene un mejor soporte |
|**Software** |bases de datos y ||para aplicaciones |
||contenedores (MySQL, ||comerciales  |
||Docker) |||
|**Rendimiento** |Ligero, excelente ||Tiene un alto rendimiento, |
||rendimiento en hardware ||pero también un mayor |
||más modesto ||consumo |
|**Seguridad** |Una comunidad activa ||Secured-core, SMB cifrado |
||||y TILS 1.3 por defecto |
|**Virtualización** |LXD, KVM y soporte ||Hyper-V, soporte nativo |
||avanzado para ||para máquinas virtuales |
||contenedores |||
|**Escalabilidad** |Lo puedes escalable, ideal ||Muy escalable |
||para nubes híbridas y ||especialmente en |
||clústeres.  ||entornos de Microsoft |
|**Soporte en la nube** |Integración con AWS y ||Soporte con Azure y |
||Azure ||también con Windows |
||||admin |
|**Soporte Técnico** |Puede tener soporte ||Licencias de Microsoft que |
||comercial, pero es más ||son de pago para dar |
||opcional  ||soporte  |

**Qué sistema vamos a elegir:**  

Creemos que la mejor opción para gestionar nuestro CPD la mejor opción es la de **Windows Server 22**. Por qué podemos tener una interfaz gráfica que puede ser mucho más intuitiva que la de Ubuntu que sería por comandos entonces la administración con Windows sería más fácil por ser gráficamente y por las aplicaciones que incluye con Microsoft que son de pago pero que nos pueden ayudar mucho a la gestión del CPD para la aplicación de los productos de los supermercados, como Active Directory, SQL Server y Azure, además de soporte nativo para Hyper-V, ideal para virtualización. Su enfoque en la seguridad incluye características avanzadas como Secured-Core, SMB cifrado y TLS 1.3 por defecto, garantizando protección robusta para tus datos.

1. Servidores

<a name="_page5_x69.00_y73.00"></a>**Servidor 1: Controlador principal** 

- Funciones: Active Directory (gestión de usuarios), DNS, DHCP y supervisión básica. 
- Hardware:  
- CPU: Procesador de 8 núcleos Intel Xeon  
- RAM: 32 GB 
- Almacenamiento: SSD  4 TB para el S.O y los servicios  

**Servidor 2: Servidor de Aplicaciones y Bases de Datos**

- Funciones: SQL Server, aplicaciones empresariales o software de gestión de productos. 
- Hardware: 
- CPU: Procesador similar al primer servidor o más potente (16 núcleos).
- RAM: 32-GB (según la carga de la base de datos la podemos aumentar). 
- Almacenamiento: 2 TB en SSD para datos críticos y HDD de respaldo si se manejan grandes volúmenes.

**Servidor 3: Sera el servidor de respaldo**  

**Almacenaremos las copias de seguridad que tengamos en los servidores 1 y 2 por sí hay algun problema poder recuperar la información para poder seguir trabajando.**  

- Disponer de copias espejo para permitir una rápida restauración de Active Directory, servicios que tengamos instalados. 
- Sincronización de base de datos mediante SQL para poder recuperarlo si fuera necesario.  
- Configuraciones de redundancia (RAID) para mayor fiabilidad. 
2. Almacenamiento

<a name="_page6_x69.00_y73.00"></a>El almacenamiento que hemos elegido es el siguiente: 

- **Cabina de almacenamiento NAS (almacenamiento centralizado):**
- Capacidad inicial: 20 TB (RAID 5 para redundancia). 
- NAS será dedicado. 
- Tipos de disco: 
- SSD para datos críticos de alta velocidad.
- SSD para datos menos utilizados o copias de seguridad.
- **Opciones de escalabilidad:**
- Si necesitamos más servicios podremos contratar los servicios en la nube como Azure o AWS S3 para almacenamiento adicional, lo que nos puede reducir la necesidad de grandes inversiones iniciales en hardware.
3. Infraestructura<a name="_page6_x69.00_y339.00"></a> Adicional 

Para tener una virtualización estable, seguro y eficiente, es esencial contar con una infraestructura adicional que este adecuada. Eso incluye sistemas de alimentación redundantes, equipos de red avanzados y mecanismos de refrigeración eficientes. 

` `**Sistemas de alimentación redundantes** 

Vamos a utilizar UPS en línea: Nos ofrece una protección constante contra las variaciones de voltaje y cortes.  

**Características**:  

- Tiene una autonomía para mantener el sistema activo durante el tiempo necesario para activar generadores o aturar las máquinas virtuales de manera segura.  
- Podemos monitorizar de forma remota y tener notificaciones en tiempo real para avisarnos de lo que queramos. 
- El tema de la redundancia lo vamos a configurar N+1 para poder asegurar la continuidad operativa en caso de fallo de algún modulo. 

**Sistema de Refrigeración para Evitar sobrecalentamiento y otros problemas.**

Una buena gestión y diseño de refrigeración evita daños a los servidores y mantiene el rendimiento optimo de la infraestructura de virtualización. 

Vamos a utilizar la refrigeración por aire pensamos que es la más adecuada para nuestro CPD.  

**Refrigeración por aire características:**  

- Vamos a utilizar unidades de climatización (CRAC – Computer Room Air Conditioning). 
- Flujos de aire optimizados con ventiladores i con los racks cerrados podemos dirigir aire frio hasta los servidores que tenemos y al nas. 
- También tendremos la configuración de los pasillos calientes que recogen el aire que expulsa por la parte posterior de los servidores. 

**Pondremos también otros objetos adicionales como:** 

- Sensores de Temperatura y humanidad para tenerlo monitorizada en tiempo real.  
- Sistemas de ventilación redundantes para evitar los puntos de fallos únicos. 
- Utilizaremos sistema de refrigeración con tecnología de ahora energético para reducir costes operativos.  
4. Mecanismos<a name="_page7_x69.00_y440.00"></a> de Redundancia 

Sistemas de alimentación:  

Vamos a obtener un **SAIs** para poder garantizar la disponibilidad de energía en caso de cortes eléctricos, poder tener un tiempo que es limitado, pero nos pude salvar para poder hacer una copia de seguridad o también guardar la información en el NAS externo que tenemos para las copias de seguridad.  

También instalaremos generadores eléctricos junto al SAIs en el CPD para garantizar la continuidad del servicio durante los cortes eléctricos que podamos tener. 

5. Herramientas<a name="_page8_x69.00_y73.00"></a> de Virtualización

**Hyper-V:** Utilizaremos el hyper-v que ya viene integrado en Windows Server 2022 que nos permitirá crear y gestionar las máquinas virtuales que sean necesarias para nuesto centro de datos. Esto nos ayudará en los servidores y mejorar la eficiencia de hardware.  

**Aplicaciones de Gestión:**  

**Microsoft System Center Virtual Machine Manager (SCVMM):** Es una herramienta que nos ayudara a administrar y automatizar la implementación y la gestión de las máquinas virtuales en el entorno de Hyper-V.  

**Microsoft Azure  Site Recovery:** Este servicio nos dará protección y recuperación ante desastres que nos pueda surgir en las máquinas virtuales es como poder tener un respaldo por si pasara algo.   

**Monitoreo y Supervisión:** Utilizaremos Microsoft Operations Management Suite (OMS) para el monitorear el rendimiento y poder controlar la salud de nuestra infraestructura para poder hacer cambios antes de que se rompa algo de dentro del CPD y asi nos podemos proteger de que antes de que se rompa lo podemos detectar y cambiar para 

no parar el servicio del CPD.  

6. Contratación<a name="_page8_x69.00_y445.00"></a> de Servicios AWS S3

Vamos a contratar servicios externos que serán los de AWS S3 que es de Amazon. Lo vamos a contratar para poder mejor la gestión y el almacenamiento de datos de la aplicación del supermercado de la comparación de los precios. 

**Características:**  

- **Almacenamiento Seguro y Escalable:** AWS S3 no permite almacenar grandes volúmenes de datos seguro y escalable dependiendo de las necesidades. 
- **Alta Disponibilidad:** Con los servicios de AWS S3 nos podemos asegurar de que los datos estarán accesibles incluso cuando tengamos picos de tráfico altos. 
- **Copia de Seguridad y Recuperación:** AWS S3 nos facilita la creación de copias de seguridad regulares y poder recuperar los datos de forma rápida y segura en caso de tener algún problema o fallo. 
7. Dispositivos<a name="_page9_x69.00_y73.00"></a> que vamos a tener. 
- 5 Ordenadores: Que estarán en diferentes VLANS para poder gestionar el CPD 
- 2 switch: Para poder conectar los dispositivos de red como los servidores, ordenadores.  
- 1 Router: Para tener salida a Internet y también poder comunicarse entre las redes locales del CPD 
- 3 Servidores: Que serán el corazón del CPD donde se alojan las aplicaciones, servicios y bases de datos.  
- 1 NAS: Lo tendremos conectado a la red para poder guardar y compartir los datos.  
- 1 SAI: Nos permitirá poder guardar información cuando tengamos un fallo eléctrico temporal y no tendremos suministro eléctrico.
3. Diseño<a name="_page9_x69.00_y312.00"></a> de la seguridad del sistema 
1. Medidas<a name="_page9_x69.00_y353.00"></a> de Protección
- **3.1.1 Firewall perimetral:** 

Se instalará un sistema de cortafuegos para filtrar el tráfico que entra y sale del CPD (Como el software Waf) . Se configurarán reglas específicas para bloquear Direcciones ip sospechosas, limitar protocolos no necesarios y garantir que solo las conexiones seguras pudiendo acceder al sistema. Ejemplo: bloqueo automático de cualquier intento de conexión desde direcciones ip que no cumplan los requisitos de seguridad establecidos.

- **3.1.2 Sistemas de detección y prevención de intrusos (IDS/IPS)**

  Se hará uso de un sistema avanzado para monitorear el tráfico en tiempo real (Como el software snort), identificar posibles intentos de intrusión y tomar medidas preventivas automáticamente. Eso incluye, por ejemplo, el bloqueo de tráfico que muestre patrones de ataque como SQL inyection.

- **3.1.3 Cifrado de Comunicaciones**

  Todas las comunicaciones entre el usuario y la plataforma utilizaran protocolos seguros como HTTPS mediante certificado SSL/TLS. 

  Eso garantiza que los datos sensibles, como las contraseñas o las preferencias de productos, no sean interceptados por agentes externos

2. Protección<a name="_page10_x69.00_y73.00"></a> contra amenazas internas
- **3.2.1 Cifrado de base de datos** 

  Se utilizará algoritmos de cifrado como AES-256 Para proteger la información almacenada. Eso significa que, si un atacante consigue acceder a la base de datos, no podrá leer los datos sin las llaves de descifrado.

- **3.2.2 Acceso restringido a los datos**

Se implementará un modelo de mínimo privilegio que garantice que cada usuario del sistema solo tiene acceso a los datos necesarios para su función. Por ejemplo, los empleados solo pueden ver los datos relacionados con sus tareas y no pueden acceder a la información de los clientes. 

3. Respuesta<a name="_page10_x69.00_y295.00"></a> ante ciberataques
- **3.3.1 Copias de seguridad regulares:**

Se configurarán copias de seguridad automatizadas que se guardarán en servidores redundantes, situados en ubicaciones geográficas diferentes para prevenir la perdida de datos en caso de un ataque o desastre

Ejemplo: si un ataque de ransomware afecta el CPD principal, se podrá restaurar el sistema desde una copia de seguridad hecha 24 horas antes.

- **3.3.2 pruebas de intrusión** 

Se realizarán pruebas de intrusión periódicas para identificar vulnerabilidades en el sistema antes d que puedan ser explotadas por atacantes externos o internos. 

4. Politicas de seguridad
- **3.4.2 Autenticación multifactorial (MFA)** 

  Todos los administradores y empleados del supermercado que gestionan la plataforma tendrán que utilizar MFA. Eso incluye la combinación de una contraseña según el factor de autenticación, como un código enviado a un móvil o una aplicación de autenticación como Google authenticator

  Ejemplo: Un administrador que intenta acceder al tablero de gestión tendrá que introducir su contraseña y verificar un código temporal enviado a su teléfono 

- **Gestión de roles** 

  Se definirán diferentes roles con permisos específicos:

  **Usuario**: Puede ver y publicar comentarios sobre productos, añadir productos a listas de preferidos y editar su perfil.

  **Moderador**: Puede revisar comentarios inapropiados y bloquear usuarios que incumplan las normas.

  **Administrador**: Tiene acceso completo al sistema, incluyendo la gestión de contenido y usuarios. 

- **Registro y auditoria de acceso** 

  Se registrarán todas las acciones realizadas para cada usuario, incluyendo acciones de administrador. Así ayudara a identificar cualquier actividad sospecha o no autorizada.

5. Políticas<a name="_page12_x69.00_y73.00"></a> de protección de datos 

   Análisis de datos sensible: 

   Se clasificará la información según su nivel de sensibilidad. Por ejemplo, datos personales de los usuarios (nombre, correo electrónico) se consideran de alto nivel y requerirán medidas adicionales de protección.

   Tiempo de retención: 

   Los datos de los usuarios que dejen de utilizar la plataforma se mantendrán solo por el tiempo necesario para cumplir con las normativas legales y se destruirán de manera segura después de este periodo.

   **3.5.1 Monitorización continua** Análisis en tiempo real: 

   Se utilizará una herramienta de monitorización de \*logs para identificar patrones de comportamiento anómalos, como accesos masivos desde una sola dirección IP o intentos constantes de inicio de sesión fallados.

   Alertas automáticas: 

   El sistema generará alertas automáticas en caso de actividades sospechosas, como cambios masivos a la base de datos o el intento de acceso desde una ubicación geográfica no reconocida.

6. Seguridad<a name="_page12_x69.00_y526.00"></a> en dispositivos móviles 

   Como que muchos usuarios accederán a la red social desde dispositivos móviles, tenemos que implementar reglas específicas para proteger estas conexiones: 

- **Autenticación biométrica:**  

  ` `Opción de iniciar sesión como imprenta dactilar o reconocimiento facial.

- **Protección contra aplicaciones maliciosas:**

  Verificación de que la aplicación oficial se descargue solo des de fuentes seguras como Google play y Apple store 

- **Control de sesiones activas:**

  Los usuarios pueden ver y gestionar dispositivos conectados por su cuenta

- **Cifrado de datos en móviles** 

  Todos los datos almacenados localmente a la app se cifran para evitar el robo en caso de pérdida o robo del dispositivo

7. Resultado<a name="_page13_x69.00_y249.00"></a> esperado

   Con este diseño de seguridad, se espera obtener: Confidencialidad: 

   Todos los datos personales y de uso de los usuarios estarán protegidas mediante medidas de cifrado y controles de acceso. Los atacantes no podrán acceder a información sensible.

   Integridad: 

   Los datos almacenados al sistema no podrán ser modificadas de manera no autorizada gracias a las medidas de control y registro implementadas.

   Disponibilidad: 

   El sistema se mantendrá operativo incluso en caso de ataques o errores técnicos, gracias a las copias de seguridad y la redundancia del \*CPD.

   ` `Ejemplo práctico: 

   Un usuario puede acceder en la red social sabiendo que sus datos están protegidos. En caso de un ataque, los sistemas de seguridad bloquean la acción inmediatamente y los administradores pueden actuar según el protocolo establecido. 

4. **Diseño<a name="_page13_x69.00_y692.00"></a> de el plan de recuperación frente a desastres.** 
- **Propósito del plan:** 

  Garantizar la continuidad de la red social de productos de supermercado ante fallos críticos o desastres, minimizando la pérdida de datos y tiempo de inactividad. 

- **Objetivos Específicos:** 
- Definir procedimientos para realizar copias de seguridad periódicas.
- Establecer estrategias para la restauración rápida de sistemas y datos.
- Asegurar la integridad y disponibilidad de los datos almacenados.
1. **Estrategia<a name="_page14_x69.00_y211.00"></a> de Copias de Seguridad** 
- **Copias completas:** 
- Se realizan semanalmente para guardar una imagen completa de todos los datos. 
- Ventaja: Todo está en un solo punto de restauración.
- Desventaja: Toma más tiempo y espacio.
- **Copias incrementales:** 
- Se realizan diariamente para guardar solo los datos nuevos o modificados desde la última copia. 
- Ventaja: Reduce el tiempo y espacio requerido.
- Desventaja: Depende de la última copia completa.
2. **Almacenamiento<a name="_page14_x69.00_y435.00"></a> de las Copias** 
- **Almacenamiento local:** 
- RAID 5 para tolerancia a fallos y redundancia. 
- Acceso rápido a copias en servidores internos.
- **Almacenamiento en la nube:** 
- Contratación de servicios AWS S3. 
- Alta disponibilidad y recuperación en caso de pérdida de datos local.
3. **Restauración<a name="_page14_x69.00_y640.00"></a> de Sistemas y Datos** 
- **Procedimientos de restauración:**
1. Evaluar la causa del fallo. 
1. Seleccionar la copia de seguridad adecuada. 
1. Restaurar datos. 
- **Pasos detallados de Restauración:**
- Desplegar la infraestructura básica desde la copia completa más reciente.
- Aplicar las copias incrementales o completas.
- Verificar la integridad de los datos restaurados.
- Reiniciar los servicios afectados.
4. **Mecanismos<a name="_page15_x69.00_y152.00"></a> de Redundancia** 
- **Sistemas de alimentación:**
- SAIs 
- Garantizar la disponibilidad de energía en caso de cortes eléctricos.
- Instalación de generadores en el CPD.
- **Redundancia de Datos:** 
- RAID de nivel 5 debido a que tenemos 4 discos. 
- Configurar replicación a través de la nube para proteger la información.
- **Backup distribuido:** 
- Tendremos otra copia en otro lugar distinto a donde está situado nuestro CPD (estará en un centro de datos ubicado en Benirrera, Valencia).
5. **Documentación<a name="_page15_x69.00_y377.00"></a> y Pruebas Regulares** 
- **Documentación de procedimientos:**
- Guías claras para el equipo técnico sobre la configuración y el monitoreo de las copias de seguridad y el procedimiento para restaurar datos y sistemas.
- **Pruebas regulares:** 
- Realizaremos pruebas cada 3 meses de desastres para:
- Verificar que las copias de seguridad se restauren correctamente.
- Medir los tiempos de recuperación.
- Identificar puntos de mejora en los procedimientos.
5. Manual<a name="_page16_x69.00_y73.00"></a> de Usuario del CPD 

El manual de los usuarios servirá para poder orientar a todos los Usuarios que puedan entrar al Centro de Procesamiento de Datos (CPD) sobre el uso correcto de los sistemas, las normas de acceso y uso y las buenas prácticas para poder asegurar la continuidad y seguridad del servicio del CPD.  

1. Acceso<a name="_page16_x69.00_y209.00"></a> al Sistema  
- **Al Iniciar sesión** 
- Conectar los ordenadores de trabajo a la VLAN correspondiente.
- Ingresar al sistema con las credenciales asignadas necesarias. 
- **Reglas de uso**  
- Mantener la confidencialidad de las credenciales.
- No compartir accesos con terceros
- Informar de cualquier actividad sospechosa al administrador del sistema 
2. Uso<a name="_page16_x69.00_y412.00"></a> de Recursos del CPD  
- **Acceso a servidores** 
- Utilizar el protocolo RDP o SHH para la gestión remota de los servidores.
- Limitar las conexiones a lo que sea necesario para que puedan trabajar.
- **Almacenamiento en NAS**  
- Acceder a los recursos compartidos mediante autenticación si nos no se pude acceder. 
- Respetar las políticas de almacenamiento y organización de archivos.  
- **Copias de Seguridad**  
- No modificar ni eliminar archivos destinados a backups 
- Consultar al administrador si se requiere restaurar algún dato de alguna copia.  
3. Resolución<a name="_page16_x69.00_y663.00"></a> de Problemas 
- **Problemas de inicio de sesión** 
- Verificar que las credenciales son las correctas
- Confirmar que estas en la VLAN adecuada para tener acceso a los servidores e internet.  
- Contactar con los administradores (soporte técnico) por si el problema sigue y los usuarios no pueden solucionar
- **Pérdida de conexión**  
- Revisar el estado de la conexión física y la configuración de red. 
- Notificar al administrador y servicio técnico si hay caídas del servicio. 
- Revisar que las conexiones dentro de los servidores esta todo correcto y no hay ningún cable de red desconectado. 
6. Guía<a name="_page17_x69.00_y285.00"></a> de Administración del CPD

Esta guía está destinada a los administradores responsables de la gestión, mantenimiento y seguridad del CPD. Contiene procedimientos clave alineados con la arquitectura definida en el proyecto, asegurando el funcionamiento óptimo, seguro y eficiente del sistema. 

1. Gestión<a name="_page17_x69.00_y414.00"></a> de Servidores
- **Controlador Principal** 
- Revisar periódicamente el estado de Active Directory, DNS y DHCP, asegurando su correcta integración con la segmentación de VLANs establecida en la infraestructura.
- Aplicar parches y actualizaciones de seguridad mensualmente, siguiendo las políticas de protección del CPD.
- Realizar auditorías de cuentas de usuario cada tres meses para verificar accesos y permisos según el modelo de seguridad definido
- **Servidor de Aplicaciones y Bases de Datos**
- Monitorizar el rendimiento de SQL Server para garantizar el correcto funcionamiento de la aplicación.
- Optimizar consultas y mantener índices actualizados para mejorar tiempos de respuesta.
- **Servidor de Respaldo** 
- Verificar la integridad de las copias de seguridad almacenadas.
- Configurar sincronización automática con el NAS y AWS S3 para asegurar la redundancia geográfica. 
- Realizar pruebas de restauración trimestrales para validar la efectividad del plan de recuperación ante desastres.
- Situado en diferente lugar 
2. Gestión<a name="_page18_x69.00_y170.00"></a> de Red
- **VLAN’s** 
- Revisar configuraciones de VLANs (10, 20 y 30) para mantener la segmentación definida en la documentación técnica.
- Asegurar el aislamiento de tráfico entre VLANs conforme a las políticas de seguridad establecidas.
- **Switches y Router** 
- Actualizar el firmware de switches y router para garantizar estabilidad y seguridad. 
- Monitorizar el tráfico de red para identificar posibles congestiones o amenazas. 
- **Firewall** 
- Mantener las reglas de firewall actualizadas conforme a las estrategias de protección contra ciberataques.
- Configurar alertas automáticas para actividades sospechosas mediante herramientas de detección y prevención de intrusos.
3. Seguridad<a name="_page18_x69.00_y580.00"></a> del CPD
- **Control de Acceso Físico** 
- Solo personal autorizado puede acceder al CPD.
- Implementación de controles biométricos o tarjetas de acceso para restringir la entrada. 
- Registro de accesos con auditorías periódicas para detectar anomalías.
- **Protección Perimetral** 
- Revisar configuraciones de cortafuegos para proteger el acceso al CPD.
- Realizar pruebas de penetración semestrales para detectar posibles vulnerabilidades. 
- **Seguridad de la Infraestructura** 
- Monitorizar en tiempo real la temperatura y humedad del CPD con sensores especializados.
- Implementar sistemas de refrigeración redundantes para evitar sobrecalentamientos.
- Garantizar que la humedad relativa se mantenga dentro de los rangos recomendados para equipos electrónicos (40%-60%). 
- Verificar la funcionalidad de los SAI y generadores eléctricos para asegurar el suministro de energía ininterrumpida.
- **Copias de Seguridad** 
- Confirmar la ejecución correcta de copias completas e incrementales conforme al plan de respaldo documentado.
- Almacenar copias redundantes en local y en la nube mediante AWS S3 y NAS 
4. Procedimientos<a name="_page19_x69.00_y359.00"></a> de Recuperación
- **Restauración de Servidores** 
- Identificar la causa del fallo mediante el análisis de registros del sistema.
- Restaurar la infraestructura básica desde la copia completa almacenada en el NAS. 
- Aplicar copias incrementales y verificar la integridad de los datos restaurados. 
- **Plan de Recuperación Ante Desastres**
- Seguir el procedimiento documentado para la activación del plan de contingencia en caso de fallo crítico.
- Contactar con el personal clave según el protocolo establecido y escalar incidentes según su nivel de gravedad.
5. Documentación<a name="_page19_x69.00_y650.00"></a> y Auditorías
- Mantener registros detallados de todas las actividades del CPD para auditorías y revisiones periódicas. 
- Realizar auditorías de seguridad y rendimiento cada seis meses para evaluar el cumplimiento de las políticas establecidas.
- Actualizar la documentación técnica tras cualquier cambio significativo en la infraestructura del CPD. 
Página 21 de 21  Daniel Dumea, Jordi Escriva, Ivan Catala


1. **Instalación<a name="_page2_x69.00_y73.00"></a> del Servidor** 

Primero que todo, empezamos escogiendo un ordenador de todos los que habían para empezar con el proceso del servidor. Una vez escogido vimos que tenía un disco duro de 500GB lo que era bastante capacidad, pero decidimos añadir otro disco después de la instalación del sistema para hacer un RAID. 

La instalación que hicimos fue un Windows Server 2022 que la instalamos con un ventoy en el que teníamos la ISO, en la instalación no tuvimos ningún problema y logramos instalar el servidor rápido y sin fallos.

Una vez ya estamos dentro del servidor, activamos el Active Directory que era algo que nos podía ayudar mucho en nuestro proyecto ya que ayuda a almacenar información acerca de los objetos de una red y facilita su búsqueda y uso por parte de los usuarios y administradores. 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.002.jpeg)

**FIGURA-1:** Captura del Administrador del Servidor.** 

A la hora de añadir un nuevo disco tuvimos muchos problemas con los discos que le añadíamos porque muchos nos daban fallos y perdimos mucho tiempo comprobando discos, los que detectaba el sistema no se podían usar entonces pensamos que podía ser un problema del cable SATA así que lo cambiamos y ya lo podíamos usar. Lo que el nuevo disco que le pusimos tiene una capacidad de 250GB y no es de la misma capacidad al que ya tenemos puesto.

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.003.jpeg)

**FIGURA-2:** Captura de los dos discos en marcha.

2. **Instalación<a name="_page4_x69.00_y73.00"></a> de RAID 5 por Software**  

Después de tener un Windows Server 22 instalado hemos tenido que investigar como poder hacer un raid 5 por software porque hemos tenido algún problema que otro por que la tecnología de Raid 5 necesita mínimo 3 discos para poder crearse. Entonces hicimos particiones en un segundo disco físico que metimos, pero no pedimos crear el raid porque por particiones simple no nos dejaba. Luego de unos días estar investigando y preguntado también a compañeros lo podíamos hacer y lo vamos a explicar a continuación.  

**Paso 1:**  

Crear una partición en el disco 0 que es donde está instalado el sistema Operativo y dejara lo inicializado.  

A continuación, creamos 3 discos duros VHD para poder crear el raid 5.  **Paso 2:**  

Luego de tener los 3 discos VHD creados nos vamos al Administrador del Servidor, en la parte izquierda nos situamos donde pone Servicios de archivos y de almacenamiento. Ahí dentro entra a los Servidores donde vamos a crear los discos virtuales para poder crear el raid 5.  

Donde pone Discos Virtuales nos situamos y en la parte de tareas le decimos nuevo disco virtual y a continuación vemos como creamos el disco virtual. 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%204.png)

**FIGURA-3:.** Le ponemos nombre al disco virtual 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%205.png)

**FIGURA-4:.** Seleccionamos la distribución de almacenamiento que va a tener el disco virtual 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%206.png)

**FIGURA-5:** Le indicamos el tipo de aprovisionamiento que será fijo 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%207.png)

**FIGURA-5:** Le indicamos el tipo de aprovisionamiento que será fijo 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%208.png)

**FIGURA-6:** Le** especificamos el tamaño del disco duro. 

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%209.png)

**FIGURA-7:** Nos indica que un pequeño resumen de lo que hemos aplicado en cada disco virtual.** 

Luego de repetir esto 3 veces para crear los 3 disco virtuales nos vamos al administrador de discos.  

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%2010.png)

**FIGURA-8:** Podemos ver que ya tenemos los 3 discos creados por software virtuales para raid 5.  

![](https://github.com/Danii-06/Projecte-FHW/blob/main/IMAGEN%2011.png)

**FIGURA-9:** En el administrador del servidor nos vamos a los grupos de almacenamiento para poder añadir el disco físico que tenemos a los discos virtuales que hemos creado.**  

3. **Creación<a name="_page10_x69.00_y73.00"></a> de los usuarios para los trabajadores.**

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.011.jpeg)

**FIGURA-10:** Para crear usuarios en Windows Server 2022, hemos seguido estos pasos:

1. **Abrir la Administración de Equipos** 
1. Accedemos al menú Inicio y escribimos "Administración de equipos".
1. Dentro de la consola, navegamos a **Herramientas del sistema > Usuarios y grupos locales > Usuarios**. 
2. **Crear un nuevo usuario** 
1. Hacemos clic derecho en la carpeta "Usuarios" y seleccionamos **"Usuario nuevo..."**. 
1. Se abre la ventana para agregar un nuevo usuario.
3. **Configurar los datos del usuario** 

a.  En la ventana emergente, ingresamos:

1. **Nombre de usuario**: "El nombre que deseamos". 
1. **Descripción**: "la descripción que deseamos por ejemplo administrador ". 
1. **Contraseña**: Se establece y se confirma en los campos correspondientes. 
1. Se marca la opción **"El usuario debe cambiar la contraseña en el siguiente inicio de sesión"** para obligar al usuario a cambiar su clave en su primer acceso. 
4. **Finalizar la creación** 

a.  Hacemos clic en el botón **"Crear"**, y el usuario queda registrado en el 

sistema. 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.012.png)

**FIGURA-11:** Creamos el usuario Ivan.** 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.013.png)

**FIGURA-12:** Creamos el usuario Jordi.** 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.014.png)

**FIGURA-13:** Creamos el usuario Dani.** 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.015.jpeg)

**FIGURA-14:** En usuarios y Grupos locales en la carpeta de usuarios aparecerán todos los usuarios que tiene el equipo. 

4. **Instalación<a name="_page14_x69.00_y73.00"></a> de Aomei Backupper Server y una copia del disco del sistema operativo.**  

   Instalaremos AOMEI Backupper para hacer copias de seguridad por si tenemos algún problema. 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.016.jpeg)

**FIGURA-15** Primero instalaremos el AOMEI BACKUPER para hacer copias de seguridad

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.017.jpeg)

**FIGURA-16** Le daremos a nueva copia de seguridad para iniciar el proceso

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.018.jpeg)

**FIGURA-17** Le daremos a copia de seguridad del disco  

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.019.jpeg)

**FIGURA-18** Elegiremos el disco duro que queremos hacer la copia de seguridad** 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.020.jpeg)

**FIGURA-19** Luego diremos en que disco duro queremos que se haga

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.021.jpeg)

**FIGURA-20** Aquí veremos el historial de las copias de seguridad que hemos hecho. 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.022.png)

**FIGURA-21** Y luego la tendremos en el equipo exportado para poder utilizar la copia cuando lo necesitemos.

5. **Restauración<a name="_page18_x69.00_y73.00"></a> de la copia de seguridad del sistema** 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.023.jpeg)

**FIGURA-22** Seleccionamos restaurar y seleccionamos los archivos que deseemos 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.024.jpeg)

**FIGURA-23** Elegimos la copia de seguridad que deseemos restaurar

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.025.jpeg)

**FIGURA-24** Le damos a restaurar para recuperar la copia anterior.

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.026.jpeg)

**FIGURA-25** Vemos el resumen de la restauración que vamos a realizar. 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.027.png)

**FIGURA-26** Luego lo reiniciaremos con AOMEI Backupper y luego cuando reinicies tendrás los pasos para recuperar la copia de seguridad.** 

6. **Ubuntu<a name="_page21_x69.00_y73.00"></a> Server**
- Nombre del servidor Ubuntu --> proyecto 
- Contra --> grupo4 

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.028.jpeg)

**FIGURA-27**  Hemos instalado una máquina virtual de Ubuntu Server y le hemos dado nombre y contraseña luego lo conectaremos a nuestro servidor para que puedan comunicarse.  

7. **Romper<a name="_page21_x69.00_y406.00"></a> el raid y recuperarlo** 

Lo primero que hacemos es hacer como que nos falla un disco del raid 5 para poder recuperarlo es decir vamos a simular como que en la empresa el raid 5 está funcionando correctamente y de repente un disco del raid 5 falla entonces hay que añadir uno para poder recuperarlo. Vamos a hacer un paso a paso de como lo hemos realizado.  

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.029.png)

**FIGURA 28 –** Vemos como el disco que antes estaba en el raid ha fallado.

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.030.png)**FIGURA 29 –** Hemos añadido un VHD para poder recuperar el raid porque hay un disco que falla.  

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.031.png)

**FIGURA 30 –** Hemos añadido el disco VHD nuevo para poder volver a crear el raid por que el disco 4 es el que daba fallo entonces quitamos el 4 y añadimos el disco 7 para poder volver a hacer el raid 5.  

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.032.png)

**FIGURA 31 –** En esta imagen podemos ver la administración de discos virtuales con varios discos que están configurados en un grupo RAID 5, todos con aprovisamiento fijo y la distribución simple.  

![](Aspose.Words.0a348393-76d0-498f-9eed-8c1616bf2724.033.jpeg)

**FIGURA 31 –** Aquí en esta imagen podemos ver que el Disco 2/3/7 están montados en RAID 5. El Ventoy es un USB que pusimos para poder guardar las capturas para luego para poder hacer la documentación del proyecto.
Pagina 24 de 24  Daniel Dumea, Ivan Catalá, Jordi Escriva


