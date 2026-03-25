# Laboratorio 3 Instrumentación | Cálculo ambulatorio del índice pletismográfico quirúrgico (SPI) 

 - Daniel Espinosa 5600778
 - Samuel Velandia 5600777


## Introducción : 


La señal fotopletismográfica (PPG) comprende los fenómenos ópticos asociados a la variación del volumen sanguíneo en los tejidos periféricos. Esta señal cambia principalmente debido a la actividad del sistema nervioso autónomo, el cual regula la vasoconstricción y vasodilatación. Cuando una persona experimenta dolor, estrés o estímulos nociceptivos, se producen cambios en la perfusión periférica que se reflejan en la forma y amplitud de la señal PPG.

A partir de esta señal es posible estimar el índice pletismográfico quirúrgico (SPI, Surgical Pleth Index), el cual es un parámetro utilizado para evaluar el balance entre nocicepción y analgesia durante anestesia general. Este índice se basa en características de la onda de pulso y permite cuantificar la respuesta fisiológica del organismo ante estímulos dolorosos.

El SPI se interpreta dentro de un rango de valores entre 0 y 100:

Valores bajos: indican un adecuado nivel de analgesia.

Valores altos: reflejan una mayor respuesta nociceptiva (estrés fisiológico).

En condiciones clínicas, el rango objetivo suele estar entre 20 y 50 para garantizar un equilibrio adecuado durante procedimientos quirúrgicos

<img width="241" height="237" alt="image" src="https://github.com/user-attachments/assets/65c08d8e-94c8-4e77-8b9c-cfdc0a89c2db" />

Este tipo de medición ha sido ampliamente utilizado en el monitoreo intraoperatorio, ya que proporciona una estimación objetiva del estado del paciente. Sin embargo, aunque es una herramienta útil para evaluar la respuesta autonómica al dolor, presenta limitaciones y no debe considerarse como un método diagnóstico único, sino como un complemento dentro del monitoreo clínico.


## Objetivos : 

# Objetivo general: 

  Desarrollar un sistema capaz de adquirir, procesar y analizar la señal fotopletismográfica para el cálculo del índice pletismográfico quirúrgico (SPI) en condiciones ambulatorias.
  
# Objetivos específicos:

  - Identificar y extraer las características principales de la señal PPG necesarias para el cálculo del SPI.
  - Implementar un algoritmo en MATLAB que permita calcular el SPI a partir de la detección de máximos y mínimos de la señal adquirida.
  - Evaluar el comportamiento del SPI en condiciones de reposo y durante la aplicación de un estímulo fisiológico (Cold Pressor Test), analizando sus variaciones.

## Materiales : 

- Computador con acceso a Internet

- MATLAB

- Arduino UNO o Nano

- Regleta de Proto-Board

- Cables UTP (varios)

- Resistencias de varios valores (aprox. 1 kΩ a 680 kΩ)

- Condensador cerámico o de tántalo (100 nF)

- Condensador electrolítico (4.7 µF)

- Transistor 2N3904

- Sensor de reflectancia TCRT1000 o acoplador óptico TCST110

- Amplificador operacional dual LM358


## Procedimiento  : 

- Parte A

En esta etapa se inicia con la construcción del circuito en una Proto-Board, el cual permite capturar las variaciones del volumen sanguíneo periférico mediante un sensor óptico. En caso de emplear un optoacoplador TCST110, este debe ser modificado para que funcione como un sensor de reflectancia, garantizando así la correcta adquisición de la señal fotopletismográfica.

Posteriormente, la salida del circuito se conecta a una de las entradas analógicas de una placa Arduino UNO o Nano. Se verifica la señal obtenida utilizando la herramienta “Serial Plotter”, realizando los ajustes necesarios mediante los potenciómetros para reducir el ruido y mejorar la calidad de la señal. Finalmente, se investiga la técnica conocida como Cold Pressor Test (CPT), con el fin de comprender su funcionamiento y definir cómo será aplicada durante la práctica.
  
- Parte B

En esta parte, se realiza una revisión bibliográfica para obtener la definición matemática del índice pletismográfico quirúrgico (SPI), la cual debe ser incluida en el desarrollo del informe. Luego, se diseña e implementa un código en MATLAB capaz de capturar la señal proveniente del circuito, detectar máximos y mínimos de la señal y calcular el SPI en cada latido, mostrando los resultados en la consola.

<img width="833" height="422" alt="image" src="https://github.com/user-attachments/assets/931ad521-f2da-4d6b-a30d-cc56a33dd1f7" />

A continuación, se realiza una medición experimental con un voluntario durante un periodo aproximado de dos minutos. Inicialmente, el sujeto permanece en reposo durante 40 segundos; posteriormente, se aplica el Cold Pressor Test durante otros 40 segundos, y finalmente se permite un periodo de recuperación de 40 segundos. Durante todo el proceso se registran los valores del SPI para analizar su comportamiento ante el estímulo. Finalmente, el código se modifica para generar una gráfica que permita visualizar la evolución del SPI en función del tiempo.

## Cold pressure test : 

El Cold Pressor Test (CPT) es una prueba ampliamente utilizada en estudios fisiológicos para inducir una respuesta del sistema nervioso autónomo, particularmente del sistema simpático. Esta consiste en la exposición de una extremidad, generalmente la mano, a bajas temperaturas con el fin de generar un estímulo nociceptivo controlado. Como resultado, se producen cambios fisiológicos como vasoconstricción periférica, aumento de la presión arterial y modificaciones en la señal fotopletismográfica (PPG), lo que permite evaluar la respuesta del organismo ante el estrés.

En el contexto de la señal PPG, el CPT provoca una disminución en la amplitud de la señal debido a la vasoconstricción periférica inducida por el frío. Esto se traduce en variaciones en las características de la onda de pulso, las cuales son utilizadas para el cálculo del índice pletismográfico quirúrgico (SPI). Por lo tanto, esta prueba permite simular una condición de estrés o dolor controlado, facilitando el análisis del comportamiento del SPI ante un estímulo fisiológico.

Para la realización de esta práctica, se empleará un guante de uso doméstico (como los utilizados para lavar los trastes), el cual permitirá contener el medio frío y garantizar una mejor sujeción de la mano del voluntario. El guante será llenado con agua y pequeños fragmentos de hielo, asegurando que la temperatura del sistema se mantenga en un rango aproximado entre 4 °C y 8 °C. Este rango permite generar un estímulo suficiente sin representar un riesgo para el participante.
 
Durante el procedimiento experimental, el voluntario colocará su mano dentro del guante previamente preparado, manteniéndola allí durante un intervalo de tiempo definido (aproximadamente 40 segundos). Mientras se realiza esta exposición al frío, se registrará de manera continua la señal PPG y se calculará el SPI, permitiendo observar las variaciones generadas por el estímulo. Posteriormente, se retirará la mano del guante para permitir la recuperación fisiológica, continuando con la adquisición de datos.



Este enfoque permite obtener una respuesta más controlada y reproducible del CPT, facilitando la comparación entre condiciones de reposo, estímulo y recuperación dentro del análisis de resultados.
