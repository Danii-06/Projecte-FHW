# G4 - CPD para una red social orientada a productos de supermercado.

### Integrantes del grupo:
- Daniel Pablo Dumea
- Jordi Escriva Montaner
- Ivan Catala Prats
  1. [Introducción _________________________________________________________________ 3 ](#_page2_x69.00_y148.00)
1. [Objetivos del Proyecto _______________________________________________________ 3 ](#_page2_x69.00_y348.00)
1. [Requisitos Funcionales ______________________________________________________ 4 ](#_page3_x69.00_y542.00)

[1.4 Requisitos No Funcionales ___________________________________________________ 5 ](#_page4_x69.00_y365.00)

2. [Análisis de requisitos _________________________________________________________ 6 ](#_page5_x69.00_y171.00)
1. [Requisitos de Hardware ______________________________________________________ 6 ](#_page5_x69.00_y339.00)
1. [Requisitos de Software ______________________________________________________ 6 ](#_page5_x69.00_y666.00)
1. [Requisitos de Red ___________________________________________________________](#_page6_x69.00_y242.00) [7 ](#_page6_x69.00_y242.00)
1. [Capacidades Técnicas Necesarias ____________________________________________ 7 ](#_page6_x69.00_y575.00)
1. [Ejemplo de un posible escenario para el uso de la red social ____________________ 8 ](#_page7_x69.00_y115.00)

[3 Cronograma del proyecto ______________________________________________________ 8 ](#_page7_x69.00_y436.00)[4. Asignación de roles y responsabilidades ________________________________________ 9 ](#_page8_x69.00_y142.00)

1. [Los Roles del equipo _________________________________________________________ 9 ](#_page8_x69.00_y630.00)
1. [Dinámica entre roles _______________________________________________________ 10 ](#_page9_x69.00_y665.00)
1. [El Trabajo se basa en 7 actividades: __________________________________________ 11 ](#_page10_x69.00_y463.00)[5 identificación de recursos  necesarios. _________________________________________ 12 ](#_page11_x69.00_y601.00)
1. [Recursos Humanos ________________________________________________________ 13 ](#_page12_x69.00_y73.00)
1. [Costes de Hardware ________________________________________________________ 13 ](#_page12_x69.00_y547.00)
1. [Costes de Software _________________________________________________________ 14 ](#_page13_x69.00_y101.00)
1. [Costes de Red _____________________________________________________________ 14 ](#_page13_x69.00_y575.00)
1. [Costes de Infraestructura y Mantenimiento ___________________________________ 15 ](#_page14_x69.00_y333.00)
1. [Estimación Financiera ______________________________________________________ 15 ](#_page14_x69.00_y711.00)

[6. Evaluación de riesgos y planificación de contingencias _________________________ 16 ](#_page15_x69.00_y167.00)

1. [Identificación de riesgos ____________________________________________________ 16 ](#_page15_x69.00_y273.00)
1. [Evaluación de los riesgos ___________________________________________________ 16 ](#_page15_x69.00_y548.00)
1. [Plan de contingencias ______________________________________________________ 17 ](#_page16_x69.00_y73.00)
1. [Protocolos de actuación ____________________________________________________ 17 ](#_page16_x69.00_y538.00)
1. **Introducción<a name="_page2_x69.00_y148.00"></a>** 

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

![](Aspose.Words.d581e6ea-9d1f-465e-ab05-9ca4a9130a14.002.jpeg)

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
