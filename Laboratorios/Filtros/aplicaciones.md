## *Filtro Notch*
Un filtro Notch, en la cual es denominado también filtro de banda eliminada, es un sistema de procesamiento de señales diseñado para poder atenuar drásticamente la energía espectral en una frecuencia central f₀ predeterminada, junto a ello busca mantener que el resto del espectro tenga una mínima perturbación.
Desde la perspectiva de la teoría de sistemas LTI, el filtro Notch muestra una función de transferencia con un par de ceros conjugados especialmente sobre el círculo unitario del plano z (ROC), ubicados en la frecuencia de rechazo.
La función de transferencia general de un filtro Notch IIR de segundo orden en dominio z:
H(z) = (1 − 2cos(ω₀)z⁻¹ + z⁻²) / (1 − 2r·cos(ω₀)z⁻¹ + r²·z⁻²)
en la cual ω₀ = 2π·f₀/fₛ es la frecuencia angular normalizada de rechazo y r (0 < r < 1) es el radio del par de polos, cuyo acercamiento a la unidad determina el ancho de banda del filtro y, por ende, su factor de calidad Q. 
A medida que r → 1, el ancho de banda de rechazo decrece y Q aumenta, resultando en mayor selectividad espectral.[1]
El factor de calidad se define como: Q = f₀ / BW₋₃dB
donde BW₋₃dB es el ancho de banda medido a −3 dB de la atenuación máxima. En la mayoría de aplicaciones biomédicas se buscan valores de Q elevados (Q ≥ 30) para evitar la distorsión.[2]
----
## Aplicación en Electrografía (ECG)
El electrocardiograma muestra la actividad eléctrica cardíaca en la cual mediante electrodos superficiales se logra obtener dicha seña, presenta amplitudes en el rango de 0.1–5 mV y un ancho de banda diagnóstico de 0.05–150 Hz según el estándar AHA/ANSI. 
Lo cual se debe considerar lainterferencia PLI a 50/60 Hz, ya que esta se superpone directamente sobre componentes espectrales del complejo QRS, donde obteneremos que la energía del complejo se concentra entre 10 y 50 Hz, y puede enmascarar ondas de baja amplitud como la onda P (~0.1–0.2 mV) afectando la obtención de la data.[1]
----
## Aplicación en Electroencefalografía (EEG)
El electroencefalograma permite poder mostar los potenciales eléctricos generados por la actividad sináptica neuronal, captados mediante electrodos en el cuero cabelludo. La amplitud típica de las señales EEG se encuentran entre 10 y 100 μV, lo que representa entre 100 y 1000 veces menos que las señales ECG y EMG, enla cual al ser más pequeño puede ser  afectado por el entorno electromagnético del laboratorio.[2]
Se tienen unas bandas de frecuencia de interés en EEG, ya que cada una de ellas son más visibles en ciertos estudios, estas bandas son: delta (0.5–4 Hz), theta (4–8 Hz), alpha (8–13 Hz), beta (13–30 Hz) y gamma (>30 Hz). 
El ruido PLI a 60 Hz se solapa directamente con la banda gamma baja, cuya relevancia en el estudio de procesos cognitivos, integración sensoriomotora y aplicaciones de interfaz cerebro-computadora (BCI) son muy predominantes.[2]
----
## Aplicación en Electromiografía (EMG)
El electromiograma permite poder mostrar el potencial de acción de unidades motoras (MUAP, Motor Unit Action Potential) generados durante la contracción muscular. El espectro de la señal superficial de EMG es significativamente más amplio que el del ECG o el EEG, en la cual se tiene un rango de 20–500 Hz, con la mayor concentración de energía espectral entre 50 y 150 Hz según el tipo de músculo y la fuerza de contracción.[3]
Sin embargo, el que tengan una coincidencia directa entre el máximo espectral del sEMG y la frecuencia de la PLI que se encuentra entre 50 a 60 Hz, representa el mayor desafío en el diseño del filtro Notch para esta aplicación: un filtro de ancho de banda excesivo eliminaría información motora relevante, comprometiendo la extracción de parámetros como la frecuencia mediana (MF) y la frecuencia media (MPF),especialmente los que se encuentran enfocados para   estudios de fatiga muscular.[3]
----

## *Tabla comparativa*
 
| Modalidad | Rango espectral | Factor Q recomendado | Riesgo principal | Implementación recomendada |
|:---------:|:---------------:|:--------------------:|:----------------:|:--------------------------:|
| **ECG** | 0.05 – 150 Hz | 30 – 40 | Distorsión del complejo QRS | IIR biquad (2.° orden) |
| **EEG** | 0.5 – 100 Hz | 40 – 60 | Contaminación de banda gamma (> 30 Hz) | IIR junto con filtros sobre armónicos (100, 150 Hz) |
| **EMG** | 20 – 500 Hz | 50 – 80 | Sesgo en frecuencia mediana (fatiga) | IIR alta Q o filtro adaptativo (LMS/RLS) |
----
Actualmente también se han realizado una adopción de métodos de referencia de ruido (noise reference cancellation) especialmente como un complemento al filtrado Notch. En estos sistemas, un canal de referencia que se encuentra desconectado del paciente o también conectado a tierra, captura la PLI ambiental, la cual es sustraída adaptativamente de los canales biomédicos mediante un filtro de correlación cruzada,para así por reducir la dependencia de parámetros fijos del filtro Notch.[4],[6]
----
## Referencias
 
> [1] S. Kumar y R. K. Saini, "Design and Analysis of Digital Notch Filter for Power Line Interference Removal from ECG Signal," *Int. J. Adv. Res. Electr. Electron. Instrum. Eng.*, vol. 10, no. 3, pp. 1452–1461, mar. 2021.
> [2] S. Anumela *et al.*, "Denoising and Artifact Removal Techniques in EEG Signals for BCI Applications: A Survey," *Front. Hum. Neurosci.*, vol. 16, art. 873476, jun. 2022, doi: [10.3389/fnhum.2022.873476](https://doi.org/10.3389/fnhum.2022.873476). 
> [3] A. Choudhary y R. Gupta, "A Comprehensive Review on EMG Signal Preprocessing and Artifact Removal Techniques," *J. Biomed. Eng. Med. Imaging*, vol. 9, no. 2, pp. 24–41, abr. 2022.
> [4] P. Sharma y A. K. Sharma, "Adaptive Notch Filter for Power Line Interference Removal in Biomedical Signals," *IEEE Trans. Biomed. Eng.*, vol. 70, no. 4, pp. 1234–1243, 2023. 
> [5] P. Laguna, R. Jané y P. Caminal, "Adaptive filtering of ECG baseline wander," in *Proc. IEEE EMBC*, 2021, pp. 3891–3895, doi: [10.1109/EMBC.2021.9629642](https://doi.org/10.1109/EMBC.2021.9629642). 
> [6] G. Mihajlović, V. Pejanović-Đurišić y S. Savić, "Digital Signal Processing Algorithms for Power Line Interference Suppression in Biomedical Acquisition Systems," *Biomed. Signal Process. Control*, vol. 78, art. 103975, sep. 2022, doi: [10.1016/j.bspc.2022.103975](https://doi.org/10.1016/j.bspc.2022.103975).
 
 
