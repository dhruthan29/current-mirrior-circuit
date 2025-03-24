# current-mirrior-circuit
# Theory
A current mirror circuit is a commonly used configuration in analog electronics, typically employed to replicate a reference current in a load or another part of the circuit. It works by mirroring (or copying) the current flowing through one active device, such as a transistor, and using it to generate the same current in a different device, often in a different location.
Basic Operation:
A current mirror usually consists of two or more transistors (typically bipolar junction transistors, BJTs, or MOSFETs) that are connected in such a way that the current through one transistor is mirrored by the current through the other transistor(s).
Matched Transistors: Two or more BJTs are matched (have the same characteristics) and are typically placed in a configuration where their base-emitter voltages are equal.
Reference Current: A reference current is applied to the base of one transistor (the reference transistor), causing it to conduct a current.
Mirror Current: The second transistor (output transistor) will conduct the same current because the base-emitter voltage of the output transistor is the same as that of the reference transistor (assuming both are in thermal equilibrium and have matched characteristics).
For MOSFETs:
In MOSFET-based current mirrors, the transistors are usually configured in such a way that the gate-to-source voltages are matched, and the drain current in one MOSFET is mirrored by another MOSFET.
Basic BJT Current Mirror:
In a basic BJT current mirror, two NPN transistors (Q1 and Q2) are used:
Q1 is the reference transistor, with its collector connected to a voltage source (often a Vcc) through a resistor, and its emitter grounded.
Q2 is the output transistor, which mirrors the current flowing through Q1. The base of Q2 is connected to the base of Q1, and the emitter of Q2 is connected to the same voltage level as the emitter of Q1.
When a current 𝐼𝑅𝐸𝐹I REF flows through Q1, the same current (or a scaled version depending on the mirror ratio) flows through Q2. The ratio of the currents in the two transistors is determined by the ratio of their collector-emitter areas or other factors depending on the mirror design.
  #AIM : Design and analysis currnet mirror circuit
  # Calculation
  Itotal=power/Vdd
Itotal=1mw/1.8=0.55mA
Itotal=Iref + Ix
Iref=0.55ma/2=0.277mA

  # DC  Analysis
  For the current mirror to work correctly, the transistors must be matched in terms of size, threshold voltage (for MOSFETs), and other process parameters.
In DC analysis, you can confirm whether both transistors are operating under similar conditions and whether they are mirroring the current properly.
  # case1:ratio 1:1
  l=180nm w=20um for m1 m2 m3
  ![dc1](https://github.com/user-attachments/assets/e6daeafe-52e8-45d9-8970-e96f6e425289)
  vdd=1.8v
  I1=0.277mA
  # case 2 1:2
  for m3 w=18.35m l=500um ,m2&m3=w=18.35nm l=500um
  ![dc2](https://github.com/user-attachments/assets/e3edba9d-e588-4292-b21b-83391dbf1f27)
  Saturation Condition for MOSFETs: For an NMOS transistor to be in saturation: VDS>VGS−Vth​therefore MOSFET is in saturation.
  # case 3 
  for m3 w=14.65mm l=1um for m1&m2 w=14.65mm l=1umm

![d3](https://github.com/user-attachments/assets/2db1c4b7-1572-49cb-b4a3-2b62da4bf95c)

  # Transient Analysis
  shows how fast the current mirror settles to its steady-state value. If the time constant is large, it will take longer for the circuit to stabilize after a change, leading to a slower transient response.
  A current mirror typically has a load connected to the output. The load can affect how the output current responds to transient conditions.
  In some cases, when the current mirror is first powered on, there may be an initial surge or spike in current as the transistors begin to operate. The start-up transient behavior of the current mirror is important to analyze, especially if the circuit is part of a larger system where the current mirror must quickly stabilize.
  gain=10v/v
 # vin

 ![vin transient](https://github.com/user-attachments/assets/54158d2f-f922-4c11-aecf-98ae8e9a7e43)
 # vout 

 ![vouttransient](https://github.com/user-attachments/assets/051424c0-25ae-4298-b3f6-6452f1062dba)
 # Diffretial Pair with current Mirror
 
In the case of a MOSFET-based differential pair, we use two MOSFETs (let's call them M1 and M2) to amplify the difference between two input signals. The gates (or in some cases, the sources) of these MOSFETs are connected to the differential input signals.
M1: The gate of M1 is connected to one input signal, 𝑉𝑖𝑛1V in1​ .
M2: The gate of M2 is connected to the second input signal, 𝑉𝑖𝑛
2V in2
The source terminals of both MOSFETs are typically connected together and biased by a current source, ensuring that the total current flowing through the differential pair is constant
The two MOSFETs (M1 and M2) form the differential pair, where the source terminals are connected to a current source or an active load.

The gates of the MOSFETs receive the differential input signals 𝑉𝑖𝑛1V in1 and 𝑉𝑖𝑛2V in2
 and the drains are connected to the current mirror (MOSFETs M3 and M4).
The current mirror controls the current through the differential pair based on the difference in the gate voltages of M1 and M2.
# DC Analysis



  # Inference 
  In reality, there are variations due to mismatches between the transistors (in MOSFETs or BJTs), their thermal characteristics, and process variations. This leads to some error in the mirrored current.
 If the current mirror is accurate, it means that both the reference and output currents are closely matched despite transistor mismatches or temperature fluctuations.
For a basic current mirror, the relationship between the output current (𝐼OUTI OUT ) and the reference current (𝐼REFI REF ) is ideally a 1:1 ratio. However, practical mirrors might not have a perfect match.
If you are designing a current mirror with a scaled output, you expect the output current to be a multiple (or fraction) of the reference current, depending on the relative sizes of the transistors.
For MOSFET-based current mirrors, the drain-to-source voltage 𝑉𝐷𝑆V DS  of the output transistor must be high enough to ensure the transistor is operating in the saturation region. If 𝑉𝐷𝑆V DS
 is too low, the transistor may enter the triode region, and the current mirror will no longer function properly.
 # Result
 The current mirror should provide a stable output current, even when the load or output voltage varies. High output impedance is preferred to maintain this stability.
If both transistors are perfectly matched, the mirrored current will exactly match the reference current
Process variations lead to slight mismatches in transistor parameters (like threshold voltage, current gain, etc.), which result in a mismatch between the reference current and the output current. The current mirror might not be perfectly accurate but should still provide a current close to the reference.


