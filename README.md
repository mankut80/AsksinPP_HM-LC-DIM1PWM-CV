# AsksinPP_HM-LC-DIM1PWM-CV
12V PWM-Dimmer auf AsksinPP-Basis

eine modifizierte Version des 7-24V-Dimmers von psi (Danke dafür :-)).
![Treiberschaltung mit MIC4422](/images/treiberschaltung.png)

Die große Neuerung hier ist der MOSFET-Treiber MIC4422. Wärmeverluste gehören damit der Vergangenheit an, der MOSFET bleibt quasi eiskalt. Der Nachteil ist die Tatsache, dass man um eine geätzte Platine nicht herumkommt. Schuld trägt besagter Treiber in der SMD-Variante.

Der zu verwendende MOSFET ist fast egal, Hauptsache er ist vom Typ "N-Kanal". Ein möglichst niedriger Rds-On-Wert (Durchlasswiderstand im eingeschalteten Zustand) ist wünschenswert. Ein typischer N-Kanal-MOSFET ist der BUZ11 mit einem Rds von 0.04 Ohm. Dann beträgt der Leistungsverlust bei 6A: 6*6*0,04=1.5W. Das ist immer noch ohne Kühlkörper machbar. Besser ist natürlich der IRLB3036 mit einem Rds von 2.4mOhm, da kommt als Wärmeleistung 90mW heraus. Das ist quasi nichts.
