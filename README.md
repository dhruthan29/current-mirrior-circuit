# current-mirrior-circuit
# Theory
A current mirror circuit is a commonly used configuration in analog electronics, typically employed to replicate a reference current in a load or another part of the circuit. It works by mirroring (or copying) the current flowing through one active device, such as a transistor, and using it to generate the same current in a different device, often in a different location.
Basic Operation:
A current mirror usually consists of two or more transistors (typically bipolar junction transistors, BJTs, or MOSFETs) that are connected in such a way that the current through one transistor is mirrored by the current through the other transistor(s).
For BJTs:
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
  case1:ratio 1:1
  l=180nm w=20um for m1 m2 m3
  ![1](https://github.com/user-attachments/assets/fcf8e6a4-0f3b-436f-88dc-ec0b699bd167)
  vdd=1.8v
  I1=0.277mA
  #case 2 1:2
  for m3 w=180nm l=20um ,m2&m3=w=180nm l=40um
  ![2](https://github.com/user-attachments/assets/f05c87e0-7264-44ca-8b90-c58edc2e8c8e)
  when we varry the w/l the mosfet  the id current changes doubled  111111;
  # case 3 1:3
  for m3 w=20um l=180nm for m1&m2 w=60um l=180nm
  ![3](https://github.com/user-attachments/assets/8288abcc-caf8-4da1-b02c-10948ba34036)
  #Transient Analysis
  gain=10v/v
  ![4](https://github.com/user-attachments/assets/1c9c42bf-9f7a-4ea3-a969-df211a6a0ff2)


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


