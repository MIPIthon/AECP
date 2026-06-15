<h1>AECP (Analog Eddy Current Pickup)</h1>
Analog Eddy Current Pickup (AECP) is an analog eddy current signal conditioner circuit based on synchronous rectification of the amplitude of an LC tank circuit at resonance frequency. The circuit can be used to measure e.g. relative movement of a conductive or magnetic permeable object.

<h2>PCBA (Printed Circuit Board Assembly) </h2>

![AECP_A_PCB_TOP](/AECP_A/documentation/images/pcba_top_small.jpg)

![AECP_A_PCB_BOTTOM](/AECP_A/documentation/images/pcba_bottom_small.jpg)

<h2>Known issues</h2>
- INA188 zero-drift chopper amplifier: Internal chopper (zero drift) is unnecessary and detrimental to the output noise of the circuit due to beat-frequencies generated caused by the chopper frequencies and the frequency content of the square wave synchronous rectifier. 


Potential fix: Replace INA188 with INA828 (no chopper). If the common-mode voltage is approximately VCM=2.5V, the LT1167 is a suitable alternative (e.g. if the the RX part of the circuit is not directly connected to TXI and TXO (VCM=2.5V))


  FFT average: ACOUT, NoTarget, INA disconnected => White noise
  <img width="1151" height="637" alt="grafik" src="https://github.com/user-attachments/assets/31d0da18-3eeb-4da2-937e-f70c59ac9aa4" />
  
  FFT average: ACOUT and TP6,  NoTarget, INA connected => White noise + beat frequency
  <img width="1287" height="725" alt="grafik" src="https://github.com/user-attachments/assets/edfff3f9-5ea4-4853-9830-5e707f126092" />
  
  FFT average: TXI, NoTarget => Very low distortion
  <img width="1072" height="595" alt="grafik" src="https://github.com/user-attachments/assets/eadc42a3-d369-4f35-a0e0-d25f3f39fb67" />
  
  Time domain: TP6 => Distortion
  <img width="1296" height="725" alt="grafik" src="https://github.com/user-attachments/assets/b6596320-cca7-4906-8a33-5cb793261070" />
  
  Time domain: TXI => No distortion
  <img width="1277" height="722" alt="grafik" src="https://github.com/user-attachments/assets/2c309294-0274-42ff-bd80-e94c473b1576" />


<h2>Notes</h2>
- Notch filter intended to suppress the frequency component at two times the resonance frequency after rectification is not necessary. The currently used resistor and capacitor values are dummy values. 
<img width="720" height="546" alt="grafik" src="https://github.com/user-attachments/assets/35c2b70f-8db9-4ccb-9607-3ec4676fe1b5" />

<h2>Use Cases</h2>

- Guitar / musical instrument pickup
- Vibration sensing of metallic objects

<h2>Audio examples</h2>

https://github.com/user-attachments/assets/294e206a-773d-46ed-8725-847c0cfb6f45

https://github.com/user-attachments/assets/1e3492f7-05f8-4548-aefb-00401e7eae84



