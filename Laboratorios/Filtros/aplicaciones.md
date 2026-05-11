# *Filtro Notch*

Un filtro Notch, en la cual es denominado también filtro de banda eliminada, es un sistema de procesamiento de señales diseñado para poder atenuar drásticamente la energía espectral en una frecuencia central f₀ predeterminada, junto a ello busca mantener que el resto del espectro tenga una mínima perturbación.

Desde la perspectiva de la teoría de sistemas LTI, el filtro Notch muestra una función de transferencia con un par de ceros conjugados especialmente sobre el círculo unitario del plano z (ROC), ubicados en la frecuencia de rechazo.

La función de transferencia general de un filtro Notch IIR de segundo orden en dominio z:
**H(z) = (1 − 2cos(ω₀)z⁻¹ + z⁻²) / (1 − 2r·cos(ω₀)z⁻¹ + r²·z⁻²)**

en la cual **ω₀ = 2π·f₀/fₛ** es la frecuencia angular normalizada de rechazo y r (0 < r < 1) es el radio del par de polos, cuyo acercamiento a la unidad determina el ancho de banda del filtro y, por ende, su factor de calidad Q. 

A medida que r → 1, el ancho de banda de rechazo decrece y Q aumenta, resultando en mayor selectividad espectral.[1]

Finalmente se tiene un factor de calidad se define como:
**Q = f₀ / BW₋₃dB**
donde BW₋₃dB es el ancho de banda medido a −3 dB de la atenuación máxima. En la mayoría de aplicaciones biomédicas se buscan valores de Q elevados (Q ≥ 30) para evitar la distorsión.[2]

## Aplicación en Electrografía (ECG)
El electrocardiograma muestra la actividad eléctrica cardíaca en la cual mediante electrodos superficiales se logra obtener dicha seña, presenta amplitudes en el rango de 0.1–5 mV y un ancho de banda diagnóstico de 0.05–150 Hz según el estándar AHA/ANSI. 
Lo cual se debe considerar lainterferencia PLI a 50/60 Hz, ya que esta se superpone directamente sobre componentes espectrales del complejo QRS, donde obteneremos que la energía del complejo se concentra entre 10 y 50 Hz, y puede enmascarar ondas de baja amplitud como la onda P (~0.1–0.2 mV) afectando la obtención de la data.[1]

## Aplicación en Electroencefalografía (EEG)
El electroencefalograma permite poder mostar los potenciales eléctricos generados por la actividad sináptica neuronal, captados mediante electrodos en el cuero cabelludo. La amplitud típica de las señales EEG se encuentran entre 10 y 100 μV, lo que representa entre 100 y 1000 veces menos que las señales ECG y EMG, enla cual al ser más pequeño puede ser  afectado por el entorno electromagnético del laboratorio.[2]
Se tienen unas bandas de frecuencia de interés en EEG, ya que cada una de ellas son más visibles en ciertos estudios, estas bandas son: delta (0.5–4 Hz), theta (4–8 Hz), alpha (8–13 Hz), beta (13–30 Hz) y gamma (>30 Hz). 
El ruido PLI a 60 Hz se solapa directamente con la banda gamma baja, cuya relevancia en el estudio de procesos cognitivos, integración sensoriomotora y aplicaciones de interfaz cerebro-computadora (BCI) son muy predominantes.[2]

## Aplicación en Electromiografía (EMG)
El electromiograma permite poder mostrar el potencial de acción de unidades motoras (MUAP, Motor Unit Action Potential) generados durante la contracción muscular. El espectro de la señal superficial de EMG es significativamente más amplio que el del ECG o el EEG, en la cual se tiene un rango de 20–500 Hz, con la mayor concentración de energía espectral entre 50 y 150 Hz según el tipo de músculo y la fuerza de contracción.[3]
Sin embargo, el que tengan una coincidencia directa entre el máximo espectral del sEMG y la frecuencia de la PLI que se encuentra entre 50 a 60 Hz, representa el mayor desafío en el diseño del filtro Notch para esta aplicación: un filtro de ancho de banda excesivo eliminaría información motora relevante, comprometiendo la extracción de parámetros como la frecuencia mediana (MF) y la frecuencia media (MPF),especialmente los que se encuentran enfocados para   estudios de fatiga muscular.[3]

## *Tabla comparativa*
 
| Modalidad | Rango espectral | Factor Q recomendado | Riesgo principal | Implementación recomendada |
|:---------:|:---------------:|:--------------------:|:----------------:|:--------------------------:|
| **ECG** | 0.05 – 150 Hz | 30 – 40 | Distorsión del complejo QRS | IIR biquad (2.° orden) |
| **EEG** | 0.5 – 100 Hz | 40 – 60 | Contaminación de banda gamma (> 30 Hz) | IIR junto con filtros sobre armónicos (100, 150 Hz) |
| **EMG** | 20 – 500 Hz | 50 – 80 | Sesgo en frecuencia mediana (fatiga) | IIR alta Q o filtro adaptativo (LMS/RLS) |
----
Actualmente también se han realizado una adopción de métodos de referencia de ruido (noise reference cancellation) especialmente como un complemento al filtrado Notch. En estos sistemas, un canal de referencia que se encuentra desconectado del paciente o también conectado a tierra, captura la PLI ambiental, la cual es sustraída adaptativamente de los canales biomédicos mediante un filtro de correlación cruzada,para así por reducir la dependencia de parámetros fijos del filtro Notch.[4],[6]

# *Filtro Pasabajos*

Este filtro es un sistema de procesamiento de señales que atenúa las componentes espectrales por encima de una frecuencia de corte fc en el que se mantienen las frecuencias inferiores sin alteración significativa [7].
En los sistemas LTI la función de transferencia de los filtros pasabajos IIR de segundo orden en el dominio z es:  

**H(z) = (1 − 2cos(ωc)z⁻¹ + z⁻²) / (1 − 2r·cos(ωc)z⁻¹ + r²·z⁻²)**

Los coeficientes a y b dependen de la frecuencia de corte (fc) normalizada así como del factor de amortiguamiento. La elección de fc determinará qué parte del espectro se conserva y la que se elimina [7].

## Aplicación en Electromiografía (EMG)
En el estudio de Vigotsky et al. (2018) se muestra que las señales EMG de superficie contienen información útil entre 20 y 500 Hz mientras que los componentes superiores a este rango corresponden mayormente a ruido eléctrico ambiental [8]. Por ello, se emplea un filtro pasabajos con corte en 500 Hz para conservar la actividad muscular y eliminar el ruido que no aporta información neuromuscular.

## Aplicación en Electrocardiografía (ECG)
Prasad et al. (2017) describen que las señales ECG poseen un ancho de banda diagnóstico entre 0.05 y 100 Hz y que las frecuencias superiores a este rango corresponden a ruido muscular torácico y a interferencias asociadas al movimiento [9]. El uso de un filtro pasabajos con corte en 100 Hz asegura la preservación de las ondas P, QRS y T mientras se atenúan las interferencias de alta frecuencia que podrían distorsionar la interpretación clínica.

## Aplicación en Electroencefalografía (EEG)
Sanei y Chambers (2017) explican que las señales EEG se analizan principalmente en el rango de 0.5 a 40 Hz, correspondiente a las bandas delta, theta, alfa y beta [7]. Las frecuencias superiores a 40 Hz suelen estar contaminadas por ruido muscular craneal y por interferencias electromagnéticas. Entonces el filtro pasabajos con corte en 40 Hz permitirá conservar las oscilaciones cerebrales relevantes así como la eliminación el ruido que compromete la calidad del registro.

En la siguiente tabla se resumen las principales características del filtro pasabajos aplicado a señales ECG, EEG y EMG en el que el mismo principio de filtrado se adapta a diferentes modalidades de registro.

| Modalidad | Rango espectral | Ruido eliminado | Riesgo principal | Implementación recomendada |
|:---------:|:---------------:|:--------------------:|:----------------:|:--------------------------:|
| ECG [9]| 0.05 – 100 Hz | Ruido muscular torácico, artefactos de movimiento, alta frecuencia | Atenuación de componentes de alta frecuencia del complejo QRS si el corte es demasiado bajo | Filtro IIR biquad de 2.º orden con corte en 100 Hz |
| EEG [7]| 0.5 – 40 Hz | Ruido muscular craneal e interferencia electromagnética | Pérdida de información en banda gamma (>30 Hz) si el corte es muy agresivo | Filtro IIR junto con técnicas de supresión adaptativa |
| EMG [8]| 20 – 500 Hz | Ruido eléctrico ambiental, interferencia de alta frecuencia | Sesgo en parámetros espectrales (frecuencia mediana, fatiga) si el corte es demasiado bajo | Filtro IIR alta selectividad o FIR con corte en 500 Hz |

Con ello, se puede ver que el filtro pasabajos no se aplica igual en todas las señales biomédicas. En EMG, por ejemplo, un corte en 500 Hz elimina interferencias sin comprometer los parámetros de fatiga, lo cual exige un rango bastante más amplio que en otras señales. En ECG basta con 100 Hz para preservar la morfología del complejo QRS, mientras que en EEG bajar el límite a 40 Hz reduce la contaminación por ruido muscular aunque se tiene el riesgo de afectar la banda gamma. En ese sentido, tanto la frecuencia de corte como la elección entre IIR y FIR no son arbitrarios, sino que dependen directamente de qué información se necesita conservar en cada caso.

# *Filtro Pasa Altas*

Un filtro pasa altas es un sistema de procesamiento de señales diseñado para atenuar las componentes espectrales por debajo de una frecuencia de corte \(f_c\), permitiendo el paso de las frecuencias superiores con una perturbación mínima. En el marco de los sistemas LTI, este tipo de filtro se utiliza ampliamente para eliminar deriva de línea base, desplazamientos lentos y artefactos de baja frecuencia en señales biomédicas [10].

La función de transferencia general de un filtro pasa altas IIR de segundo orden en el dominio \(z\) puede expresarse como:

**H(z) = (1 − 2z⁻¹cos(ωc) + z⁻²) / (1 − 2r·cos(ωc)z⁻¹ + r²z⁻²)**

donde \(ωc = 2π·fc/fs\) es la frecuencia angular normalizada de corte, \(fs\) es la frecuencia de muestreo y \(r\) \((0 < r < 1)\) controla la selectividad del filtro. 

## Aplicación en Electrocardiografía (ECG)

El electrocardiograma registra la actividad eléctrica cardíaca mediante electrodos superficiales y presenta amplitudes típicas en el rango de 0.1–5 mV. Su principal problema de baja frecuencia es la deriva de línea base, producida por respiración, movimiento y cambios de impedancia en los electrodos, la cual puede afectar la interpretación del segmento ST [10].

Por ello, suele emplearse un filtro pasa altas con frecuencia de corte baja, típicamente entre 0.05 y 0.5 Hz, para eliminar el desplazamiento lento sin distorsionar en exceso las ondas P, QRS y T. 

## Aplicación en Electroencefalografía (EEG)

El electroencefalograma mide la actividad eléctrica cerebral captada en el cuero cabelludo y presenta amplitudes mucho menores que el ECG, usualmente del orden de microvoltios. En EEG, las componentes de muy baja frecuencia pueden deberse a deriva instrumental, movimientos lentos, sudoración o cambios en la impedancia del electrodo [11].

En muchos análisis se utiliza un filtro pasa altas con corte alrededor de 0.1 Hz o 0.5 Hz para remover fluctuaciones lentas y conservar las bandas de interés como delta, theta, alpha, beta y gamma. No obstante, un corte demasiado agresivo puede distorsionar la actividad cerebral de baja frecuencia y afectar estudios de potenciales evocados o análisis conectivos.

## Aplicación en Electromiografía (EMG)

El electromiograma representa la actividad eléctrica muscular y, a diferencia del ECG y EEG, contiene información relevante en frecuencias más altas. En EMG superficial, los artefactos de movimiento y la contaminación de baja frecuencia pueden ser significativos, especialmente en registros durante contracción dinámica o en músculos del tronco [12][13].

Por esta razón, se emplean filtros pasa altas con frecuencias de corte frecuentemente situadas entre 10 y 30 Hz, e incluso mayores en algunos contextos, para reducir artefactos y mejorar el análisis de la señal. Aun así, elevar demasiado el corte puede atenuar componentes útiles y modificar parámetros como amplitud integrada o estimaciones de fuerza muscular.

## Tabla comparativa

| Modalidad | Rango espectral útil | Frecuencia de corte típica | Ruido eliminado | Riesgo principal | Implementación recomendada |
|:---------:|:--------------------:|:---------------------------:|:---------------:|:----------------:|:--------------------------:|
| ECG | 0.05 – 150 Hz | 0.05 – 0.5 Hz | Deriva de línea base, respiración, movimiento | Distorsión del ST si el corte es alto | IIR biquad o FIR de fase lineal |
| EEG | 0.1 – 100 Hz | 0.1 – 0.5 Hz | Deriva lenta, cambios de impedancia, artefactos instrumentales | Pérdida de componentes lentas relevantes | Filtro FIR suave o IIR de baja orden |
| EMG | 20 – 500 Hz | 10 – 30 Hz | Artefactos de movimiento y baja frecuencia | Atenuación de información muscular útil | IIR alta selectividad o FIR según la aplicación |

En general, el filtro pasa altas no se diseña igual para todas las señales biomédicas. En ECG se busca suprimir la deriva sin alterar la interpretación clínica; en EEG se preservan las oscilaciones lentas relevantes; y en EMG se prioriza la eliminación de artefactos de movimiento para conservar una señal apta para análisis muscular [10][12].

# *Filtro Pasa Bandas*

Un filtro pasa banda se define como un sistema lineal e invariante en el tiempo (LTI) que permite el paso de componentes de frecuencia dentro de un rango determinado (ω 
min <ω<ωmax) y atenúa las componentes fuera de este intervalo[14]. En el procesamiento digital, este comportamiento se logra mediante una función de transferencia H(z), que es la transformada z de la respuesta al impulso del sistema. Para un filtro de segundo orden, la expresión general en el dominio z es una función racional de polinomios.

$$H(z) = \frac{b_0 + b_1 z^{-1} + b_2 z^{-2}}{1 + a_1 z^{-1} + a_2 z^{-2}}$$

Un diseño específico para un filtro pasa banda de segundo orden consiste en colocar ceros en z=1 (frecuencia cero/DC) y z=−1 (frecuencia de Nyquist) para asegurar la atenuación en los extremos, y un par de polos complejos conjugados cerca del círculo unitario en la frecuencia central deseada. Por ejemplo, si se desea una frecuencia central en π/2 con un radio de polo r, la función se simplifica a:

$$H(z) = G \frac{1 - z^{-2}}{1 + r^2 z^{-2}}$$

Donde G es una constante de ganancia para normalizar la respuesta en la banda de paso
La aplicación de filtros pasa banda es crítica para "limpiar" señales biomédicas cuando el espectro del ruido no se traslapa con el de la señal deseada[b]. Los ruidos se categorizan según su origen y frecuencia:

- Interferencias de baja frecuencia:
Desplazamiento de la línea base (Baseline Wander): Causado por la respiración, ruidos químicos en la interfaz piel-electrodo y movimientos del cable. Generalmente ocurre por debajo de 0.5 - 1 Hz en ECG y EEG, pero puede ser inestable hasta los 20 Hz en EMG[16].
Artefactos de movimiento: Producidos cuando el músculo se mueve bajo la piel o por impulsos de fuerza en el sensor, concentrando su energía principalmente por debajo de los 20 Hz[16].

- Interferencias de alta frecuencia:
Ruido de línea eléctrica: Interferencia de 50/60 Hz y sus armónicos, captada capacitiva o inductivamente por el cuerpo y los cables[b].
Ruido Electromiográfico (EMG) en otras señales: En registros de ECG o EEG, la actividad de músculos esqueléticos cercanos actúa como ruido de banda ancha (hasta 500 Hz)[15]
Ruido electrónico: Ruido térmico intrínseco de los amplificadores y componentes del sistema[15]

## Aplicación en Electrocardiografía (ECG)

En el ECG, los filtros deben preservar la información entre 0.05 Hz y 100 Hz. El límite inferior es crítico para medir correctamente los desplazamientos lentos del segmento ST (indicadores de isquemia), mientras que el límite superior ayuda a definir el complejo QRS. En dispositivos como los marcapasos cardíacos, se emplea un filtro pasa banda con una frecuencia central de 30 Hz para la detección de ondas R (que operan entre 10-30 Hz). Este filtro permite que el circuito ignore señales lentas como las ondas T (≤ 5 Hz) y ruidos rápidos provenientes de músculos esqueléticos (10-200 Hz), evitando detecciones falsas o inhibiciones inapropiadas del dispositivo[15]

## Aplicación en Electroencefalografía (EEG)

Para el EEG, el filtrado se utiliza para aislar ritmos cerebrales específicos esenciales para el diagnóstico clínico, cuyo rango de interés oscila entre 0.5 Hz y 100 Hz. El filtrado pasa banda permite separar bandas como Delta (0.5–3.5 Hz), Theta (4–7 Hz), Alpha (8–13 Hz) y Beta (14–40 Hz). Este proceso es vital antes de la conversión analógico-digital para evitar el aliasing, asegurando que ruidos como el de la red eléctrica (50 Hz) no se repliquen dentro de las bandas de interés diagnóstico (como la banda Beta a 30 Hz)[15].

## Aplicación en Electromiografía (EMG)

En las señales de EMG de superficie (sEMG), el espectro útil se encuentra típicamente entre 10 Hz y 450 Hz. El filtrado pasa banda es crucial para mitigar los artefactos de movimiento que contaminan el extremo inferior del espectro. Investigaciones empíricas recomiendan un filtro Butterworth de segundo orden con una frecuencia de corte inferior de 20 Hz para uso general. Se desaconseja bajar de los 20 Hz porque la señal en ese rango es inestable debido a las tasas de disparo de las unidades motoras, y un filtro de 10 Hz suele ser insuficiente para eliminar los componentes espectrales del artefacto de movimiento[16].


## Tabla comparativa

| Modalidad | Rango espectral útil | Ruido eliminado | Riesgo principal | Implementación recomendada |
|:---------:|:--------------------:|:---------------:|:----------------:|:--------------------------:|
| ECG[15] | 0.05 Hz – 100 Hz | Desplazamiento de línea base (respiración) y ruido muscular (10-200 Hz) | Distorsión del segmento ST (isquemia) o errores en la definición del complejo QRS | Filtro centrado en 30 Hz para detección de ondas R en marcapasos; Butterworth para diagnóstico |
| EEG[15] | 0.5 Hz – 100 Hz | Artefactos oculares, movimientos lentos y ruido de red eléctrica (50 Hz) para evitar aliasing | Mezcla de ruidos en bandas Delta, Theta, Alpha y Beta, invalidando el análisis clínico | Filtros para bandas específicas, aplicación obligatoria previa a la conversión ADC |
| EMG[16] | 20 Hz – 450 Hz | Artefactos de movimiento ($< 20$ Hz) e inestabilidad por tasas de disparo de unidades motoras | Señal inestable y contaminación por artefactos de movimiento si el corte es inferior a 20 Hz | Filtro Butterworth de 2.° orden con frecuencia de corte inferior fija en 20 Hz |

# *Filtro Wavelet*
El filtrado mediante la Transformada Wavelet (WT) es una técnica de procesamiento de señales que, a diferencia de la Transformada de Fourier, permite una localización simultánea en el tiempo y la frecuencia. Este sistema es especialmente eficaz para señales no estacionarias, donde se busca eliminar componentes de ruido (denoising) preservando transitorios rápidos y discontinuidades que contienen información clínica relevante [17].

Desde la perspectiva del análisis multirresolución, el filtro Wavelet descompone la señal original en diferentes niveles de aproximación (bajas frecuencias) y detalles (altas frecuencias) mediante un par de filtros: un filtro paso-bajo g[n] y un filtro paso-alto h[n] [18]. La relación matemática de la descomposición se define como:

**$$y_{low}[k] = \sum_{n} x[n] \cdot g[2k - n]$$**

**$$y_{high}[k] = \sum_{n} x[n] \cdot h[2k - n]$$**

La función básica de una wavelet hija se define matemáticamente como:

**$$\psi_{a,b}(t) = \frac{1}{\sqrt{a}} \psi \left( \frac{t-b}{a} \right)$$**

donde $a$ representa la escala (frecuencia) y $b$ la traslación (tiempo) [17].


El proceso de filtrado o "Thresholding" consiste en descomponer la señal, aplicar un umbral $\lambda$ a los coeficientes de detalle para eliminar el ruido y, finalmente, reconstruir la señal mediante la Transformada Wavelet Discreta Inversa (IDWT). La selección de la Wavelet madre (p. ej., Daubechies, Symlet, Coiflet) y el tipo de umbralización (Hard o Soft thresholding) determina la fidelidad de la señal filtrada [17].


## Aplicación en Electromiografía (EMG)

En el EMG, el filtrado Wavelet se utiliza principalmente para el denoising de ruido blanco gaussiano y la separación de señales de diferentes unidades motoras. Debido a que el espectro del EMG es amplio (20–500 Hz), el ruido se solapa en toda la banda. El uso de Wavelets como Daubechies o Meyer permite una separación superior en el dominio tiempo-frecuencia. Esto es vital para calcular la conducción muscular sin el sesgo introducido por el ruido de instrumentación, permitiendo un análisis más preciso de la fatiga muscular y la sincronización de fibras durante contracciones de alta intensidad [19] [20].


## Aplicación en Electrocardiografía (ECG)

En el ECG, el desafío principal tras eliminar la interferencia de línea es la corrección de la deriva de línea base provocada por la respiración y el movimiento del paciente (< 0.5 Hz). Dado que el complejo QRS tiene componentes de alta frecuencia, un filtro de Fourier convencional podría deformar los segmentos ST. La DWT permite aislar la deriva de línea base en los niveles de aproximación más altos (bajas frecuencias) y removerlos sin afectar la morfología del complejo QRS. Se suelen utilizar Wavelets de la familia Daubechies debido a su similitud morfológica con el complejo cardiaco, optimizando la detección de picos R incluso en entornos ruidosos [17] [21] [22].


## Aplicación en Electroencefalografía (EEG)

Las señales EEG son extremadamente sensibles a artefactos no biológicos y biológicos (parpadeo ocular, actividad muscular). El filtrado Wavelet es la herramienta estándar para la eliminación de artefactos oculares, que suelen concentrarse en frecuencias bajas (1–4 Hz) pero ocurren de forma transitoria. Mediante la descomposición multirresolución, es posible identificar los coeficientes que corresponden al parpadeo en las bandas delta y eliminarlos selectivamente. Para EEG, se prefieren las Symlets por su simetría casi perfecta, lo que reduce la distorsión de fase en las ondas cerebrales gamma y beta [7] [23].


## Tabla comparativa

| Modalidad | Rango espectral | Ruido eliminado | Riesgo principal | Implementación recomendada |
|:---------:|:---------------:|:--------------------:|:----------------:|:--------------------------:|
| ECG | 0.05 – 150 Hz | Deriva de línea base y ruido muscular | Suavizado de la onda R (pérdida de amplitud) | DWT con Wavelet Daubechies |
| EEG | 0.5 – 100 Hz | Artefactos oculares y parpadeo | Eliminación accidental de ondas delta/theta | Wavelet Transform con Symlets |
| EMG | 20 – 500 Hz | Ruido blanco y solapamiento muscular | Artefactos de Gibbs en la reconstrucción | Wavelet Packet Transform (WPT) con Symlets |



## Referencias
 
> [1] S. Kumar y R. K. Saini, "Design and Analysis of Digital Notch Filter for Power Line Interference Removal from ECG Signal," *Int. J. Adv. Res. Electr. Electron. Instrum. Eng.*, vol. 10, no. 3, pp. 1452–1461, mar. 2021.

> [2] S. Anumela *et al.*, "Denoising and Artifact Removal Techniques in EEG Signals for BCI Applications: A Survey," *Front. Hum. Neurosci.*, vol. 16, art. 873476, jun. 2022, doi: [10.3389/fnhum.2022.873476](https://doi.org/10.3389/fnhum.2022.873476).

> [3] A. Choudhary y R. Gupta, "A Comprehensive Review on EMG Signal Preprocessing and Artifact Removal Techniques," *J. Biomed. Eng. Med. Imaging*, vol. 9, no. 2, pp. 24–41, abr. 2022.

> [4] P. Sharma y A. K. Sharma, "Adaptive Notch Filter for Power Line Interference Removal in Biomedical Signals," *IEEE Trans. Biomed. Eng.*, vol. 70, no. 4, pp. 1234–1243, 2023.

> [5] P. Laguna, R. Jané y P. Caminal, "Adaptive filtering of ECG baseline wander," in *Proc. IEEE EMBC*, 2021, pp. 3891–3895, doi: [10.1109/EMBC.2021.9629642](https://doi.org/10.1109/EMBC.2021.9629642).

> [6] G. Mihajlović, V. Pejanović-Đurišić y S. Savić, "Digital Signal Processing Algorithms for Power Line Interference Suppression in Biomedical Acquisition Systems," *Biomed. Signal Process. Control*, vol. 78, art. 103975, sep. 2022, doi: [10.1016/j.bspc.2022.103975](https://doi.org/10.1016/j.bspc.2022.103975).

> [7] S. Sanei and J. A. Chambers, EEG Signal Processing, 2nd ed., Wiley, 2017, ch. 2, sec. 2.8, pp. 79–83.
 
> [8] A. D. Vigotsky, I. Halperin, G. J. Lehman, G. S. Trajano, and T. M. Vieira, "Interpreting Signal Amplitudes in Surface Electromyography Studies in Sport and Rehabilitation Sciences," Front. Physiol., vol. 8, p. 985, Jan. 2018, doi: 10.3389/fphys.2017.00985.
  
> [9] S. Asgari and A. Mehrnia, “A novel low-complexity digital filter design for wearable ECG devices,” PLOS ONE, vol. 12, no. 4, p. e0175139, Apr. 2017, doi: 10.1371/journal.pone.0175139.
‌
> [10] P. Laguna, R. Jané y P. Caminal, “Adaptive filtering of ECG baseline wander,” *Proc. IEEE EMBC*, 2021.  doi:[10.1109/EMBC.2021.9629642]

> [11] S. Sanei y J. A. Chambers, *EEG Signal Processing*, 2nd ed., Wiley, 2017.  
doi:[10.1002/9781119386957]

> [12] A. D. Vigotsky et al., “Interpreting Signal Amplitudes in Surface Electromyography Studies in Sport and Rehabilitation Sciences,” *Frontiers in Physiology*, 2018.  
doi:[10.3389/fphys.2017.00985]

> [13] A. Choudhary y R. Gupta, “A Comprehensive Review on EMG Signal Preprocessing and Artifact Removal Techniques,” *Journal of Biomedical Engineering and Medical Imaging*, 2022. 
https://www.sciencedirect.com/science/article/abs/pii/S1050641120300821

> [14] J. Proakis and D. Manolakis, “DIGITAL SIGNAL PROCESSING Principles, Algorithms, m l Applications.” [Online]. Available: https://uvceee.wordpress.com/wp-content/uploads/2016/09/digital_signal_processing_principles_algorithms_and_applications_third_edition.pdf

> [15] M. E. Valentinuzzi, “Bioelectrical signal processing in cardiac and neurological applications and electromyography: physiology, engineering, and noninvasive applications,” BioMedical Engineering OnLine, vol. 6, no. 1, p. 27, 2007, doi: 10.1186/1475-925x-6-27.

> [16]  C. J. De Luca, L. Donald Gilmore, M. Kuznetsov, and S. H. Roy, “Filtering the surface EMG signal: Movement artifact and baseline noise contamination,” Journal of Biomechanics, vol. 43, no. 8, pp. 1573–1579, May 2010, doi: 10.1016/j.jbiomech.2010.01.027.

> [17] P. S. Addison, The illustrated Wavelet Transform Handbook. 2017. doi: 10.1201/9781315372556.

> [18] J. Too, A. R. Abdullah, N. M. Saad, N. M. Ali, and H. Musa, “A detail study of Wavelet families for EMG pattern recognition,” International Journal of Electrical and Computer Engineering (IJECE), vol. 8, no. 6, p. 4221, Dec. 2018, doi: 10.11591/ijece.v8i6.pp4221-4229.

> [19] A. Phinyomark, P. Phukpattaranont, and C. Limsakul, “WAVELET-BASED DENOISING ALGORITHM FOR ROBUST EMG PATTERN RECOGNITION,” Fluctuation and Noise Letters, vol. 10, no. 02, pp. 157–167, Dec. 2010, doi: 10.1142/s0219477511000466.

> [20] C. Ouyang, L. Cai, B. Liu, and T. Zhang, “An improved wavelet threshold denoising approach for surface electromyography signal,” EURASIP Journal on Advances in Signal Processing, vol. 2023, no. 1, Oct. 2023, doi: 10.1186/s13634-023-01066-3.

> [21] “A wavelet based technique for suppression of EMG noise and motion artifact in ambulatory ECG,” IEEE Conference Publication | IEEE Xplore, Aug. 01, 2011. https://ieeexplore.ieee.org/document/6091791

> [22] Z. Wang, J. Zhu, T. Yan, and L. Yang, “A new modified wavelet-based ECG denoising,” Computer Assisted Surgery, vol. 24, no. sup1, pp. 174–183, Jan. 2019, doi: 10.1080/24699322.2018.1560088.

> [23] D. J. M. Elena, “Procesamiento de señales de electroencefalograma mediante wavelets para la eliminación de artefactos cardíacos  | Archivo Digital UPM.” https://oa.upm.es/71888/



 
