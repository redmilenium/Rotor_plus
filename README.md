# ROTOR_PLUS
Rotor con azimuth y elevation basado en ESP32 

Este proyecto esta diseñado para la recepción de nanosatelites del proyecto tinygs.com  

Este proyecto es una mejora del anterior rotor que solo contaba con giro de azimuth.

Igualmente puede utilizarse de forma manual, ajustando el azimuth y la elevation a los valores que deseemos, y tambien puede trabajar de forma automatica poniendose a las ordenes de la tinyGS, que le envia el satelite a seguir, y el rotor busca en Celestrak los TLE´s actualizados para obtener la posición del satelite en tiempo real, con la ayuda de la librería Sgp4:  hopperpop/Sgp4@^1.0.3

Mi agradecimiento a los siguientes magos de la programación:

lib_deps = 

	esphome/AsyncTCP-esphome@^1.2.2
	
	ottowinter/ESPAsyncWebServer-esphome@^2.1.0
	
	arduino-libraries/NTPClient@^3.2.1
	
	paulstoffregen/Time@^1.6.1
	
	jchristensen/Timezone@^1.2.4
	
	hopperpop/Sgp4@^1.0.3
	
	waspinator/AccelStepper@^1.61
	
	me-no-dev/ESP Async WebServer@^1.2.3.
	
  
  Asi como a:
  
              https://github.com/G4lile0/tinyGS  
  

Diseñado especificamente para capturar telemetría de la familia de satelites FossaSat: la antena que he fabricado esta optimizada para la frecuencia de estos satelites.

![image](https://user-images.githubusercontent.com/48222471/180614173-b6e6713a-deb8-4f4f-9173-88964b037b58.png)

Los resultados han mejorado notablemente con respecto al rotor anterior (solo azimuth).

Vista del hardware:

![image](https://user-images.githubusercontent.com/48222471/180614595-1c1f45ef-7f25-4ad3-9da9-7140ff463c83.png)

Vista una vez instalado y con la Tinygs en su interior:  LNA + TTGO

![image](https://user-images.githubusercontent.com/48222471/180614744-c5e2242c-3ab8-4e87-be8f-4dc12a05e20e.png)

En la versión en funcionamiento he protegido los componentes interiores de la perjudicial luz solar.

He utilizado la potencia de los 2 nucleos del ESP32 para optimizar el funcionamiento.

Vista de la página web servida desde el ESP32:
![image](https://user-images.githubusercontent.com/48222471/180615329-6ca98c3f-5c46-4797-aa4f-1cd8161137aa.png)

Esquema:
![image](https://user-images.githubusercontent.com/48222471/180657120-4b9f4182-c0c6-4d5d-bc0d-1f658a040fc2.png)

Vista del detector de cero de elevation:
![image](https://user-images.githubusercontent.com/48222471/180657142-6ab82634-b866-4d89-85f9-b60fd9836910.png)

CONSTRUCCION

La columna vertebral del sistema la forma una chapa de 4 mm. de espesor y de 210 mm. de ancho x 335 mm de alto, 2 SOPORTES PUENTE UCP 207 ISB y un mastil de los que se utilizan para instalar antenas de TV de 35 mm. de diametro.

![image](https://user-images.githubusercontent.com/48222471/184387880-ce34af6a-313a-44b5-a5bb-c44805ffdab8.png)

Dado que el mastil es de 35 mm. de diametro y el diametro interior de los soportes puente, tambien es de 35 mm. es necesario hacer un corte longitudinal con una dremel en los primeros 150 mm. del mastil. De esta manera y con la ayuda del martillo de Thor, es posible meter el mastil en su sitio.
Entre los 2 soportes puente, hay que meter el sistema de imanes que activará el detector hall del azimuth.

![image](https://user-images.githubusercontent.com/48222471/184388746-12f8c61a-37ae-46ea-bbf2-d1885753e1c6.png)

Como en un principio, estaba utilizando detector hall bipolares (cuando se les expone a un polo Sur se activan y hasta que no se le expone a un polo Norte no se desactivan, el el sistema de imanes van 3 filas de imanes:  norte - sur  - norte (cuando llega el norte se desactiva y cuando llega el sur se activa):

![image](https://user-images.githubusercontent.com/48222471/184389039-ed0e3010-747f-4081-a10d-db2c2ae1073b.png)


En breve ire subiendo mas información referente a materiales utilizados, soft.



