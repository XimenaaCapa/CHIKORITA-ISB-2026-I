# Laboratorio Electrocarfiografía (ECG)
## Introducción
La electrocardiografía (ECG) es una técnica que registra la actividad eléctrica del corazón para el análisis de la función cardíaca como la detección de arritmias y monitoreo de la salud cardiovascular [1].

Se han estudiado aplicaciones de ECG en contextos clínicos para diagnóstico y seguimiento de pacientes.Así como en rehabilitación cardiaca para evaluar la recuperación funcional y en el deporte para analizar adaptaciones fisiológicas en atletas y diferenciar patrones normales de hallazgos patológicos.[2].

En este laboratorio se está desarrollando la adquisición de la señal ECG con el objetivo de obtener la diferencia de actividad eléctrica durante el ciclo cardíaco.   

## Metodología
Para la correcta extracción de datos ECG se trabajará con los siguientes materiales
| Equipo | Cantidad |
| :--- | :--- |
| Kit Bitalino | 1 |
| Assembled Electrocardiography (ECG) Sensor | 1 |
|Gelled Self-adhesive Disposable Ag/AgCl- Electrodes|3|
| Bluetooth dongle|1|

### 1. Conexión del set Bitalino inicial
Se debe comenzar por conectar la bateria y encender el equipo
<img width="766" height="492" alt="image" src="https://github.com/user-attachments/assets/a240b11c-1bd4-4e96-8db6-8b4b703a3fad" />  

Se conecta al puerto de *Electrocardiography (ECG)*
<img width="1284" height="712" alt="image" src="https://github.com/user-attachments/assets/47e39ec0-1898-4556-9390-f0047fb3895d" />


### 2. Conexión Bitalino al sofware
Como primer paso, se tuvo que conectar mediante bluetooth el dispositivo de adquisición con la computadora. Luego se trabajará con la señal mediante la librería **opensignalsreader** en google collab.

### 3. Colocación de electrodos 
| Derivada | Electrodo positivo| Electrodo negativo| Neutro |
| :--- | :--- | :--- | :--- |
| Primera derivada | LA (Brazo izquierdo)| RA (Brazo derecho)| Cresta iliaca|
| Segunda derivada | Cresta ilíaca| RA (Brazo derecho)| LA (Brazo izquierdo)|
| Tercera derivada |Cresta ilíaca | LA (Brazo izquierdo)| RA (Brazo derecho) |

## Primera derivada
Se utiliza el electrodo negro (-) en la posición derecha y el rojo (+) en la izquierda. Luego, se coloca el electrodo blanco (referencia) en la cresta iliaca. 
| Referencia de posición |Referencia de colocación de electrodos|
| :--- | :--- |
|<img width="230" height="235" alt="image" src="https://github.com/user-attachments/assets/e266ef1d-15fa-4a4f-85d0-8b4c92d34c6d" /> |<img width="200" height="266" alt="image" src="https://github.com/user-attachments/assets/7ba9ed68-d47f-4228-8828-2ee064da3aac" />|

### Vista frontal de la colocación de los electrodos
<img width="694" height="445" alt="image" src="https://github.com/user-attachments/assets/a2c33e1b-ddae-4051-8be5-b8031194218a" />

## 1. Señal basal
### 1.1 Video señal basal 
https://github.com/user-attachments/assets/e4181f79-6d54-497a-8aed-47a3728b01e4

### 1.2. Ciclo inhalación 

### 1.3. Segunda señal basal

## 2. Actividad física 
### 2.1 Burpees

## 3. Mantener respiración

## Segunda derivada
Se cambia de posición el electrodo positivo a la cresta iliaca y el de referencia a la posición izquierda.
<img width="679" height="494" alt="image" src="https://github.com/user-attachments/assets/ec505f03-1735-4f70-9448-46ff57b63047" />

## Tercera derivada
Se cambia de posición el electrodo negativo a la posicón izquierda y el de referencia a la posición derecha.
<img width="766" height="505" alt="image" src="https://github.com/user-attachments/assets/60db3d29-11b1-4993-816a-cdb05eb99f37" />

## Resultados
### Estado basal - Derivada 1
<img width="1389" height="691" alt="basal_D1" src="https://github.com/user-attachments/assets/7039b05d-7690-4316-a228-f558d21e0d97" />

### Estado basal - Derivada 2
<img width="1390" height="691" alt="basal_D2" src="https://github.com/user-attachments/assets/7f0fd7bf-7440-4cc4-bbd0-b414b19cdeae" />

### Estado basal - Derivada 3
<img width="1389" height="691" alt="basal_D3" src="https://github.com/user-attachments/assets/e9a6f2a4-a482-45b6-889f-20f8eefd8d3a" />

### Estado basal después de hiperventilación - Derivada 1
<img width="1389" height="691" alt="basal_hiperv_D1" src="https://github.com/user-attachments/assets/813a70f3-82b9-4f37-a193-e1dc34564fbe" />


### Estado basal después de hiperventilación - Derivada 2
<img width="1390" height="691" alt="basal_hiperv_D2" src="https://github.com/user-attachments/assets/0ab8f447-22df-4cac-8153-1c5615ffbf45" />


### Estado basal después de hiperventilación - Derivada 3
<img width="1389" height="691" alt="basal_hiperv_D3" src="https://github.com/user-attachments/assets/88624819-4f38-4b1b-95d9-22121b98abb9" />

### Señal después de actividad física - Derivada 1
<img width="1389" height="691" alt="actividad_D1" src="https://github.com/user-attachments/assets/5aa1f288-1219-4df6-9700-8ad0837a1657" />


### Señal después de actividad física - Derivada 2
<img width="1389" height="691" alt="actividad_D2" src="https://github.com/user-attachments/assets/749ffb4d-5cb8-4856-b39f-9aac9a599870" />


### Señal después de actividad física - Derivada 3
<img width="1389" height="691" alt="actividad_D3" src="https://github.com/user-attachments/assets/441c652b-cb8c-432f-9ec8-05092cd395a2" />

### Señal durante la retención de aire - Derivada 1
<img width="1389" height="691" alt="respiracion_D1" src="https://github.com/user-attachments/assets/fd3b7286-cb3d-4aaa-b295-3f5e2148b731" />


### Señal durante la retención de aire - Derivada 2
<img width="1389" height="691" alt="respiracion_D2" src="https://github.com/user-attachments/assets/69b238f9-a81f-4c85-8f5e-3fc56fa2fa5c" />


### Señal durante la retención de aire - Derivada 3
<img width="1389" height="691" alt="respiracion_D3" src="https://github.com/user-attachments/assets/b42bd0b9-a79b-4fab-9fc8-c01b6c3aef60" />






## Discusión
### Q1. ¿Cuáles son los tipos más comunes de fuentes de ruido que afectan al ECG?
El ruido es uno de los principales problemas para la adquisición de señales biomédicas. Este puede clasificarse según su origen y su frecuencia. Entre los tipos más comunes se encuentra la interferencia de la línea de potencia a 50 a 60 Hz, generada por el acoplamiento electromagnético con la red eléctrica que se encuentran en las viviendas y los equipos médicos 
en el ámbito clínico.[3]

Otra fuente significativa de ruido son las señales electromiográficas (EMG), producidas por la contracción de los músculos esqueléticos durante la tensión muscular. Su espectro de frecuencia es amplio y se solapa frecuentemente con el complejo QRS, lo que dificulta considerablemente su filtrado sin comprometer la información clínica del registro cardíaco.[3]

Asimismo, antes de iniciar el protocolo de adquisición, es necesario establecer una línea base para identificar el ruido de baja frecuencia que se origina por la respiración y los movimientos corporales breves. Durante la respiración, la expansión y contracción de la cavidad torácica desplaza la posición relativa del corazón, en la cual, modifica la impedancia entre los electrodos y la piel.[3]

Finalmente, los movimientos bruscos pueden provocar cambios repentinos en la impedancia electrodo-piel, fenómeno estrechamente relacionado con una preparación inadecuada de la piel, como la presencia de vello excesivo, grasa o la ausencia de gel conductor. Una impedancia elevada incrementa la susceptibilidad del electrodo a captar interferencias externas, deteriorando aún más la calidad de la señal adquirida. [3]

### Q2. ¿Por qué el cambio en la posición de los sensores (derivaciones I-III) modifica los componentes de la señal ECG? ¿Cómo cambian estos componentes?
Para cada derivación del ECG registra la proyección de dicho vector sobre su propio eje espacial, por lo que la señal obtenida depende directamente del ángulo entre ambos: cuando el vector es paralelo al eje de la derivación la amplitud es máxima, cuando es perpendicular la señal es isoeléctrica, y cuando apunta en sentido opuesto la onda resulta negativa, en la cual también es muy importante para poder hallar las diferencias relevantes para poder obtener las derivaciones.[4]

En la cual las derivaciones I, II y III poseen orientaciones espaciales distintas, esto debido a que sus proyecciones difieren tanto en amplitud como en morfología. El complejo QRS, suele ser de mayor amplitud en la Derivación II, por estar más alineada con la dirección dominante del vector ventricular, mientras que la onda P puede presentarse bifásica en algunas derivaciones y positiva en otras,también es una de las más relevantes para poder determinar alguna anomalía fisiopatológica. [4]


### Q3. Describe si existen diferencias importantes en la señal al adquirirla desde distintas ubicaciones del cuerpo (por ejemplo: muñeca / clavícula / pecho). ¿Cuál podría ser la causa? ¿Esperabas estos cambios en la señal? Guarda un segmento de señal de cada caso para visualizar las diferencias.
Sí, existen diferencias significativas al adquirir la señal ECG desde distintas ubicaciones del cuerpo. Durante cada latido, las células del corazón se despolarizan y repolarizan, generando corrientes eléctricas que se propagan a través del tejido cardíaco. La suma de estas corrientes da lugar a un campo eléctrico que se distribuye en el espacio tridimensional del cuerpo. Este comportamiento suele modelarse mediante un vector dipolar cardíaco, que representa la dirección y magnitud global de la actividad eléctrica en cada instante.[5]

Cada electrodo del ECG registra una proyección distinta de ese campo eléctrico tridimensional, por lo que la señal observada depende de la posición, orientación y distancia respecto al corazón, así como de las propiedades eléctricas de los tejidos interpuestos (como músculo, grasa y hueso), que pueden atenuar y distorsionar la señal.[5]

En el pecho (derivaciones precordiales), al estar más cerca del corazón y con menor atenuación, se obtiene una señal de mayor amplitud y con ondas P, QRS y T claramente definidas. En la región de la clavícula, la señal presenta una amplitud intermedia y una morfología similar, aunque más atenuada debido a la mayor distancia y a la presencia de estructuras óseas. En la muñeca, la señal es de menor amplitud y más susceptible a ruido, especialmente artefactos de movimiento y actividad muscular, además de variaciones en la impedancia de contacto electrodo-piel. [6]


### Q4. Se sabe que los sistemas cardíaco y respiratorio están estrechamente relacionados. ¿Esperas que diferentes tipos de respiración (por ejemplo, más rápida o más profunda) influyan en las señales de ECG? Muestra capturas de señales de ECG en distintas condiciones respiratorias y describe las variaciones, si las hay.

Sí hay cambios: en una respiración normal hay variación leve y rítmica de los intervalos R-R, la frecuencia cardiaca sube levemente al inhalar y baja al exhalar, mientras que en una respiración rápida, las variaciones del intervalo R-R son más frecuentes, pero de menor amplitud, con posible ruido del movimiento del tórax, así mismo, en una respiración profunda, las variaciones del intervalo R-R son más pronunciadas y lentas, con un cambio de amplitud de la onda R, porque el corazón se desplaza con el diafragma.[7]

<img width="550" height="461" alt="fig6" src="https://github.com/user-attachments/assets/e4d66a79-ea77-47ad-817a-daab2a897489" />
<img width="510" height="459" alt="fig7" src="https://github.com/user-attachments/assets/513a8a9e-eb4e-423c-a2d2-e7986a696c29" />

En la etapa 1 se ve la gráfica en reposo de una señal con ritmo cardiaco estable; en la etapa 2 se puede ver una variación de la frecuencia cardiaca, con la amplitud de las ondas T de mayor magnitud; en la etapa 3, la morfología de los complejos QRS se mantiene todavía similar, pero los intervalos R-R son más cortos. En la etapa 4, aumenta considerablemente la frecuencia cardiaca, se acortan más los intervalos R-R; además, hay una ligera elevación del segmento ST. Por su parte, en la etapa 5, la frecuencia cardiaca llega a ser la mayor entre todas las señales, que es acorde al esfuerzo máximo que se está realizando, con intervalos R-R mucho más reducidos, donde visualmente la onda P puede verse superpuesta con la onda T. Finalmente, en la etapa 6, la frecuencia cardiaca empieza a disminuir, los intervalos R-R se empiezan a alargar, la forma de las ondas se empieza a regularizar o volver a su forma basal.[7]


### Q5. En el Home-Guide #1 viste que diferentes niveles de fuerza muscular generan señales con distintas amplitudes. ¿Cómo influye el movimiento en tu señal de ECG?

El movimiento muscular influye en la calidad de la señal de ECG, ya que cualquier actividad física como caminar, mover los brazos o incluso respirar con fuerza pueden generar una interferencia mecánica y eléctrica que puede comprometer la calidad de diagnósticos. Esta interferencia se debe al desplazamiento o movimiento de los electrodos sobre la piel como es el caso de la actividad eléctrica de los músculos cercanos que pueden producir esta alteración. Estas alteraciones  se pueden manifestar de diferentes formas, una de ellas es el desplazamiento de la línea base, el cual ocurre cuando movimientos involuntarios como temblores, hipo o inquietud provocan variaciones lentas en la señal, alejándose de su eje original. [8]

Asimismo, el ruido muscular suele afectar ciertas fases del ECG, como la despolarización auricular (onda P) y la repolarización ventricular (onda T). Por ello estas interferencias o también denominadas artefactos de movimiento pueden asemejarse a arritmias reales, lo cual puede producir errores graves en el diagnóstico médico.[8]


### Q6. Según tu conocimiento, ¿cómo puedes detectar bradicardia y taquicardia en la señal de ECG?
Para detectar la bradicardia y la taquicardia en un ECG, se debe analizar la frecuencia y la morfología de las ondas, considerando que la bradicardia se define generalmente como una frecuencia cardíaca lenta, inferior a 60 latidos por minuto, y puede manifestarse a través de bloqueos cardíacos como el de primer grado con un intervalo PR superior a 0,2 segundos o el síndrome del seno enfermo, que puede mostrar pausas prolongadas. Por otro lado, la taquicardia, caracterizada por la frecuencia cardiaca rápida, se clasifica según la duración del complejo QRS.[9] 

Se considera estrecha si mide menos de 0,12 segundos, permitiendo diferenciar entre la taquicardia sinusal, la supraventricular, la fibrilación auricular o el aleteo auricular; mientras que se clasifica como ancha si el QRS supera los 0,12 segundos, lo que incluye la taquicardia ventricular o la torsades de pointes, caracterizada por complejos que parecen "retorcerse" alrededor de la línea de base.[9]

## Referencias
[1] J. S. Steinberg, N. Varma, I. Cygankiewicz, P. Aziz, P. Balsam, A. Baranchuk, et al., “2017 ISHNE-HRS expert consensus statement on ambulatory ECG and external cardiac monitoring/telemetry,” Heart Rhythm, vol. 14, no. 7, pp. e55–e96, 2017. doi: 10.1016/j.hrthm.2017.03.038.

[2] J. A. Drezner et al., “International criteria for electrocardiographic interpretation in athletes: Consensus statement,” British Journal of Sports Medicine, vol. 51, no. 9, pp. 704–731, Mar. 2017, doi: 10.1136/bjsports-2016-097331.

[3] Pabitha P, Praveen R, Chandana KCJ, Ponlibarnaa S, Aparnaa AS. A comparative study of deep learning models for ECG signal-based user classification. En: 2023 12th International Conference on Advanced Computing (ICoAC). IEEE; 2023. p. 1–8.

[4] Ardeti VA, Kolluru VR, Varghese GT, Patjoshi RK. An overview on state-of-the-art electrocardiogram signal processing methods: Traditional to AI-based approaches. Expert Syst Appl [Internet]. 2023;217(119561):119561. Disponible en: http://dx.doi.org/10.1016/j.eswa.2023.119561

[5] Zavala-Villeda JA. Vectores cardíacos, derivaciones del plano frontal y horizontal, ondas, intervalos y segmentos en el electrocardiograma [Internet]. Medigraphic.com. [citado el 2 de mayo de 2026]. Disponible en: https://www.medigraphic.com/pdfs/rma/cma-2018/cmas181bi.pdf 

[6] Kania M, Rix H, Fereniec M, Zavala-Fernandez H, Janusek D, Mroczka T, et al. The effect of precordial lead displacement on ECG morphology. Med Biol Eng Comput [Internet]. 2014;52(2):109–19. Disponible en: http://dx.doi.org/10.1007/s11517-013-1115-9 

[7] Wong S, Cruz J, Gauvrit H, Hernández A, La Cruz A. No title [Internet]. Scielo.org. Los autores permiten el uso libre de sus publicaciones bajo la norma CC-BY; 2008 [citado el 2 de mayo de 2026]. Disponible en: https://ve.scielo.org/scielo.php?script=sci_arttext&pid=S1316-48212008000100002

[8] Harrison A, Wandall K, Thorball J. ECG movement artefacts can be greatly reduced with the aid of a movement absorbing device. Journal of Pre-Clinical and Clinical Research [Internet]. 2007 [citado el 2 de mayo de 2026];1:65–7. Disponible en: https://www.jpccr.eu/pdf-71235-8475?filename=ECG-movement-artefacts-ca.pdf

[9] Arrhythmias [Internet]. Zerotofinals.com. [citado el 2 de mayo de 2026]. Disponible en: https://zerotofinals.com/medicine/cardiology/arrhythmias/


