tags:: #ciberseguridad #pentesting #hacking #conceptos

- ### **Spoofing (Suplantación):**
  collapsed:: true
  Spoofing es un ataque en el que un actor malintencionado se hace pasar por una entidad confiable para engañar a los usuarios o sistemas y obtener acceso no autorizado a datos, sistemas o redes.
	- **Tipos comunes de spoofing:**
	  
	  **IP Spoofing:** El atacante falsifica una dirección IP para hacerse pasar por otro dispositivo en la red.
	  **Email Spoofing:** Se falsifica la dirección de correo del remitente para que parezca provenir de una fuente confiable.
	  **DNS Spoofing:** El atacante manipula las respuestas del sistema de nombres de dominio para redirigir a los usuarios a sitios maliciosos.
	  **Website Spoofing:** Se crea un sitio web falso que imita a uno legítimo para robar credenciales o datos personales.
	  
	  **Impacto:**
	  Compromiso de datos sensibles, distribución de malware o phishing.
- ### **Tampering (Manipulación):**
  collapsed:: true
  Tampering es la alteración no autorizada de datos, hardware, software o comunicaciones para modificar su comportamiento o contenido con fines maliciosos.
	- **Ejemplos de tampering:**
	  
	  **Intercepción de datos:** Durante una comunicación, un atacante modifica los datos en tránsito, como mensajes o transacciones financieras.
	  **Alteración de software:** Se inyecta código malicioso en una aplicación para cambiar su funcionamiento, como en ataques de "backdoor".
	  **Hardware tampering:** Manipulación física de dispositivos para insertar componentes que permitan el espionaje o robo de datos.
	  
	  **Impacto:**
	  Pérdida de integridad de los datos, alteración de funciones críticas o sabotaje de sistemas.
- ### **URL Forwarding (Redirección de URL):**
  collapsed:: true
  Este ataque ocurre cuando se manipulan los enlaces de redirección (forwarding) en una página web o correo electrónico para llevar a los usuarios a sitios maliciosos o fraudulentos.
	- **Tipos comunes:**
	  
	  **Open Redirects:** Una vulnerabilidad en aplicaciones web que permite al atacante usar una URL legítima para redirigir a un dominio malicioso.
	  **Phishing Links:** Los atacantes crean enlaces aparentemente legítimos que conducen a sitios diseñados para robar credenciales.
	  **SEO Poisoning:** Uso de técnicas de redirección en motores de búsqueda para posicionar sitios maliciosos como confiables.
	  
	  **Impacto:**
	  Robo de información personal, distribución de malware o ataques de phishing.
- ### **Ciberinteligencia**
	- Enfoque: **Recolección, análisis e interpretación de información digital** para anticipar, detectar y responder a amenazas cibernéticas.
	- **Características principales**:**
	  *Análisis predictivo*:
	  Anticipa amenazas antes de que se materialicen.
	  Usa datos sobre patrones de ataque, actividad de actores maliciosos y tendencias.
	  *Recolección de datos*:
	  Fuentes principales:
	  Open Source Intelligence ((6740fa87-4b13-4fff-a747-87afcc89d8be)): Información pública.
	  Dark Web Intelligence: Datos de foros y mercados en la web oscura.
	  Threat Intelligence Feeds: Bases de datos sobre amenazas.
		- **Objetivo**:
		  Identificar:
		  **Quién** está detrás de las amenazas.
		  **Qué** herramientas usan.
		  **Cómo** operan.
		  **Por qué** atacan.
		- **Uso estratégico**:
		  Toma de decisiones informadas sobre medidas preventivas.
		  Priorización de recursos hacia amenazas críticas.
		  **Tipos de ciberinteligencia**:
		  **Táctica**: Información operativa para equipos de respuesta.
		  **Técnica**: Datos sobre herramientas y métodos de ataque.
		  **Estratégica**: Evaluaciones de alto nivel para líderes.
		- Analizar: el marco de inteligencia colectiva admite muchas fuentes diferentes
		  de datos del mismo tipo, como por ejemplo, respaldarse de bases de datos
		  de sitios reportados como maliciosos. Entonces, podemos, a través de esta
		  información, generar un conjunto de datos “similares” a los cuales podemos
		  asignar atributos como "fuente" y "confianza", “peligroso”, “malicioso”,
		  según sea el caso.
		- Normalizar: el grupo de datos obtenidos por inteligencia de amenazas a
		  menudo tiene diferencias sutiles entre sí. La clasificación internacional de
		  funcionamiento CIF (Collective Intelligence Framework) regula este grupo de
		  información, lo que le brinda una experiencia predecible al aprovechar la
		  inteligencia de amenazas en otras aplicaciones o procesos.
		  Post procesado: la CIF tiene muchos procesos posteriores que van
		  adquiriendo inteligencia adicional de amenazas. Un buen ejemplo sería que
		  un dominio y una dirección IP se pueden transferir de una URL digerida por
		  un CIF.
		- Almacenamiento: en la clasificación internacional de funcionamiento se
		  usan JSON y ElasticSearch, porque son almacenes de datos para miles de
		  millones de registros de inteligencia de amenazas.
		- Consulta: en la CIF es posible consultar a través de la web, un cliente CLI
		  (Comand Line Interface), aplicaciones que no son gráficas, pueden consultar
		  mediante esta línea de comando o derechamente mediante la API (interfaz
		  de programación de aplicaciones) del servicio.
		- Compartir: la API de la clasificación internacional de funcionamiento permite
		  el registro de usuarios, grupos y claves. Cada uno de estos registros de
		  inteligencia de amenazas puede ser etiquetado para ser compartido con un
		  grupo específico de usuarios. Así, esta información puede ser transmitida y
		  retroalimentada entre distintas organizaciones.
		- Producción: la CIF permite la creación de nuevos grupos de datos a partir
		  de la inteligencia de amenazas compilada. Estos conjuntos de datos se
		  clasifican por tipo y confianza. La clasificación internacional de
		  funcionamiento también permite el registro de listas blancas durante el
		  proceso de generación de retroalimentaciones.
	- ### Funcion de la ciberinteligencia
		- Identificar: aquí debemos debe ser capaces de hacer un análisis preventivo
		  que permita comprender cuáles son los riesgos latentes para los activos y
		  recursos más importantes de la empresa.
		- Proteger: esto implica desarrollar controles de seguridad estandarizados
		  que permitan proteger la infraestructura crítica de la organización.
		- Detectar: es importante implementar alertas de detección temprana o
		  predicción ataques informáticos; estas deben ser apoyadas por una
		  supervisión continua de sus políticas de seguridad.
		- Responder: la capacidad de entregar respuestas oportunas y adecuadas a
		  cada amenaza que se presenta; estas deben basarse en análisis preventivo
		  estandarizado y una planificación eficaz de los posibles riesgos.
		- Recuperar: es primordial tener planes de recuperación que garanticen la
		  continuidad funcionamiento del negocio tras un ataque. Asimismo, las
		  actividades de una empresa no se verán paralizadas ni afectadas
	- ![image.png](../assets/image_1732848884203_0.png)
		-
- ### **Collective Intelligence Framework**
  collapsed:: true
	- El **Collective Intelligence Framework (CIF)**, es un modelo o conjunto de prácticas diseñado para recopilar, procesar y compartir inteligencia de amenazas de manera colaborativa entre organizaciones, comunidades o equipos de seguridad. Su principal objetivo es fortalecer la capacidad colectiva para detectar, responder y prevenir amenazas cibernéticas mediante el intercambio de datos relevantes y procesables.
	- ### Principales características del CIF:
	- **Enfoque colaborativo**
	  Promueve la colaboración entre diferentes actores (empresas, gobiernos, individuos, comunidades de investigación) para compartir información sobre amenazas.
	- **Automatización**
	  Utiliza herramientas y tecnologías para automatizar la recopilación, análisis y distribución de inteligencia de amenazas, reduciendo el tiempo y el esfuerzo manual.
	- **Interoperabilidad**
	  Facilita la integración de datos provenientes de diferentes fuentes (logs, informes de incidentes, datos de OSINT, etc.) y los hace compatibles con sistemas y protocolos comunes.
	- **Estandarización**
	  Emplea estándares de intercambio de datos como **STIX** (Structured Threat Information Expression) o **TAXII** (Trusted Automated Exchange of Indicator Information) para asegurar que la información se comparta de manera coherente y segura.
	- **Procesamiento de datos**
	  Incluye capacidades para:
		- Recopilar indicadores de compromiso (IoCs).
		- Correlacionar eventos y patrones de amenazas.
		- Generar inteligencia procesable basada en análisis.
	- ### ¿Dónde se usa?
	- **Empresas privadas**: Para mejorar su ciberseguridad compartiendo inteligencia con otras organizaciones del mismo sector.
	- **Gobiernos**: En agencias de ciberseguridad nacionales o internacionales para coordinar respuestas ante ataques masivos.
	- **Comunidades de investigación**: Como parte de redes globales que analizan amenazas emergentes y comparten resultados.
	- ### Beneficios del CIF
	- **Mitigación rápida de amenazas**: La inteligencia compartida permite tomar medidas preventivas antes de que las amenazas se materialicen.
	- **Optimización de recursos**: Al compartir inteligencia, las organizaciones reducen el costo de investigar y analizar amenazas por separado.
	- **Visibilidad ampliada**: Una red colaborativa tiene más alcance y puede identificar patrones que serían invisibles a una sola entidad.
- ### **Ciberseguridad**
  collapsed:: true
	- Enfoque: **Protección de sistemas, redes y datos** frente a ataques y accesos no autorizados.
	- **Características principales**:
	  *Enfoque preventivo y reactivo*:
	  Implementación de herramientas para proteger infraestructuras digitales.
	  Respuesta a incidentes para minimizar daños.
	  *Componentes clave*:
	  **Confidencialidad**: Acceso solo para usuarios autorizados.
	  **Integridad**: Protección contra modificaciones no autorizadas.
	  **Disponibilidad**: Asegurar acceso a datos y servicios.*
	  Técnicas y herramientas*:
	  Firewalls, sistemas de detección de intrusos (IDS), antivirus.
	  Pruebas de penetración y auditorías de seguridad.
	  Protocolos de recuperación y continuidad.
	  *Áreas de aplicación*:
	  Protección de infraestructuras críticas (redes eléctricas, sistemas bancarios).
	  Seguridad de dispositivos personales y corporativos.
	  *Responsabilidad*:
	  Proceso continuo y actualizado para mitigar vulnerabilidades.
- ### **Diferencias entre Ciberinteligencia y Ciberseguridad**
  collapsed:: true
	- *Propósito*:
	  Ciberinteligencia: Detectar y anticipar amenazas mediante análisis.
	  Ciberseguridad: Proteger sistemas y datos contra ataques.
	  *Enfoque*:
	  Ciberinteligencia: Estratégico y predictivo.
	  Ciberseguridad: Técnico y operativo.
	  *Métodos*:
	  Ciberinteligencia: Monitoreo de amenazas y análisis de información.
	  Ciberseguridad: Implementación de herramientas y políticas de protección.
	  *Alcance*:
	  Ciberinteligencia: Identificación de actores, patrones y tendencias.
	  Ciberseguridad: Defensa de infraestructura tecnológica.
	  *Temporalidad*:
	  Ciberinteligencia: Anticipación a largo plazo.
	  Ciberseguridad: Prevención y respuesta inmediata.
	  *Herramientas usadas*:
	  Ciberinteligencia: OSINT, feeds de inteligencia, análisis de amenazas.
	  Ciberseguridad: Firewalls, IDS, cifrado, protocolos de seguridad.
- ### **OSINT (Open Source Intelligence)**
  id:: 6740fa87-4b13-4fff-a747-87afcc89d8be
  collapsed:: true
	- **Definición**:
	  Recolección y análisis de información pública y legalmente accesible.
	- **Características**:
	  Fuentes abiertas y legales.
	  Identificación de patrones, riesgos y amenazas.
	- **Fuentes principales**:
	  *Internet*: Sitios web, blogs, foros.
	  *Medios de comunicación*: Noticias, podcasts.
	  *Redes sociales*: Twitter, Facebook, LinkedIn.
	  *Datos gubernamentales*: Registros públicos, bases de datos.
	  *Imágenes*: Fotografías satelitales y documentos gráficos.
- ### **Variantes de OSINT**
  collapsed:: true
	- **GEOINT (Geospatial Intelligence)**:
		- **Definición**: Análisis de información geoespacial (mapas, imágenes satelitales).
		- **Aplicaciones**:
			- Detección de movimientos militares.
			- Monitoreo de desastres naturales.
			- Planificación urbana.
	- **SOCMINT (Social Media Intelligence)**:
		- **Definición**: Análisis de datos obtenidos de redes sociales.
		- **Ejemplos**:
			- Monitoreo de tendencias y hashtags.
			- Geolocalización de publicaciones.
		- **Herramientas**:
			- Análisis de hashtags, sentiment analysis.
	- **HUMINT (Human Intelligence)**:
		- **Definición**: Inteligencia obtenida mediante interacción humana directa.
		- **Relación con OSINT**: Verificación de información obtenida.
	- **SIGINT (Signals Intelligence)**:
		- **Definición**: Análisis de señales de comunicación o electrónicos.
		- **Relación con OSINT**: Complementa datos de fuentes abiertas.
	- **TECHINT (Technical Intelligence)**:
		- **Definición**: Inteligencia sobre tecnologías específicas.
		- **Relación con OSINT**: Publicaciones científicas, patentes, análisis técnicos.
	- **FININT (Financial Intelligence)**:
		- **Definición**: Inteligencia obtenida del análisis de transacciones financieras.
		- **Ejemplos**:
			- Rastreo de fondos ilícitos.
			- Actividades económicas de grupos criminales.
	- **CYBINT (Cyber Intelligence)**:
		- **Definición**: Inteligencia específica del entorno digital.
		- **Ejemplos**:
			- Análisis de patrones de ataque.
			- Identificación de actores maliciosos en la Dark Web.
- ### **Payload**
  collapsed:: true
	- ### Conceptos Clave de un Payload
	- **Entrega**: El payload es la parte del malware que se entrega al sistema objetivo a través de diversos métodos, como phishing, exploits, descargas maliciosas, o mediante el uso de otro malware como un troyano.
	- **Ejecuta una acción específica**: Una vez entregado, el payload se activa para realizar una acción maliciosa. Esta acción puede variar ampliamente dependiendo del objetivo del atacante.
	- **Tipos de acciones maliciosas**:
	  * **Ransomware**: Encripta los archivos del usuario y solicita un rescate para descifrarlos.
	  * **Spyware**: Recoge información del sistema objetivo y la envía al atacante.
	  * **Rootkits**: Otorgan acceso privilegiado continuo a un sistema comprometido.
	  * **Botnets**: Transforman el sistema en parte de una red de bots para realizar ataques coordinados, como DDoS.
	  * **Keyloggers**: Capturan las pulsaciones del teclado para robar credenciales y otra información sensible.
	- ### Ejemplo Práctico
	  
	  Supongamos que recibes un correo electrónico con un archivo adjunto aparentemente inofensivo (como un documento de Word). Al abrirlo, el documento contiene un script malicioso que se ejecuta automáticamente y descarga el payload desde un servidor remoto. Este payload puede ser un ransomware que encripta tus archivos y muestra una nota de rescate pidiendo dinero para descifrarlos.
	- ### Relación con las Vulnerabilidades
	  
	  El éxito de un payload a menudo depende de la explotación de vulnerabilidades en el sistema objetivo. Por ejemplo, puede aprovechar una vulnerabilidad en el software del sistema operativo o en una aplicación para ejecutarse con privilegios elevados y causar más daño.
	- ### Prevención y Mitigación
	- **Actualización y parcheo**: Mantener los sistemas y aplicaciones actualizados para evitar que los atacantes exploten vulnerabilidades conocidas.
	- **Antivirus y antimalware**: Utilizar software de seguridad que pueda detectar y neutralizar payloads maliciosos.
	- **Concienciación y formación**: Educar a los usuarios sobre los riesgos de abrir archivos adjuntos desconocidos y hacer clic en enlaces sospechosos.
	- **Firewalls y sistemas de detección de intrusos**: Implementar medidas de seguridad en la red para detectar y bloquear actividades sospechosas.
- ### **Internet Blackout**
  collapsed:: true
	- es una interrupción intencional de todos o parte de los servicios de internet en una región o país. Los gobiernos pueden implementar estos apagones por diversas razones, como el control social, la seguridad nacional, o para sofocar protestas y disturbios.
	- ### Técnicas de censura y control de internet
	- **Apagón total de Internet**: Los gobiernos ordenan a los proveedores de servicios de internet (ISP) que corten completamente el acceso a la red. Esto puede ser a nivel regional o nacional.
	- **Bloqueo de sitios web**: Se restringe el acceso a sitios web específicos mediante el bloqueo de direcciones IP o DNS. Esto impide que los usuarios accedan a plataformas de redes sociales, medios de comunicación independientes y otros recursos en línea.
	- **Filtrado de contenido**: Utilizan software para filtrar contenido basado en palabras clave o temas específicos. Esto puede incluir el bloqueo de ciertos términos de búsqueda o la censura de publicaciones en redes sociales.
	- **Limitación de ancho de banda**: Reducen la velocidad de internet a un punto en que se vuelve casi inutilizable para ciertas actividades, como la transmisión de videos o la participación en videoconferencias.
	- **Cierre de redes sociales**: Bloquean el acceso a plataformas de redes sociales populares como Facebook, Twitter, y WhatsApp, para evitar la organización y difusión de información.
	- ### Técnicas de desinformación y propagación de miedo
	- **Creación de noticias falsas (fake news)**: Difunden información falsa o engañosa a través de medios controlados por el gobierno o a través de trolls y bots en redes sociales. Esto puede incluir teorías de conspiración, información errónea sobre eventos actuales, o ataques dirigidos a disidentes.
	- **Trolls y bots**: Utilizan cuentas falsas en redes sociales para amplificar mensajes pro-gobierno, desacreditar a opositores, y crear confusión entre la población.
	- **Propaganda estatal**: Los medios de comunicación controlados por el gobierno difunden narrativas favorables al régimen y desacreditan a los críticos. Esto incluye la exageración de amenazas externas o internas para justificar medidas represivas.
	- **Ataques cibernéticos**: Realizan ataques de denegación de servicio (DDoS) contra sitios web independientes y medios de comunicación, o hackean cuentas de redes sociales de activistas para sembrar desconfianza y miedo
	-
- ### **Pharming**
  collapsed:: true
	- es un tipo de ataque cibernético en el que el atacante redirige el tráfico de un sitio web legítimo hacia un sitio web falso, con el fin de robar información sensible, como contraseñas, números de tarjetas de crédito o credenciales de inicio de sesión.
	- ### Funcionamiento del Pharming
	  
	  En un ataque de pharming, el usuario intenta acceder a un sitio web legítimo, como su banco o una tienda en línea, pero termina siendo redirigido sin saberlo a un sitio web falso que parece idéntico al original. La idea es que el usuario no se dé cuenta de la diferencia y, al ingresar sus datos personales, los esté proporcionando al atacante.
	- ### Métodos Comunes de Pharming
	  
	  Existen dos métodos principales para llevar a cabo un ataque de pharming:
	- **Envenenamiento de caché DNS (DNS Poisoning o DNS Spoofing):**
		- Los atacantes manipulan el **servidor DNS** (Domain Name System), que es responsable de traducir nombres de dominio (como [www.banco.com](http://www.banco.com)) en direcciones IP (como 123.456.789.101). Al modificar los registros de DNS, el atacante puede hacer que una dirección legítima apunte a la dirección IP de un sitio web malicioso.
		- Como resultado, cuando el usuario intenta acceder a un sitio web legítimo, el servidor DNS infectado lo redirige al sitio falso.
	- **Modificación del archivo `hosts` en la computadora del usuario:**
		- Cada computadora tiene un archivo `hosts` que almacena direcciones IP asociadas con ciertos dominios. Los atacantes pueden modificar este archivo a través de malware, asignando nombres de dominio legítimos a direcciones IP falsas controladas por el atacante.
		- Esto engaña al navegador para que acceda al sitio web fraudulento en lugar del legítimo, sin que el usuario lo note.
	- ### Diferencias entre Pharming y Phishing
	  
	  Aunque el **pharming** y el **phishing** comparten el objetivo de robar información confidencial, funcionan de manera diferente:
	- **Phishing:** Involucra engañar a la víctima para que haga clic en un enlace malicioso o abra un correo fraudulento, llevándola voluntariamente a un sitio falso.
	- **Pharming:** Redirige automáticamente a la víctima, sin necesidad de que haga clic en un enlace engañoso, alterando la resolución DNS o el archivo `hosts` local.
	- ### Prevención de Pharming
	- **Uso de DNS seguros y confiables:** Servidores DNS bien configurados y protegidos pueden evitar ataques de envenenamiento DNS.
	- **Antivirus y software antimalware actualizados:** Estos pueden detectar y bloquear malware que intente modificar el archivo `hosts`.
	- **Uso de conexiones HTTPS:** Los sitios web que usan HTTPS proporcionan un certificado digital que permite verificar que el sitio es auténtico. Si un sitio legítimo no usa HTTPS, podría ser una señal de alerta.
	- **Monitoreo de certificados SSL:** Muchos sitios bancarios y de comercio electrónico utilizan certificados SSL (candado verde en la barra de direcciones) para proteger las conexiones.
- ### **Malicious media file explotation**
  collapsed:: true
	- The attack vector involving malware embedded in media files, including audio, video, or subtitle files, is commonly referred to as **"Media Parsing Exploits"** or **"Malicious Media File Exploitation"**.
	  
	  When specifically targeting subtitle files, it is often called a **"Subtitle File Exploit"** or **"Malicious Subtitles Attack"**.
	- ### Key Terms for the Attack Vector:
	- **Media Parsing Exploit**: Refers to the exploitation of vulnerabilities in the way media players parse and process media files.
	- **Trojanized Media Files**: Legitimate-looking media files that contain hidden malicious code.
	- **Malicious Subtitles Attack**: A specific subset of this vector targeting vulnerabilities in subtitle file processing.
	- ### Notable Examples:
	- **2017 Check Point Report**: This research highlighted how subtitle files could be used to deliver malware by exploiting vulnerabilities in popular media players like VLC, Kodi, and Popcorn Time.
	- **Steganography in Media Files**: Malware may also hide in the data streams of audio/video files, using techniques like steganography to evade detection.
	- ---
	- ### 1.  **Audio and Video Files**
		- **Exploiting File Format Vulnerabilities**: Audio and video files, like MP4, AVI, or MP3, follow specific encoding standards. Malicious actors can craft files that exploit vulnerabilities in the software (media players) that process these formats. When the file is played, the media player may execute the malware unintentionally.
		- **Embedding Code in Metadata**: Media files often contain metadata (like song titles, album names, etc.). Malware can be embedded in these fields, exploiting poorly implemented metadata parsers to trigger malicious activity.
		- **Trojanized Media**: The file itself may appear to be a regular media file, but it could include additional data or scripts designed to execute malware when opened.
	- ### 2.  **Subtitle Files**
		- **Code Execution in Subtitle Parsers**: Subtitle files (like `.srt`, `.sub`, or `.ssa`) are simple text files that provide time-synchronized captions for videos. Some media players have vulnerabilities in how they process subtitle files. A malicious subtitle file can exploit these flaws to execute arbitrary code.
		- **Priority Hijacking**: Attackers might manipulate subtitle repositories (like OpenSubtitles) to distribute malicious subtitles. When a media player downloads and plays the subtitle file, the malware can be executed without the user's knowledge.
	- ### 3.  **Attack Process**
		- The user downloads or streams an infected file, often from untrusted sources.
		- The media player or system processes the file.
		- Malicious code exploits vulnerabilities in the player or operating system.
		- The malware is executed, which can lead to various outcomes like data theft, system hijacking, or spreading the infection.
	- ### 4.  **Protection Tips**
		- **Update Media Players Regularly**: Ensure your media players are updated to patch known vulnerabilities.
		- **Download Files from Trusted Sources**: Avoid downloading media or subtitles from unverified websites.
		- **Use Antivirus Software**: A reliable antivirus program can detect and block malicious files.
		- **Check File Extensions**: Be cautious of unusual or double extensions (e.g., `video.mp4.exe`).
		  
		  This method of delivering malware highlights the importance of being cautious, even with seemingly harmless media files.