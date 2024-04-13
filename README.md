# AsksinPP_HM-LC-DIM1PWM-CV
12V PWM-Dimmer auf AsksinPP-Basis

![3D-Ansicht](/images/HM-LC-DIM1PWM-CV_3D_640x360.jpg)

eine modifizierte Version des 7-24V-Dimmers von psi (Danke dafür :-)).
![Treiberschaltung mit MIC4422](/images/treiberschaltung.png)

Die große Neuerung hier ist der MOSFET-Treiber MIC4422. Wärmeverluste gehören damit der Vergangenheit an, der MOSFET bleibt lauwarm bis kalt. Der Nachteil ist die Tatsache, dass man um eine geätzte Platine nicht herumkommt. Schuld trägt besagter Treiber in der SMD-Variante.

Der zu verwendende MOSFET ist fast egal, Hauptsache er ist vom Typ "N-Kanal". Ein möglichst niedriger Rds-On-Wert (Durchlasswiderstand im eingeschalteten Zustand) ist wünschenswert. 
Ein typischer N-Kanal-MOSFET alter Bauart ist der BUZ11 mit einem Rds von 0,04 Ohm. 
Bei ihm beträgt der Leistungsverlust bei 6A: 6x6x0,04=1.5W. Das ist immer noch ohne Kühlkörper machbar. Besser ist natürlich der IRLB3036 mit einem Rds von 2,4mOhm, da kommt als Wärmeleistung 90mW heraus. Das ist quasi nichts. Die Umschaltverluste kommen da noch oben drauf, die sind aber vernachlässigbar.

Vorsicht!
Die höchste, zulässige Eingangsspannung ist 18V. 24V-LED-Bänder scheiden damit leider aus.

### Gehäuse
Das Gehäuse wird mit einer einzigen Schraube verschlossen. Im CAD-Verzeichnis liegen die passenden step-Dateien und das Original im FreeCAD-Format.
![Gehäuse](/cad/HM-LC-DIM1PWM-CV_Gehaeuse.png)

### Sketch
Im Sketch müssen die üblichen Anpassungen der Serial usw. vorgenommen werden. Ansonsten enspricht es genau der Version von psi.

### Bauteilliste
| Pos | Ref | Wert |
|-----|-----|------|
| 1 | C3, C4 | 100nF / Keramikkondensator, RM2.5 |
| 2 | C1 | 100µF / 25V D=6mm |
| 3	|	C2 | 100nF	C_Rect_L4.6mm_W3.0mm_P2.50mm_MKS02_FKP02 |
| 4	|	R1 | 330R, 0207 |
| 5	|	D1 | LED	3mm, Farbe egal |
| 6 |	U1 | L78L05, TO92 |
| 7	|	U2 | CC1101-Modul |
| 8 | U3 | MIC4422YM	SOIC-8 |
| 9 |	X1, X2 | Schraubklemme 2pol P5.00mm oder 5.08mm	|
| 10 | SW1 | Taster 6x6mm H5mm |
| 11 | SW2 | Taster 6x6mmm H5mm |
| 12 | A1	| Arduino Pro_Mini |
| 13 | Q1	| IRF3708 oder anderer N-Kanal MOSFET, TO-220 |
| 14 | J3	| AVR-ISP-6	Molex_PicoBlade_53047-0610_1x06_P1.25mm_Vertical |

Position 14 kann bedenkenlos weggelassen werden wenn man nicht per ISP programmieren möchte
