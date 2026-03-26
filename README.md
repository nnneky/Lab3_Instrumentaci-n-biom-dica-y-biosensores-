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

<img width="1062" height="507" alt="image" src="https://github.com/user-attachments/assets/7b84ad42-332c-42f3-a0c7-3bff7d60350a" />


Este enfoque permite obtener una respuesta más controlada y reproducible del CPT, facilitando la comparación entre condiciones de reposo, estímulo y recuperación dentro del análisis de resultados.


## Marco Teórico : 

La fotopletismografía (PPG) es una técnica óptica no invasiva ampliamente utilizada en la instrumentación biomédica para la evaluación de la dinámica cardiovascular y la perfusión sanguínea periférica. Su principio de funcionamiento se basa en la emisión de luz (generalmente en el espectro infrarrojo o rojo) hacia el tejido biológico y la medición de la luz reflejada o transmitida, la cual varía en función de los cambios en el volumen sanguíneo durante el ciclo cardíaco (Allen, 2007). Debido a su simplicidad, bajo costo y capacidad de integración en sistemas portátiles, la PPG se ha consolidado como una herramienta fundamental en dispositivos clínicos como el oxímetro de pulso y sistemas de monitoreo continuo.

Desde el punto de vista de su estructura, la señal PPG está compuesta por dos componentes principales: una componente continua (DC), asociada al volumen sanguíneo basal, tejido y absorción constante de luz, y una componente pulsátil (AC), que refleja las variaciones periódicas del volumen sanguíneo causadas por la actividad cardíaca (Tamura et al., 2014). Esta última es de especial interés, ya que contiene información relevante sobre parámetros fisiológicos como la frecuencia cardíaca, la variabilidad del pulso y características morfológicas de la onda, tales como la amplitud y el tiempo entre picos, que son fundamentales para el análisis hemodinámico.

La señal PPG no solo depende del sistema cardiovascular, sino que también está fuertemente modulada por el sistema nervioso autónomo (SNA), particularmente por la actividad del sistema simpático. Este sistema regula el tono vascular mediante mecanismos de vasoconstricción y vasodilatación, los cuales afectan directamente la perfusión periférica. Ante estímulos como el estrés, el dolor o la activación nociceptiva, se produce un incremento en la actividad simpática que induce vasoconstricción periférica, reduciendo la amplitud de la señal PPG y alterando su morfología (Challoner, 1979). Este fenómeno convierte a la PPG en una herramienta indirecta para evaluar la respuesta autonómica del organismo.

En el contexto clínico, especialmente en anestesia, resulta fundamental cuantificar el equilibrio entre nocicepción (respuesta del sistema nervioso ante estímulos dolorosos) y analgesia (supresión farmacológica de dicha respuesta). Tradicionalmente, esta evaluación ha sido subjetiva o basada en parámetros hemodinámicos generales; sin embargo, estos no siempre reflejan con precisión la respuesta nociceptiva. En este sentido, el índice pletismográfico quirúrgico (SPI, Surgical Pleth Index) surge como una herramienta cuantitativa que utiliza la señal PPG para estimar este balance (Huiku et al., 2007).

El SPI es un índice adimensional que varía entre 0 y 100 y se calcula a partir de dos parámetros principales derivados de la señal PPG: la amplitud de la onda de pulso (PPGA, Photoplethysmographic Pulse Wave Amplitude) y el intervalo entre latidos cardíacos (HB interval). Estos parámetros reflejan tanto la actividad vascular periférica como la regulación cardíaca, ambos modulados por el sistema autónomo. Un incremento en el SPI indica una mayor actividad simpática y, por tanto, una mayor respuesta nociceptiva, mientras que valores bajos indican un estado adecuado de analgesia (Huiku et al., 2007). En la práctica clínica, se considera que un rango entre 20 y 50 representa un equilibrio adecuado durante anestesia general .

A pesar de su utilidad, el SPI presenta limitaciones importantes. Su valor puede verse afectado por múltiples factores, como cambios en la temperatura periférica, el estado hemodinámico del paciente, la administración de fármacos vasoactivos y la variabilidad interindividual. Por esta razón, su uso debe complementarse con otros parámetros clínicos y no debe considerarse como un indicador absoluto de dolor o nocicepción (Ledowski, 2019).

Para validar y analizar el comportamiento del SPI en entornos experimentales, se emplean pruebas fisiológicas que inducen respuestas autonómicas controladas. Una de las más utilizadas es el Cold Pressor Test (CPT), el cual consiste en la exposición de una extremidad a bajas temperaturas (generalmente entre 4 °C y 10 °C) para provocar una activación del sistema nervioso simpático. Esta activación genera respuestas como vasoconstricción periférica, aumento de la presión arterial y cambios en la frecuencia cardíaca (Mitchell et al., 2004).

Desde el punto de vista de la señal PPG, el CPT produce una disminución en la amplitud de la onda de pulso debido a la reducción del flujo sanguíneo periférico. Esto se traduce en modificaciones en los parámetros utilizados para el cálculo del SPI, permitiendo observar un incremento del índice durante la aplicación del estímulo. De esta manera, el CPT se convierte en una herramienta experimental clave para simular condiciones de estrés o dolor de forma controlada y evaluar la sensibilidad del sistema desarrollado.

En el ámbito de la ingeniería biomédica, la implementación de sistemas de adquisición y procesamiento de señales PPG mediante plataformas como Arduino y MATLAB permite el desarrollo de soluciones de monitoreo ambulatorio. Estos sistemas integran sensores ópticos, circuitos de acondicionamiento de señal y algoritmos de procesamiento digital que permiten la detección de características relevantes de la señal, como máximos, mínimos, amplitud y frecuencia, necesarias para el cálculo del SPI en tiempo real (Webster, 2010).

En conjunto, la integración de la PPG, el análisis del sistema nervioso autónomo, el cálculo del SPI y la aplicación de pruebas como el CPT constituyen una base sólida para el desarrollo de sistemas biomédicos orientados al monitoreo del estado fisiológico del paciente. Estas herramientas no solo permiten comprender mejor la relación entre variables hemodinámicas y la respuesta al dolor, sino que también abren la puerta al desarrollo de tecnologías portátiles para el seguimiento continuo en entornos clínicos y ambulatorios.

 <img width="1048" height="522" alt="image" src="https://github.com/user-attachments/assets/bda09b96-ed40-4116-af16-c89284a53a09" />

 ## Código de MatLab : 
 

 ```bash
clc;
clear;
close all;
%% ============================
%   PARÁMETROS
% ============================
Fs = 100;
answer = inputdlg("Ingrese el tiempo de adquisición (s):", ...
"Tiempo de adquisición", 1, {"20"});
if isempty(answer)
    error("Cancelado");
end
T = str2double(answer{1});
if isnan(T) || T <= 0
    error("Tiempo inválido");
end
%% ============================
%   SERIAL
% ============================
s = serialport("COM3",115200);
configureTerminator(s,"LF");
flush(s);
pause(2);
%% ============================
%   FIGURA TIEMPO REAL
% ============================
figure;
h1 = animatedline('Color','r','LineWidth',0.8);
xlabel("Tiempo [s]");
ylabel("Señal PPG [V]");
title("Señal PPG - Tiempo real");
grid on;
xlim([0 T]);
%% ============================
%   ESTABILIZACIÓN
% ============================
disp("Estabilizando señal...");
t_estab = 1.0;
tic;
while toc < t_estab
    linea = readline(s);
end
disp("Adquiriendo señal PPG...");
%% ============================
%   ADQUISICIÓN POR TIEMPO REAL
% ============================
ppg = [];
ts  = [];
tic;
while toc <= T
    linea = readline(s);
    nums = regexp(linea,'[-+]?\d*\.?\d+','match');
    if isempty(nums)
        continue;
    end
    y = str2double(nums{1});
    if isnan(y)
        continue;
    end
    ppg(end+1) = y;
    ts(end+1)  = toc;
    addpoints(h1, ts(end), y);
    if mod(length(ppg), 5) == 0
        drawnow limitrate
    end
end
clear s
N       = length(ppg);
Fs_real = N / T;
fprintf("Muestras adquiridas : %d\n", N);
fprintf("Fs real             : %.1f Hz\n", Fs_real);
disp("Adquisición finalizada");
%% ============================
%   CENTRAR Y NORMALIZAR
% ============================
win_dc = round(2.0 * Fs_real);
ppg_c  = ppg - movmean(ppg, win_dc);

% Normalizar entre 0 y 1
ppg_n  = (ppg_c - min(ppg_c)) / (max(ppg_c) - min(ppg_c));

win   = max(3, round(0.05 * Fs_real));
ppg_d = movmean(ppg_n, win);
%% ============================
%   MÉTODO DEL MONTAÑERO
% ============================
max_idx = [];
min_idx = [];
estado  = 0;

for i = 2:length(ppg_d)
    if ppg_d(i) > ppg_d(i-1)
        if estado == -1
            min_idx(end+1) = i-1;
        end
        estado = 1;
    elseif ppg_d(i) < ppg_d(i-1)
        if estado == 1
            max_idx(end+1) = i-1;
        end
        estado = -1;
    end
end

fprintf("Máximos crudos    : %d\n", length(max_idx));
fprintf("Mínimos crudos    : %d\n", length(min_idx));
%% ============================
%   CÁLCULO SPI
% ============================
fprintf("------ SPI por latido (Método del Montañero) ------\n");
SPI = [];

for i = 1:length(max_idx)
    mins_prev = min_idx(min_idx < max_idx(i));
    if isempty(mins_prev)
        continue;
    end
    idx_v = mins_prev(end);
    Pmin  = ppg_n(idx_v);
    Pmax  = ppg_n(max_idx(i));
    if Pmax == 0
        continue;
    end
    spi = (Pmax - Pmin) / Pmax;
    SPI(end+1) = spi;
    fprintf("Latido %d -> SPI = %.3f\n", length(SPI), spi);
end

if ~isempty(SPI)
    fprintf("---\nSPI promedio = %.3f\n", mean(SPI));
    fprintf("Latidos detectados: %d\n",  length(SPI));
else
    disp("No se detectaron latidos válidos.");
end
%% ============================
%   GRÁFICA FINAL
% ============================
figure;
plot(ts, ppg_n, 'r'); hold on;
plot(ts(max_idx), ppg_n(max_idx), 'go', 'MarkerFaceColor','g', 'MarkerSize',7);
plot(ts(min_idx), ppg_n(min_idx), 'bo', 'MarkerFaceColor','b', 'MarkerSize',7);
xlabel("Tiempo [s]");
ylabel("Señal PPG (normalizada 0-1)");
title("PPG + detección de pulsos (Método del Montañero)");
legend("PPG","Máximos sistólicos","Pies del pulso");
grid on;
```

Este código en MATLAB sirve para adquirir, procesar y analizar una señal fotopletismográfica (PPG) en tiempo real desde un Arduino, con el objetivo de detectar los latidos y calcular un índice tipo SPI. Primero le pide al usuario el tiempo de adquisición y establece la comunicación serial con el Arduino para leer los datos de la señal. Luego, muestra la señal en tiempo real mientras la va guardando. Una vez termina la adquisición, la señal se centra (se elimina el nivel DC), se normaliza entre 0 y 1 y se suaviza para reducir ruido. Después aplica el llamado “método del montañero”, que básicamente detecta subidas y bajadas en la señal para identificar los máximos (picos del pulso) y mínimos (inicio del pulso). Con estos puntos, el código calcula un valor de SPI por cada latido usando la diferencia entre el valor máximo y mínimo de cada pulso, lo que refleja cambios en la amplitud de la señal. Finalmente, muestra los resultados en consola (como el SPI promedio) y genera una gráfica donde se visualiza la señal junto con los puntos detectados, permitiendo analizar cómo varía el pulso en el tiempo.

## Código en Arduino : 

```bash
#include <Wire.h>
#include "MAX30105.h"

MAX30105 particleSensor;

void setup()
{
  Serial.begin(115200);
  Serial.println("Initializing...");

  // Initialize sensor
  if (!particleSensor.begin(Wire, I2C_SPEED_FAST)) //Use default I2C port, 400kHz speed
  {
    Serial.println("MAX30105 was not found. Please check wiring/power. ");
    while (1);
  }

  //Setup to sense a nice looking saw tooth on the plotter
  byte ledBrightness = 0x1F; //Options: 0=Off to 255=50mA
  byte sampleAverage = 8; //Options: 1, 2, 4, 8, 16, 32
  byte ledMode = 3; //Options: 1 = Red only, 2 = Red + IR, 3 = Red + IR + Green
  int sampleRate = 100; //Options: 50, 100, 200, 400, 800, 1000, 1600, 3200
  int pulseWidth = 411; //Options: 69, 118, 215, 411
  int adcRange = 4096; //Options: 2048, 4096, 8192, 16384

  particleSensor.setup(ledBrightness, sampleAverage, ledMode, sampleRate, pulseWidth, adcRange); //Configure sensor with these settings

  //Arduino plotter auto-scales annoyingly. To get around this, pre-populate
  //the plotter with 500 of an average reading from the sensor

  //Take an average of IR readings at power up
  const byte avgAmount = 64;
  long baseValue = 0;
  for (byte x = 0 ; x < avgAmount ; x++)
  {
    baseValue += particleSensor.getIR(); //Read the IR value
  }
  baseValue /= avgAmount;

  //Pre-populate the plotter so that the Y scale is close to IR values
  for (int x = 0 ; x < 500 ; x++)
    Serial.println(baseValue);
}

void loop()
{
  Serial.println(particleSensor.getIR()); //Send raw data to plotter
}
```
Este código de Arduino tiene como objetivo adquirir la señal PPG utilizando el sensor MAX30105 y enviarla en tiempo real al computador a través del puerto serial. Primero, en la función setup(), se inicializa la comunicación serial y el sensor mediante I2C; si el sensor no se detecta, el programa se detiene. Luego, se configuran parámetros importantes como el brillo del LED, el número de muestras promediadas, el modo de LEDs (rojo, infrarrojo y verde), la frecuencia de muestreo y el rango del ADC, lo cual determina la calidad y resolución de la señal. Después, el código toma varias lecturas iniciales para calcular un valor promedio de la señal IR y lo envía repetidamente al plotter serial, con el fin de estabilizar la escala de la gráfica. Finalmente, en el loop(), el programa lee continuamente el valor de la señal infrarroja (getIR()), que corresponde a la señal PPG, y la envía por el puerto serial, permitiendo visualizarla en tiempo real en el computador para su posterior análisis.

## Gráficas : 

<img width="761" height="461" alt="image" src="https://github.com/user-attachments/assets/741f9737-5aad-4cc4-98d5-6a5d05f563c3" /> 

Gráfica PPG a tiempo real.

<img width="777" height="443" alt="image" src="https://github.com/user-attachments/assets/7d4c715a-6153-48ee-821d-9a69605555a5" />

Cáptura SPI  a tiempo real cada 10 segundos.

## Analísis : 

El comportamiento del índice pletismográfico quirúrgico (SPI) a lo largo del tiempo evidencia tres fases claramente diferenciables: una fase inicial de reposo (0–40 s), una fase de estímulo correspondiente a la aplicación del Cold Pressor Test (40–80 s) y una fase de recuperación posterior (>80 s). En la primera ventana (0–10 s), se observa un valor de SPI relativamente bajo (0.165), lo cual puede atribuirse tanto a condiciones de reposo como a la estabilización inicial del sistema de medición. Sin embargo, a partir de la segunda ventana, los valores aumentan significativamente (≈0.85), lo que sugiere una mayor sensibilidad del sistema una vez estabilizada la señal.

Durante la fase previa al estímulo (hasta el segundo 40), el SPI presenta valores elevados y relativamente constantes (entre 0.78 y 0.86), lo cual podría indicar que el sistema es sensible a pequeñas variaciones en la señal PPG o que existe un nivel basal de activación simpática en el sujeto. No obstante, es a partir de la ventana correspondiente al intervalo de 40–50 s donde se inicia la aplicación del Cold Pressor Test, momento en el cual se observa una tendencia a la disminución progresiva del SPI (de ≈0.78 a ≈0.61 en ventanas posteriores).

Este comportamiento puede explicarse fisiológicamente, ya que el Cold Pressor Test induce una respuesta simpática caracterizada por vasoconstricción periférica. Esta vasoconstricción reduce la amplitud de la señal PPG, lo cual afecta directamente el cálculo del SPI basado en la diferencia relativa entre máximos y mínimos. En este caso particular, la disminución del SPI durante el estímulo sugiere que la métrica implementada es altamente dependiente de la amplitud de la señal y no necesariamente refleja de forma directa el aumento de la actividad simpática, lo que constituye una limitación del modelo utilizado.

En la fase posterior al estímulo (después de 80 s), se observa que el SPI tiende a estabilizarse en valores intermedios (≈0.56 – 0.72), lo que indica un proceso de recuperación fisiológica del sujeto. Este comportamiento es consistente con la disminución progresiva de la activación simpática una vez retirado el estímulo frío, permitiendo la restauración del flujo sanguíneo periférico y, por ende, de la amplitud de la señal PPG.

En cuanto al número de latidos detectados, se evidencia un incremento durante la aplicación del estímulo (hasta 13 latidos por ventana), lo cual es coherente con una posible elevación de la frecuencia cardíaca inducida por el CPT. Este resultado respalda la presencia de una respuesta autonómica al estímulo aplicado. Sin embargo, la variabilidad en la detección de latidos también sugiere la influencia de ruido o limitaciones en el algoritmo de detección.

La gráfica de la señal PPG muestra una señal suavizada y normalizada, donde se identifican correctamente los máximos sistólicos y los pies del pulso. No obstante, la baja variabilidad en amplitud observada en la gráfica indica que el proceso de normalización reduce la capacidad de visualizar cambios fisiológicos reales, lo que impacta directamente en la interpretación del SPI.

En conjunto, los resultados demuestran que el sistema desarrollado es capaz de captar cambios fisiológicos asociados a la aplicación del Cold Pressor Test, evidenciados en la variación del SPI y en el número de latidos detectados. Sin embargo, también se identifican limitaciones importantes en la forma en que se calcula el índice, ya que este no refleja completamente el comportamiento esperado de la respuesta simpática. Esto sugiere la necesidad de incorporar parámetros adicionales o mejorar el procesamiento de la señal para obtener una estimación más precisa del estado nociceptivo.

## Conclusiones : 

En conclusión, el desarrollo de la práctica permitió implementar de manera exitosa un sistema de adquisición y procesamiento de la señal fotopletismográfica (PPG) para la estimación de un índice tipo SPI en condiciones ambulatorias, evidenciando la relación entre la señal periférica y la actividad del sistema nervioso autónomo. A partir de los resultados obtenidos, se logró observar una variación del SPI asociada a la aplicación del Cold Pressor Test, reflejando cambios fisiológicos como la vasoconstricción periférica y el aumento de la actividad simpática, lo cual valida la sensibilidad del sistema ante estímulos nociceptivos controlados. No obstante, también se identificaron limitaciones importantes, especialmente en el método de cálculo del SPI basado únicamente en la amplitud de la señal y en el efecto de la normalización, lo que impide una correspondencia directa con los índices clínicos reales. Asimismo, la variabilidad en la detección de latidos y la influencia del ruido resaltan la necesidad de mejorar los algoritmos de procesamiento y de incorporar múltiples parámetros fisiológicos para una estimación más precisa. En conjunto, la práctica permitió no solo comprender los fundamentos de la PPG y su aplicación en el monitoreo biomédico, sino también analizar críticamente el alcance y las limitaciones de los sistemas desarrollados, aportando una base sólida para futuras mejoras en el diseño de herramientas de evaluación no invasiva del estado autonómico y nociceptivo.

## Preguntas para la discusión  : 

   - 1.    ¿Cómo se relacionan las variaciones del volumen sanguíneo periférico con el balance autonómico?

   Las variaciones del volumen sanguíneo periférico, medidas a través de la señal PPG, están directamente influenciadas por el sistema nervioso autónomo, especialmente por el equilibrio entre la actividad simpática y parasimpática. Cuando predomina la actividad simpática, como ocurre ante estímulos de estrés o dolor, se produce vasoconstricción periférica, lo que reduce el flujo sanguíneo en los tejidos y disminuye la amplitud de la señal PPG. Por el contrario, cuando predomina la actividad parasimpática, se favorece la vasodilatación, aumentando el flujo sanguíneo y la amplitud de la señal. Por lo tanto, las variaciones observadas en la PPG reflejan cambios en el balance autonómico y permiten inferir el estado fisiológico del organismo frente a diferentes estímulos.

   - 2.   ¿Cómo se compara el SPI con otros índices comúnmente empleados en cirugía, como el índice nocicepción-analgesia (ANI) y el índice de perfusión?

   El SPI, el ANI y el índice de perfusión son herramientas utilizadas para evaluar el estado fisiológico del paciente durante procedimientos quirúrgicos, pero se basan en diferentes principios. El SPI se deriva de la señal PPG y combina información de la amplitud del pulso y la frecuencia cardíaca para estimar el balance entre nocicepción y analgesia, estando más asociado a la actividad simpática. Por otro lado, el ANI se basa en el análisis de la variabilidad de la frecuencia cardíaca (HRV), reflejando principalmente la actividad parasimpática. Mientras tanto, el índice de perfusión mide la relación entre el componente pulsátil y no pulsátil de la señal PPG, indicando el nivel de perfusión periférica, pero sin estar diseñado específicamente para evaluar dolor.

En comparación, el SPI es más sensible a cambios rápidos asociados al dolor o estrés, mientras que el ANI proporciona una visión más relacionada con la regulación parasimpática. El índice de perfusión, aunque útil, es menos específico para la evaluación nociceptiva. Por ello, estos índices suelen considerarse complementarios, ya que cada uno aporta información distinta sobre el estado autonómico del paciente.

## Referencias : 

- Allen, J. (2007). Photoplethysmography and its application in clinical physiological measurement. Physiological Measurement, 28(3), R1–R39. https://doi.org/10.1088/0967-3334/28/3/R01

- Challoner, A. V. J. (1979). Photoelectric plethysmography for estimating cutaneous blood flow. En J. S. Rolfe (Ed.), Non-invasive physiological measurements (pp. 125–151). Academic Press.

- Huiku, M., Uutela, K., van Gils, M., Korhonen, I., Kymäläinen, M., Meriläinen, P., Paloheimo, M., Rantanen, M., Takala, P., Viertiö-Oja, H., & Yli-Hankala, A. (2007). Assessment of surgical stress during general anaesthesia. British Journal of Anaesthesia, 98(4), 447–455. https://doi.org/10.1093/bja/aem004

- Ledowski, T. (2019). Objective monitoring of nociception: A review of current commercial solutions. British Journal of Anaesthesia, 123(2), e312–e321. https://doi.org/10.1016/j.bja.2019.03.024

- Mitchell, L. A., MacDonald, R. A., & Brodie, E. E. (2004). Temperature and the cold pressor test. The Journal of Pain, 5(4), 233–237. https://doi.org/10.1016/j.jpain.2004.03.004

- Tamura, T., Maeda, Y., Sekine, M., & Yoshida, M. (2014). Wearable photoplethysmographic sensors—Past and present. Electronics, 3(2), 282–302. https://doi.org/10.3390/electronics3020282

 - Webster, J. G. (2010). Medical instrumentation: Application and design (4th ed.). Wiley.
