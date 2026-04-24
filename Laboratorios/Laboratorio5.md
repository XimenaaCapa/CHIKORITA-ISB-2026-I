# Laboratorio Electrocarfiografía (ECG)
## Introducción

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

## Discusión
Q1. ¿Cuáles son los tipos más comunes de fuentes de ruido que afectan al ECG?

Q2. ¿Por qué el cambio en la posición de los sensores (derivaciones I-III) modifica los componentes de la señal ECG? ¿Cómo cambian estos componentes?

Q3. Describe si existen diferencias importantes en la señal al adquirirla desde distintas ubicaciones del cuerpo (por ejemplo: muñeca / clavícula / pecho). ¿Cuál podría ser la causa? ¿Esperabas estos cambios en la señal? Guarda un segmento de señal de cada caso para visualizar las diferencias.

Q4. Se sabe que los sistemas cardíaco y respiratorio están estrechamente relacionados. ¿Esperas que diferentes tipos de respiración (por ejemplo, más rápida o más profunda) influyan en las señales de ECG? Muestra capturas de señales de ECG en distintas condiciones respiratorias y describe las variaciones, si las hay.

Q5. En el Home-Guide #1 viste que diferentes niveles de fuerza muscular generan señales con distintas amplitudes. ¿Cómo influye el movimiento en tu señal de ECG?

Q6. Según tu conocimiento, ¿cómo puedes detectar bradicardia y taquicardia en la señal de ECG?

## Referencias

