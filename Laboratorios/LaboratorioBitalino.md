# Laboratorio Bitalino
## Introducción
La electromiografía de superficie (sEMG) es una técnica que se utiliza para registrar la actividad eléctrica de los músculos con aplicaciones en biomecánica, rehabilitación y ciencias del deporte [1].  

Se analizan músculos de miembro superior como flexores y extensores del antebrazo, bíceps braquial, tríceps, deltoides y de miembro inferior cuádriceps, bíceps femoral, gastrocnemio, tibial anterior, esto por su relevancia en el control motor y la locomoción [2].  

En este laboratorio estamos desarrollando la adquisición de la señal EMG para poder obtener la diferencia de actividad eléctrica de la contracción muscular. Para ello evaluaremos dos músculos: el bíceps braquial y el trapecio superior. Ya que permiten estudiar la interacción entre acciones de fuerza (flexión del codo) y soporte postural (estabilización escapular) con aplicaciones en rehabilitación, ergonomía y en entrenamiento deportivo.


## Metodología
### Para la correcta extracción de datos EMG se trabajará con los siguientes materiales
| Equipo | Cantidad |
| :--- | :--- |
| Kit Bitalino | 1 |
| Cables y electrodos | 3 |
| Laptop | 1 |
| Sofware OpenSignals | 1 |

### 1. Conexión del set Bitalino inicial
 Se debe comenzar por conectar la bateria y encender el equipo
<img width="800" height="600" alt="WhatsApp Image 2026-04-17 at 11 45 46 AM" src="https://github.com/user-attachments/assets/e99b6cd6-2e6c-4c5a-a762-84a2a63b6a8a" />

### 2. Conexión Bitalino al sofware
Como primer paso, se tuvo que conectar mediante bluetooth el dispositivo de adquisición con la computadora. Luego se trabajará con la señal mediante la librería **opensignalsreader** en google collab.
<img width="600" height="620" alt="070ccfe7-4b9a-42ce-9f4c-23cedaa503a5" src="https://github.com/user-attachments/assets/0e81f1aa-a369-4c77-8aaf-84574d1ae9cd" />


### 3. Colocación de electrodos 
Se utiliza el electrodo negro (-)  y rojo (+) para la toma de datos y el electrodo blanco como punto neutro. Se deben colocar siguiendo un espaciado de 2 cm entre electrodos. Para poder realizar la medición de la señal basal se seguira la sigueinte colocación de electrodos: 
## 3.1. Para Bícep
<img width="889" height="451" alt="image" src="https://github.com/user-attachments/assets/f701451d-2065-4e0b-b78c-9325e328ffd1" />
Figura 1. Extraido de “Electromyography (EMG) Sensor User Manual.” [Online]. Available: https://support.pluxbiosignals.com/wp-content/uploads/2021/11/electromyography-emg-user-manual.pdf  

## 3.2. Para Trapecio 
Para poder realizar la medición de la señal basal se seguira la sigueinte colocación de electrodos:
<img width="1196" height="572" alt="image" src="https://github.com/user-attachments/assets/501d99e9-321e-474b-86be-2b7ba73a0a77" />
Figura 2. Extraido de “Electromyography (EMG) Sensor User Manual.” [Online]. Available: https://support.pluxbiosignals.com/wp-content/uploads/2021/11/electromyography-emg-user-manual.pdf  

### 4. Protocolo de adquisición de datos
	4.1. Registro de línea base de 1-2 minutos
	4.2. CONTRACCIÓN-REPOSO-RELAJACIÓN por 5 ciclos: Contracción durante 2 segundos y el reposo durante 2 segundos donde las contracciones se ejecutaron de menor a mayor intensidad, siendo la última correspondiente a la contracción voluntaria máxima (CVM).
	4.3. Registro de segunda línea base de (30 segundos) .
	4.4. Activaciones cortas consecutivas (1 segundo cada una) seguidas de una contracción sostenida de 10 segundos.


 ### 5. Vistas de la adquisición
## 5.1 Para Bícep
#### Fotos
 | Contracción | Relajado |
| :--- | :--- |
| <img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/854db418-5470-41e7-9316-9cf573220d80" />| <img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/417a00a7-e9da-499d-8aae-50103032ccb9" />|

### Video de señal en silencio eléctrico
https://github.com/user-attachments/assets/612360ec-0471-4bf2-b93e-1fe529e0300d

## 5.2 Para Trapecio
#### Fotos
 | Contracción | Relajado |
| :--- | :--- |
|<img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/a3829520-93e5-459f-8547-2e6dcaad9af7" />|<img width="300" height="400" alt="image" src="https://github.com/user-attachments/assets/097cdd9c-be79-4059-b7dc-68c881965125" />
 |

### Video de señal en silencio eléctrico

https://github.com/user-attachments/assets/5c05c44d-91cb-4399-95c0-297dd0a56908


 ### 6. Plot de graficas
### 6.1 Estado basal del músculo bíceps
<img width="1026" height="625" alt="descarga1" src="https://github.com/user-attachments/assets/0e56ecaf-8d63-4b56-9e6f-707cd5f0b790" />


### 6.2 Estado de contracción del músculo bíceps

### 6.3 Estado basal del músculo trapecio

### 6.4 Estado de contracción del músculo trapecio


### 


## Discusión


### **¿Cuáles son las frecuencias significativas para las adquisiciones de EMG? ¿Son las mismas en todas las áreas del cuerpo, como el área facial?**

La frecuencia espectral de la señal EMG oscila principalmente entre 25 y 250 Hz. Para poder capturar estas frecuencias sin pérdida de información, lo que se recomienda, es poder emplear una frecuencia de muestreo de al menos 500 Hz, lo cual nos permite usar una frecuencia de sampleo de 1000 Hz para cumplir con los criterios técnicos de reconstrucción de señal (criterio de Nyquist).[2]
Por otro lado, no son las mismas frecuencias de muestra para todas las áreas Es por ello que la señal EMG depende intrínsecamente de factores anatómicos y fisiológicos específicos de cada músculo.En el caso de los músculos faciales, aunque el espectro general se mantiene en el rango bajo los 500 Hz, la mayoría de estas áreas cuentan con unidades motoras (MUs) en las cuales son más pequeñas y una densidad de inervación distinta a las otras áreas.[1]

### **¿Qué tipo de filtro es esencial al trabajar con señales de EMG? ¿Por qué necesitamos aplicar dicho filtro?**
Se recomienda primero usar un filtro paso alto con un corte entre 0.5 y 20 Hz (o hasta 20 Hz para eliminar de forma efectiva el "baseline wander"), ya que nos permite poder eliminar el ruido de movimiento causados por los movimientos de los cables o electrodos, y también el poder suprimir componentes de baja frecuencia que no son de origen muscular.[2]
Luego, se aplica como filtro anti-aliasing antes de la digitalización. Junto a ello en la parte del  post-procesamiento, se usa un filtro paso-bajo después de rectificar la señal, lo que ya nos permite estudiar la intensidad y el tiempo de activación.Finalmente, para suprimir interferencias, se aplica un filtro de muesca (Notch) para la red eléctrica y técnicas de eliminación de ECG específicas según la zona de análisis, como el Gating o el Wavelet denoising [2]. En las cuales dichas técnicas son esenciales porque el ruido cardíaco (ondas P-Q)  pueden sobrepasar la potencia de la señal EMG por órdenes de magnitud.[2]

### **¿Cómo varía la amplitud en cada contracción muscular? ¿Hay diferencia según la ubicación en el cuerpo?**
Ambos músculos generan distintas amplitudes en estado basal, el bíceps de 0.1 mV y el trapecio superior de 0.4 mV, incrementándose en la contracción, llegando a 1.5 mV (el bíceps aumenta más de estado basal a contracción) en el primer minuto y en el caso del bíceps a 1 mV  en el segundo minuto. En esta fase podemos ver que las señales difieren en las frecuencias, basándonos en sus espectros de frecuencia, el bíceps tiene más frecuencias altas, con una frecuencia media de 64.9 Hz, mientras que el trapecio una de 60 Hz. Asimismo podemos ver que el bíceps tiene menor ruido de fondo en reposo. Podemos considerar que en el hombro se cuentan con músculos adyacentes al trapecio superior que podrían generar interferencia. Además de ello el trapecio superior sostiene activamente la cabeza y escápula por lo que no está en reposo como tal, a diferencia del bíceps, que al apoyarse se puede relajar.

### **¿La señal corresponde a lo esperado?**
SÍ, ya que se realizó movimientos circulares hacia atrás con los hombros, con lo que se esperaba que al elevar el hombro haya mayor activación que al bajarlo, esto concuerda con las variaciones de amplitud obtenidas.

### **¿Equivale la amplitud de la EMG a la cantidad de fuerza que has generado con tu músculo?**
No, la amplitud de la señal EMG no es igual a la cantidad de fuerza generada por el músculo, a pesar de que existe una correlación clara entre ambas, no existe una ecuación exacta que describe esta relación de forma directa, ya que es un proceso no lineal que depende de muchos factores.[1]
Es por ello que al momento de análisis se debe tener en cuenta el tipo de contracción. Por ejemplo, en las contracciones excéntricas se puede producir una fuerza mecánica muy alta con una amplitud de EMG baja, mientras que en las concéntricas se necesita mucha más activación neural, en la cual poseen una mayor amplitud para generar la misma cantidad de fuerza.[1]
Luego, influyen factores mecánicos esenciales como la longitud de la fibra muscular y la velocidad de contracción. Esto significa que un mismo nivel de amplitud EMG puede resultar en diferentes niveles de fuerza dependiendo de la posición de la articulación o de qué tan rápido se esté moviendo el músculo en ese momento.Por último, los factores externos como el tejido graso subcutáneo o la fatiga muscular afectan la amplitud detectada.[2]

## Referencias
* [1] A. D. Vigotsky, I. Halperin, G. J. Lehman, G. S. Trajano, and T. M. Vieira, “Interpreting Signal Amplitudes in Surface Electromyography Studies in Sport and Rehabilitation Sciences,” Frontiers in Physiology, vol. 8, Jan. 2018, doi: 10.3389/fphys.2017.00985.
* [2] V. ALCAN and M. ZİNNUROĞLU, “Current developments in surface electromyography,” Turkish Journal of Medical Sciences, vol. 53, no. 5, pp. 1019–1031, Oct. 2023, doi: 10.55730/1300-0144.5667.
‌
* [1]Romero Avila E, Williams SE, Disselhorst-Klug C. Advances in EMG measurement techniques, analysis procedures, and the impact of muscle mechanics on future requirements for the methodology. Journal of Biomechanics. 2023;156:111687.
* [2] Jonkman AH, Warnaar RSP, Baccinelli W, Carbon NM, D’Cruz RF, Doorduin J, et al. Analysis and applications of respiratory surface EMG: report of a round table meeting. Critical Care. 2024;28(2):1-17.
