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

En breve ire subiendo toda la información referente a materiales utilizados, esquema electrico y soft.
He utilizado la potencia de los 2 nucleos del ESP32 para optimizar el funcionamiento.

Vista de la página web servida desde el ESP32:
![image](https://user-images.githubusercontent.com/48222471/180615329-6ca98c3f-5c46-4797-aa4f-1cd8161137aa.png)



