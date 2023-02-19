# rotor_plus
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
  
ANTENA

Es la parte mas importante de todo el sistema y la colocación de la misma.

Diseñada especificamente para capturar telemetría de la familia de satelites FossaSat.

En concreto está diseñada para una frecuencia central de 401/402 Mhz).

El sistema deber estar situado en una posición con visibilidad despejada 360 grados y con cobertura WIFI (necesaría para la TinyGS y para el rotor)

Dado que vamos a disponer de rotor con autoseguimiento de los satelites, utilizaremos una antena direccional. En nuestro caso una Yagi-Uda.

![image](https://user-images.githubusercontent.com/48222471/185983736-d0efbd2e-206d-40a5-934b-82519f61df22.png)

![image](https://user-images.githubusercontent.com/48222471/185977603-b3e7a397-408d-4257-92c9-11517492e8a6.png)

Material para la fabricación de la antena:

- 2 varillas aluminio de 4 mm. diametro y 1 m. de longitud

- 1 tubo pvc 16 mm. de diametro (se usa en instalaciones electricas)

- 3 piezas de impresión 3D

![image](https://user-images.githubusercontent.com/48222471/186407441-2afc2516-0fce-41e0-b2ff-257fc7725cd8.png)

Dado que no es posible soldar con estaño sobre aluminio, para poder conectar el cable coaxial que une la antena con la tinygs es necesario hacer las siguientes operaciones sobre los extremos del dipolo (para ello necesitaremos una Dremel):

1 - corte longitudinal de 4 mm.

2 - insertar hilo de cobre desnudo dentro, dado varias vueltas alrededor de la varilla de aluminio

3- crimpar con un alicate la varilla de aluminio y el hilo de cobre (quedara perfectamente unido electricamente)

4- cubrir con estaño el hilo de cobre

5- Ahora ya podemos soldar el coaxial

6- Proteger con silicona o pegamento caliente la uniones para que los elementos atmosfericos no puedan deteriorarlas.

![image](https://user-images.githubusercontent.com/48222471/185979307-dac56215-aed4-45f2-b8ae-2dd314cbcd0b.png)

![image](https://user-images.githubusercontent.com/48222471/185980989-77397cb9-303e-4a73-8eab-b3fcb06c6532.png)

Disposición elementos antena:

![image](https://user-images.githubusercontent.com/48222471/185982072-12188788-cfc3-4abd-a865-5b477c18bafe.png)

Medidas Reflector:

![image](https://user-images.githubusercontent.com/48222471/185982310-df78e4de-eb9a-4be3-8283-060819106e71.png)

Medidas Dipolo:

![image](https://user-images.githubusercontent.com/48222471/185982504-a7aa444d-312b-4617-9848-759d65ced827.png)

![image](https://user-images.githubusercontent.com/48222471/185982579-1c430b51-aa65-458e-89e7-031b1f2fa99e.png)

Medidas director:

![image](https://user-images.githubusercontent.com/48222471/185982764-51c40126-1148-49e7-bf62-8625f228ce32.png)

Los resultados han mejorado notablemente con respecto al rotor anterior (solo azimuth):
![image](https://user-images.githubusercontent.com/48222471/180614173-b6e6713a-deb8-4f4f-9173-88964b037b58.png)

Vista del hardware del rotor:

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

Como en un principio, estaba utilizando detector hall bipolares (cuando se les expone a un polo Sur se activan y hasta que no se le expone a un polo Norte no se desactivan, en el sistema de imanes van 3 filas de imanes:  norte - sur  - norte (cuando llega el norte se desactiva y cuando llega el sur se activa):

![image](https://user-images.githubusercontent.com/48222471/184389039-ed0e3010-747f-4081-a10d-db2c2ae1073b.png)

EJE AZIMUTH

Compuesto por un nema 17 con Gearbox  relacion 50:1

![image](https://user-images.githubusercontent.com/48222471/184946869-ffdb750c-8a7a-4a3b-9e8b-889a0e291979.png)

Al eje del Gearbox he colocado un acoplador (8 mm.  - 10 mm.):

![image](https://user-images.githubusercontent.com/48222471/184947100-25fa2059-077a-4ea2-84b7-06cd7b0832cc.png)

La parte de 8 mm. va al Gearbox y la de 10 mm. a un eje de aluminio de 30 cm. de longitud y mediante una pieza hecha cen 3D al interior del mastil.
Dado que el acoplador dispone de una parte elastica, se va a comportar como un cardan y eliminará las ligeras faltas de alineacion que pueda haber entre el Gearbox y el mastil que gira sobre los 2 soporte puente.


Funcionamiento

El sistema se encuentra parado a la espera de que al TinyGS le indique a que satelite debe seguir.
Una vez que la TinyGS le envia via peticion GET el nombre del satelite a seguir, el ESP32 del rotor entra en internet y se descarga los TLE actuales de dicho satelite y cuando se encuentre visible, comienza a seguirlo. 

Cuando se encuentre no visible, es decir que la elevacion sea menor de 0 grados, dejará de seguirlo.

Y asi a la espera de recibir de la TinyGS la orden de seguir a otro satelite.

19/02/20232 He descubierto que al estar el ESP32 del rotor cerca de la antena interfiere, por la WIFI, en la señales que se reciben desde los satelites. 
Mas en concreto de los satelites que envian alrededor de los 400 Mhz. 
Lo he "solucionado" provisionalmente desactivando la WIFI cuando se esta haciendo el seguimiento de un satelite, y volviendola a activar cuando el satelite deja de
estar visible.
Durante el tiempo de silencio WIFI, no puedo acceder al ESP32 del rotor y no acepta comando GET para el seguimiento de otros satelites.
Active la nueva funcionalidad sobre las 13:00 y se puede observar que la mejora es apreciable y el número de paquetes con CRC erroneo ha descendido.
![image](https://user-images.githubusercontent.com/48222471/219946906-e9aa5649-f6fa-4b95-a99c-58052608c960.png)

Ademas he separado mediante un coaxial de 3 metros la TinyGS de la antena, dejando solo la antena, el LNA y el filtro pasabanda. La TinyGS tambien emite WIFI y tambien 
interfiere en la señales que se reciben de los satelites.

En resumen, hay que dejar antena, LNA y filtros pasabanda solos y minimizar las emisiones de RF cercanas: parando la WIFI del ESP32 que controla el rotor y alejando la TinyGS.








