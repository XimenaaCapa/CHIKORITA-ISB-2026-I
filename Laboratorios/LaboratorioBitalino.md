# Laboratorio Bitalino
## Introducción
En este laboratorio estamos desarrollando la adquisición de la señal EMG, en la cual este tipo de señal esta enfocado en poder obtener la diferencia de actividad eléctrica de la contracción muscular. Para ello evaluaremos...

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


### 3. Colocación de los electrodos en el Bícep
Para poder realizar la medición de la señal basal se seguira la sigueinte colocación de electrodos: 
<img width="889" height="451" alt="image" src="https://github.com/user-attachments/assets/f701451d-2065-4e0b-b78c-9325e328ffd1" />
Figura 1. Extraido de “Electromyography (EMG) Sensor User Manual.” [Online]. Available: https://support.pluxbiosignals.com/wp-content/uploads/2021/11/electromyography-emg-user-manual.pdf
‌#
En la que se deben colocar siguiendo un espaciado de 2 cm entre electrodos.
Se utilizan los electrodos negros y rojos para la toma de datos y el electrodo blanco como punto neutro.


### 4. Protocolo de adquisición de datos
	4.1. Registro de línea base de (30 segundos) 
	4.2. CONTRACCIÓN-REPOSO-RELAJACIÓN por 5 ciclos: Contracción durante 2 segundos y el reposo durante 2 segundos donde las contracciones se ejecutaron de menor a mayor intensidad, siendo la última correspondiente a la contracción voluntaria máxima (CVM).
	4.3. Registro de segunda línea base de (30 segundos) .
	4.4. Activaciones cortas consecutivas (1 segundo cada una) seguidas de una contracción sostenida de 10 segundos.


 ### 5. Vistas de la adquisición

### 
## Discusión

## Referencias
