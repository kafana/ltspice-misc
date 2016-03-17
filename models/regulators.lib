* Compiled By Robertugo_2005, use with the symbol reg3all.asy,located at folder
*\sym\Robertugo and pick & compare with the regulator model of you choice!
******************************************************************************
*dummy subckt used only for symbol initialization
.subckt Vreg 1 2 3
.ends
******************************************************************************
.subckt 7805 In Aj Out
F1 In 0 Vc 1
Rcon In 0 1e6
B1 4 Aj V= Table (V(In,Aj), 0,0, 1,0, 7,5, 35,5, 36,0)
Vc 4 Out 0
F2 In Aj Vc 4m
.ends
*78L05 MCE 7-12-95
*78L05 circuit taken from Signetics 1977 Analog Data Book page 160
*5V 100mA Voltage Regulator pkg:TO-92 1,2,3
.SUBCKT 78L05 1 2 3
Q1 5 5 1 QPNP
Q2 10 5 1 QPNP
Q3 1 11 12 QNPN
Q4 1 10 11 QNPN
Q5 10 13 14 QNPN
Q6 1 4 20 QNPN
Q7 10 19 21 QNPN
Q8 9 9 2 QNPN
Q9 18 9 22 QNPN OFF
Q10 8 18 2 QNPN
Q11 5 7 17 QNPN
Q12 5 16 17 QNPN
Q13 10 15 17 QNPN
C1 15 10 20E-12
D1 2 4 DZ5V
Q14 2 8 7 QPNP
R17 2 17 4E3
R16 4 1 20E3
R15 16 20 4E3
R14 19 16 700
R13 2 19 300
R12 2 21 100
R11 9 7 1E3
R10 18 7 10E3
R9 7 3 2.2E3
R8 2 22 1E3
R7 8 7 2E3
R6 2 15 1.4E3
R5 15 3 4.5E3
R4 3 14 100
R3 3 12 2
R2 13 11 500
R1 13 12 200

.MODEL QPNP PNP(IS=1.05E-15 BF=220 VAF=240 IKF=0.1 ISE=1.003E-9
+ NE=4 ISC=1.003E-9 NC=4 RB=3 RE=0.5 RC=0.2 CJE=5.7E-12 VJE=0.75 TF=3.35E-10
+ CJC=4.32E-12 VJC=0.75 TR=1.7E-7 VJS=0.75 KF=4E-15 )

.MODEL QNPN NPN(IS=8.11E-14 BF=205 VAF=113 IKF=0.5 ISE=1.06E-11
+ NE=2 BR=4 VAR=24 IKR=0.225 RB=1.37 RE=0.343 RC=0.137 CJE=2.95E-11
+ TF=3.97E-10 CJC=1.52E-11 TR=8.5E-8 XTB=1.5 )

.MODEL DZ5V D(IS=1E-11 RS=7.708 N=1.27 TT=5E-8 CJO=4.068E-10 VJ=0.75
+ M=0.33 BV=4.946 IBV=0.01 )
.ENDS 78L05
* LM7805 model. 
* No need to use .inc - I've set the .asy symbol to remove the need for .inc.
* (I used the symbol of LT1084, just replaced the LT1084 by LMxxxx and LTC.LIB by regulators.lib) 

.SUBCKT LM7805  1    2    3
* In GND Out
QT6          23  10  2   Q_NPN 0.1
QT7          5   4   10  Q_NPN 0.1
QT5          7   6   5   Q_NPN 0.1
QT1          1   9   8   Q_NPN 0.1
QT3          11  8   7   Q_NPN 0.1
QT2          11  13  12  Q_NPN 0.1
QT17         1   15  14  Q_NPN 10
C2           10  23      4P
R16          12  5       500
R12          16  2       12.1K
QT18         17  23  16  Q_NPN 0.1
D1           18  19  	 D_D 
R11          20  21      850
R5           22  3       100
QT14         24  18  2   Q_NPN 0.1
R21          6   2       2.67K
R20          3   6       640
DZ2          25  26      D_5V1 
R19          1   26      16K
R18          14  3       250M
R17          25  14      380
R15          25  15      1.62K
QT16         1   20  15  Q_NPN 1
QT15         2   24  21  Q_PNP 0.1
*OFF
R14          21  24      4K
C1           27  24      20P
R13          19  2       4K
QT13         24  27  18  Q_NPN 0.1
QT12         20  25  22  Q_NPN 1 
*OFF
QT11         20  28  2   Q_NPN 0.1
*OFF
QT10         20  11  1   Q_PNP 0.1
R10          17  27      16.5K
R9           5   4       1.9K
R8           4   23      26
R7           10  2       1.2K
R6           29  2       1K
QT9          11  11  1   Q_PNP 0.1
QT8          27  16  29  Q_NPN 0.1
QT4          15  6   17  Q_NPN 0.1
DZ1          2   9       D_5V6
R4           1   9       80K
R3           28  2       830
R2           13  28      4.97K
R1           8   13      7K
*
.MODEL D_5V1 D( IS=10F N=1.16 BV=5.1 IBV=0.5M CJ0 = 1P TT = 10p )
.MODEL D_5V6 D( IS=10F N=1.16 BV=5.6 IBV=5U CJ0 = 1P TT = 10p )
.MODEL Q_NPN NPN( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+       TF=10P TR=1N )
.MODEL Q_PNP PNP( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+      TF=10P TR=1N )
.MODEL D_D D( IS=1F N=1.16 CJ0 = 1P TT = 10p )

.ENDS LM7805
*
.subckt NV78L05 1 2 3
Q1 1 N006 N010 0 NP
Q2 1 N004 N006 0 NP
*R1 N010 2 7
R1 N010 2 3.5
R2 N006 2 2.5K
R3 2 N018 2.65k
R4 N018 3 2.23K
Q3 N012 N015 N020 0 NP
Q4 N003 N003 1 0 PN
R5 N018 N015 15k
Q5 N022 N022 3 0 NP
R7 N019 3 7.8k
Q6 N006 N017 N020 0 NP
C1 N015 N012 5p
Q7 N020 N021 N023 0 NP
R9 N004 N012 5.76k
Q9 N004 N009 N013 0 NP
Q11 N021 N021 N022 0 NP
R17 N010 N009 100
R18 N001 N005 2k
Q16 N008 N003 N002 0 PN
Q17 N004 N003 1 0 PN
Q18 3 N012 N004 0 PN
J1 1 3 N007 2N3819
D4 3 N008 DZ
Q8 N003 N007 N008 0 NP
R13 1 N002 410
Q10 N019 N014 N011 0 PN
Q12 N003 N008 N011 0 NP
R11 N011 N014 576
R12 N014 N016 3.41k
R14 N016 N021 3.89k
R8 N023 3 2.84k
R6 N013 2 100
R10 N017 N016 13k
Q13 N004 N019 3 0 NP
D6 3 N007 DZ
D1 1 N001 1N4148
D2 N005 N009 1N4148
.model D D
.model NPN NPN
.model PNP PNP
.model NJF NJF
.model PJF PJF
.model DZ D(BV=3.5)
.model NP NPN(BF=125 Cje=.5p Cjc=.5p Rb=500)
.model PN LPNP(BF=25 Cje=.3p Cjc=1.5p Rb=250)
.ends NV78L05
*
.subckt LT1584 1 2 3
*.subckt NV78L05 1 2 3
Q1 N002 2 N001 0 N temp=27
R2 N001 1 10.06K
Q3 3 N007 2 0 NP
I2 3 N002 55µ
Q7 3 N002 N006 0 NA
Q12 2 N006 N007 0 PA
I1 N006 2 100µ
D1 N007 3 D
G1 N007 3 3 2 table( 4 0 8.5 .72m)
R3 3 N007 100K
G3 3 N007 3 2 table( 1 0m 1.3 1m)
R4 N007 1 1Meg
I4 3 2 1m load
C3 3 N006 500p Rser=5K
D3 N002 3 D
C2 3 N002 1n Rser=480Meg Rpar=180Meg
.model N NPN(BF=125 Cjc=40p)
.model NP NPN(BF=8K)
.model D D(Ron=1 Roff=1T)
.model PA PNP(BF=100)
.model NA NPN(BF=150)
.ends LT1584
*
*==================================
.subckt 7808 In Aj Out
F1 In 0 Vc 1
Rcon In 0 1e6
B1 4 Aj V= Table (V(In,Aj), 0,0, 1,0, 10,8, 35,8, 36,0)
Vc 4 Out 0
F2 In Aj Vc 4m
.ends
*78L08 MCE 7-12-95
*78L08 circuit taken from Signetics 1977 Analog Data Book page 160
*8.2V 100mA Voltage Regulator pkg:TO-92 1,2,3
.SUBCKT 78L08 1 2 3
Q1 5 5 1 QPNP
Q2 10 5 1 QPNP
Q3 1 11 12 QNPN
Q4 1 10 11 QNPN
Q5 10 13 14 QNPN
Q6 1 4 20 QNPN
Q7 10 19 21 QNPN
Q8 9 9 2 QNPN
Q9 18 9 22 QNPN OFF
Q10 8 18 2 QNPN
Q11 5 7 17 QNPN
Q12 5 16 17 QNPN
Q13 10 15 17 QNPN
C1 15 10 20E-12
D1 2 4 DZ8V
Q14 2 8 7 QPNP
R17 2 17 4E3
R16 4 1 20E3
R15 16 20 4E3
R14 19 16 700
R13 2 19 300
R12 2 21 100
R11 9 7 1E3
R10 18 7 10E3
R9 7 3 3.3E3
R8 2 22 1E3
R7 8 7 2E3
R6 2 15 1.4E3
R5 15 3 6.2E3
R4 3 14 100
R3 3 12 2
R2 13 11 500
R1 13 12 200
*
.MODEL QPNP PNP(IS=1.05E-15 BF=220 VAF=240 IKF=0.1 ISE=1.003E-9
+ NE=4 ISC=1.003E-9 NC=4 RB=3 RE=0.5 RC=0.2 CJE=5.7E-12 VJE=0.75 TF=3.35E-10
+ CJC=4.32E-12 VJC=0.75 TR=1.7E-7 VJS=0.75 KF=4E-15 )

.MODEL QNPN NPN(IS=8.11E-14 BF=205 VAF=113 IKF=0.5 ISE=1.06E-11
+ NE=2 BR=4 VAR=24 IKR=0.225 RB=1.37 RE=0.343 RC=0.137 CJE=2.95E-11
+ TF=3.97E-10 CJC=1.52E-11 TR=8.5E-8 XTB=1.5 )

.MODEL DZ8V D(IS=1E-11 RS=3.858 N=1.27 TT=5E-8 CJO=2.749E-10 VJ=0.75
+ M=0.33 BV=8.123 IBV=0.01 )
.ENDS 78L08
*==================================
.subckt 7812 In Aj Out
F1 In 0 Vc 1
Rcon In 0 1e6
B1 4 Aj V= Table (V(In,Aj), 0,0, 1,0, 14,12, 35,12, 36,0)
Vc 4 Out 0
F2 In Aj Vc 4m
.ends
*78L12 MCE 7-12-95
*78L12 circuit taken from Signetics 1977 Analog Data Book page 160
*12V 100mA Voltage Regulator pkg:TO-92 1,2,3
* Modified to produce correct (dead nuts) regulation on 12-18-03
.SUBCKT 78L12 1 2 3
Q1 5 5 1 QPNP
Q2 10 5 1 QPNP
Q3 1 11 12 QNPN
Q4 1 10 11 QNPN
Q5 10 13 14 QNPN
Q6 1 4 20 QNPN
Q7 10 19 21 QNPN
Q8 9 9 2 QNPN
Q9 18 9 22 QNPN OFF
Q10 8 18 2 QNPN
Q11 5 7 17 QNPN
Q12 5 16 17 QNPN
Q13 10 15 17 QNPN
C1 15 10 20E-12
D1 2 4 DZ10V
Q14 2 8 7 QPNP
R17 2 17 4E3
R16 4 1 20E3
R15 16 20 4E3
R14 19 16 700
R13 2 19 300
R12 2 21 100
R11 9 7 1E3
R10 18 7 10E3
R9 7 3 7.1E3
R8 2 22 1E3
R7 8 7 2E3
R6 2 15 1.4E3
R5 15 3 7.5E3
R4 3 14 100
R3 3 12 2
R2 13 11 500
R1 13 12 200
*
.MODEL QPNP PNP(IS=1.05E-15 BF=220 VAF=240 IKF=0.1 ISE=1.003E-9
+ NE=4 ISC=1.003E-9 NC=4 RB=3 RE=0.5 RC=0.2 CJE=5.7E-12 VJE=0.75 TF=3.35E-10
+ CJC=4.32E-12 VJC=0.75 TR=1.7E-7 VJS=0.75 KF=4E-15 )

.MODEL QNPN NPN(IS=8.11E-14 BF=205 VAF=113 IKF=0.5 ISE=1.06E-11
+ NE=2 BR=4 VAR=24 IKR=0.225 RB=1.37 RE=0.343 RC=0.137 CJE=2.95E-11
+ TF=3.97E-10 CJC=1.52E-11 TR=8.5E-8 XTB=1.5 )
*
.MODEL DZ10V D(IS=1E-11 RS=8.483 N=1.27 TT=5E-8 CJO=2.334E-10 VJ=0.75
+ M=0.33 BV=10.27 IBV=0.01 )
.ENDS 78L12
*
* Pinouts are the same as 7805.
*
.SUBCKT LM7812  1    2    3
QT6          23  10  2   Q_NPN 0.1
QT7          5   4   10  Q_NPN 0.1
QT5          7   6   5   Q_NPN 0.1
QT1          1   9   8   Q_NPN 0.1
QT3          11  8   7   Q_NPN 0.1
QT2          11  13  12  Q_NPN 0.1
QT17         1   15  14  Q_NPN 10
C2           10  23      4P
R16          12  5       500
R12          16  2       12.1K
QT18         17  23  16  Q_NPN 0.1
D1           18  19  	 D_D 
R11          20  21      850
R5           22  3       100
QT14         24  18  2   Q_NPN 0.1
R21          6   2       2.67K
R20          3   6       5.22K
DZ2          25  26      D_5V1 
R19          1   26      16K
R18          14  3       250M
R17          25  14      380
R15          25  15      1.62K
QT16         1   20  15  Q_NPN 1
QT15         2   24  21  Q_PNP 0.1 
*OFF
R14          21  24      4K
C1           27  24      20P
R13          19  2       4K
QT13         24  27  18  Q_NPN 0.1
QT12         20  25  22  Q_NPN 1 
*OFF
QT11         20  28  2   Q_NPN 0.1
*OFF
QT10         20  11  1   Q_PNP 0.1
R10          17  27      16.5K
R9           5   4       1.9K
R8           4   23      26
R7           10  2       1.2K
R6           29  2       1K
QT9          11  11  1   Q_PNP 0.1
QT8          27  16  29  Q_NPN 0.1
QT4          15  6   17  Q_NPN 0.1
DZ1          2   9       D_5V6
R4           1   9       80K
R3           28  2       830
R2           13  28      4.97K
R1           8   13      7K
*
.MODEL D_5V1 D( IS=10F N=1.16 BV=5.1 IBV=0.5M CJ0 = 1P TT = 10p )
.MODEL D_5V6 D( IS=10F N=1.16 BV=5.6 IBV=5U CJ0 = 1P TT = 10p )
.MODEL Q_NPN NPN( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+       TF=10P TR=1N )
.MODEL Q_PNP PNP( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+      TF=10P TR=1N )
.MODEL D_D D( IS=1F N=1.16 CJ0 = 1P TT = 10p )
*
.ENDS LM7812
*==================================
*78L15 MCE 7-12-95
*78L15 circuit taken from Signetics 1977 Analog Data Book page 160
*15V 100mA Voltage Regulator pkg:TO-92 1,2,3
.SUBCKT 78L15 1 2 3
Q1 5 5 6 QPNP
Q2 10 5 6 QPNP
Q3 6 11 12 QNPN
Q4 6 10 11 QNPN
Q5 10 13 14 QNPN
Q6 6 4 20 QNPN
Q7 10 19 21 QNPN
Q8 9 9 2 QNPN
Q9 18 9 22 QNPN OFF
Q10 8 18 2 QNPN
Q11 5 7 17 QNPN
Q12 5 16 17 QNPN
Q13 10 15 17 QNPN
C1 15 10 20E-12
D1 2 4 DZ10V
Q14 2 8 7 QPNP
R18 1 6 1E-6
R17 2 17 4E3
R16 4 6 20E3
R15 16 20 4E3
R14 19 16 700
R13 2 19 300
R12 2 21 100
R11 9 7 1E3
R10 18 7 10E3
R9 7 3 5E3
R8 2 22 1E3
R7 8 7 2E3
R6 2 15 1.4E3
R5 15 3 10.1E3
R4 3 14 100
R3 3 12 2
R2 13 11 500
R1 13 12 200
*
.MODEL QPNP PNP(IS=1.05E-15 BF=220 VAF=240 IKF=0.1 ISE=1.003E-9
+ NE=4 ISC=1.003E-9 NC=4 RB=3 RE=0.5 RC=0.2 CJE=5.7E-12 VJE=0.75 TF=3.35E-10
+ CJC=4.32E-12 VJC=0.75 TR=1.7E-7 VJS=0.75 KF=4E-15 )
*
.MODEL QNPN NPN(IS=8.11E-14 BF=205 VAF=113 IKF=0.5 ISE=1.06E-11
+ NE=2 BR=4 VAR=24 IKR=0.225 RB=1.37 RE=0.343 RC=0.137 CJE=2.95E-11
+ TF=3.97E-10 CJC=1.52E-11 TR=8.5E-8 XTB=1.5 )
*
.MODEL DZ10V D(IS=1E-11 RS=8.483 N=1.27 TT=5E-8 CJO=2.334E-10 VJ=0.75
+ M=0.33 BV=9.83 IBV=0.01 )
.ENDS 78L15
*
* Pinouts are the same as '05
.subckt 7815 In Aj Out
F1 In 0 Vc 1
Rcon In 0 1e6
B1 4 Aj V= Table (V(In,Aj), 0,0, 1,0, 17,15, 35,15, 36,0)
Vc 4 Out 0
F2 In Aj Vc 4m
.ends
*
.SUBCKT LM7815  1    2    3
QT6          23  10  2   Q_NPN 0.1
QT7          5   4   10  Q_NPN 0.1
QT5          7   6   5   Q_NPN 0.1
QT1          1   9   8   Q_NPN 0.1
QT3          11  8   7   Q_NPN 0.1
QT2          11  13  12  Q_NPN 0.1
QT17         1   15  14  Q_NPN 10
C2           10  23      4P
R16          12  5       500
R12          16  2       12.1K
QT18         17  23  16  Q_NPN 0.1
D1           18  19  	 D_D 
R11          20  21      850
R5           22  3       100
QT14         24  18  2   Q_NPN 0.1
R21          6   2       2.67K
R20          3   6       7.18K
DZ2          25  26      D_5V1 
R19          1   26      16K
R18          14  3       250M
R17          25  14      380
R15          25  15      1.62K
QT16         1   20  15  Q_NPN 1
QT15         2   24  21  Q_PNP 0.1 
*OFF
R14          21  24      4K
C1           27  24      20P
R13          19  2       4K
QT13         24  27  18  Q_NPN 0.1
QT12         20  25  22  Q_NPN 1 
*OFF
QT11         20  28  2   Q_NPN 0.1
*OFF
QT10         20  11  1   Q_PNP 0.1
R10          17  27      16.5K
R9           5   4       1.9K
R8           4   23      26
R7           10  2       1.2K
R6           29  2       1K
QT9          11  11  1   Q_PNP 0.1
QT8          27  16  29  Q_NPN 0.1
QT4          15  6   17  Q_NPN 0.1
DZ1          2   9       D_5V6
R4           1   9       80K
R3           28  2       830
R2           13  28      4.97K
R1           8   13      7K
*
.MODEL D_5V1 D( IS=10F N=1.16 BV=5.1 IBV=0.5M CJ0 = 1P TT = 10p )
.MODEL D_5V6 D( IS=10F N=1.16 BV=5.6 IBV=5U CJ0 = 1P TT = 10p )
.MODEL Q_NPN NPN( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+       TF=10P TR=1N )
.MODEL Q_PNP PNP( IS=10F NF=1.16 NR=1.16 BF=80 CJC=1P CJE=2P  
+      TF=10P TR=1N )
.MODEL D_D D( IS=1F N=1.16 CJ0 = 1P TT = 10p )
*
.ENDS LM7815
*
.SUBCKT LM7905  1    2    3            
*
DD4           4   5   D_6V3_0 
DD2           6   2   D_3V9_0 
DD1           7   2   D_4V7_0 
DD3           8   3   D_6V3_0 
C2            9  10  5P
C1            2   9  15P
QTU15         10   9   3   Q_PNP_0 1.000
R17          11  12  4.2K
QTU22          3  10  13   Q_NPN_0 3.000
R18           8   5  15.65K
R20          13  14  1K
R19           4  14  75
QTU31         12  11   4   Q_NPN_1 1.000
R16          15   1  160
R24          16   1  1.8K
C3           17   1  10P
QTU30         18  12  15   Q_NPN_1 1.000
QTU29         10  16   1   Q_NPN_1 1.000
R15          19   1  400
QTU28         10  20  19   Q_NPN_1 1.000
R14          21   1  200
QTU27         17  20  21   Q_NPN_1 1.000
R11          22  23  1K
R10          24  25  1K
QTU19         18  27  26   Q_NPN_1 1.000
R9            2  18  7.1K
QTU8          16  18   2   Q_PNP_0 1.000
QTU7          28  18   2   Q_PNP_0 1.000
QTU6          18  18   2   Q_PNP_0 1.000
QTU5          11  29   2   Q_PNP_0 1.000
QTU4          20  29   2   Q_PNP_0 1.000
QTU3           1  29   2   Q_PNP_0 1.000
QTU2           1  29   2   Q_PNP_0 1.000
R13          28   1  400
R12          30   1  400
QTU18         29  29  31   Q_NPN_1 1.000
QTU1          29  29   2   Q_PNP_0 1.000
R6           31  32  6.5K
R7           32  27  5.6K
R8           27  26  950
QTU10         33   6  26   Q_PNP_0 1.000
QTU17         34  35  33   Q_PNP_0 1.000
R5           36   1  2K
QTU24         34  34  36   Q_NPN_1 1.000
R1           37   6  6.3K
R2           37  38  670
R3           38  35  550
QTU9          38  35   6   Q_PNP_0 1.000
R4           39   1  2K
QTU23         35  34  39   Q_NPN_1 1.000
QTU16          1   7  35   Q_PNP_0 1.000
JT1           7   1   1  J_2N3458_N 
QTU14          3  17  23   Q_PNP_0 1.000
QTU13         17  17  23   Q_PNP_0 1.000
QTU12         17  17  25   Q_PNP_0 1.000
QTU11          9  17  25   Q_PNP_0 1.000
QTU32          3  13  14   Q_NPN_2 10.000
QTU26          9  20  28   Q_NPN_1 1.000
QTU25         20  20  30   Q_NPN_1 1.000
QTU21          2  40  22   Q_NPN_1 1.000
QTU20          2  37  24   Q_NPN_1 1.000
R21           2  40  4.29K
R22          40   3  500
R23          14   1  500M
*
.MODEL J_2N3458_N NJF( VTO=-3.05 BETA=699.53U LAMBDA=6M RD=1 RS=1 
+      CGD=2.81P CGS=2.91P M=227.1M PB=500M IS=114.41F 
+      VTOTC=-2.5M BETATCE=-500M KF=0 AF=1 )
.MODEL D_6V3_0  D( IS=10F N=1.24 BV=6.3 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_3V9_0  D( IS=10F N=1.24 BV=3.9 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_4V7_0  D( IS=10F N=1.24 BV=4.7 IBV=1M CJ0 = 1P TT = 10p )
.MODEL Q_PNP_0  PNP( IS=10F NF=1.04 NR=1.04 BF=50 CJC=1P CJE=2P
+      TF=10P TR=1N VAF=45)
.MODEL Q_NPN_0  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_1  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_2  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.ENDS LM7905
*
* This is a copy of the LM7905 from regulators.lib.
* R22 changed from 500 -> 7500
*
.SUBCKT LM7912  1    2    3            
DD4           4   5   D_6V3_0 
DD2           6   2   D_3V9_0 
DD1           7   2   D_4V7_0 
DD3           8   3   D_6V3_0 
C2            9  10  5P
C1            2   9  15P
QTU15         10   9   3   Q_PNP_0 1.000
R17          11  12  4.2K
QTU22          3  10  13   Q_NPN_0 3.000
R18           8   5  15.65K
R20          13  14  1K
R19           4  14  75
QTU31         12  11   4   Q_NPN_1 1.000
R16          15   1  160
R24          16   1  1.8K
C3           17   1  10P
QTU30         18  12  15   Q_NPN_1 1.000
QTU29         10  16   1   Q_NPN_1 1.000
R15          19   1  400
QTU28         10  20  19   Q_NPN_1 1.000
R14          21   1  200
QTU27         17  20  21   Q_NPN_1 1.000
R11          22  23  1K
R10          24  25  1K
QTU19         18  27  26   Q_NPN_1 1.000
R9            2  18  7.1K
QTU8          16  18   2   Q_PNP_0 1.000
QTU7          28  18   2   Q_PNP_0 1.000
QTU6          18  18   2   Q_PNP_0 1.000
QTU5          11  29   2   Q_PNP_0 1.000
QTU4          20  29   2   Q_PNP_0 1.000
QTU3           1  29   2   Q_PNP_0 1.000
QTU2           1  29   2   Q_PNP_0 1.000
R13          28   1  400
R12          30   1  400
QTU18         29  29  31   Q_NPN_1 1.000
QTU1          29  29   2   Q_PNP_0 1.000
R6           31  32  6.5K
R7           32  27  5.6K
R8           27  26  950
QTU10         33   6  26   Q_PNP_0 1.000
QTU17         34  35  33   Q_PNP_0 1.000
R5           36   1  2K
QTU24         34  34  36   Q_NPN_1 1.000
R1           37   6  6.3K
R2           37  38  670
R3           38  35  550
QTU9          38  35   6   Q_PNP_0 1.000
R4           39   1  2K
QTU23         35  34  39   Q_NPN_1 1.000
QTU16          1   7  35   Q_PNP_0 1.000
JT1           7   1   1  J_2N3458_N 
QTU14          3  17  23   Q_PNP_0 1.000
QTU13         17  17  23   Q_PNP_0 1.000
QTU12         17  17  25   Q_PNP_0 1.000
QTU11          9  17  25   Q_PNP_0 1.000
QTU32          3  13  14   Q_NPN_2 10.000
QTU26          9  20  28   Q_NPN_1 1.000
QTU25         20  20  30   Q_NPN_1 1.000
QTU21          2  40  22   Q_NPN_1 1.000
QTU20          2  37  24   Q_NPN_1 1.000
R21           2  40  4.29K
R22          40   3  7500
R23          14   1  500M

.MODEL J_2N3458_N NJF( VTO=-3.05 BETA=699.53U LAMBDA=6M RD=1 RS=1 
+      CGD=2.81P CGS=2.91P M=227.1M PB=500M IS=114.41F 
+      VTOTC=-2.5M BETATCE=-500M KF=0 AF=1 )
.MODEL D_6V3_0  D( IS=10F N=1.24 BV=6.3 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_3V9_0  D( IS=10F N=1.24 BV=3.9 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_4V7_0  D( IS=10F N=1.24 BV=4.7 IBV=1M CJ0 = 1P TT = 10p )
.MODEL Q_PNP_0  PNP( IS=10F NF=1.04 NR=1.04 BF=50 CJC=1P CJE=2P
+      TF=10P TR=1N VAF=45)
.MODEL Q_NPN_0  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_1  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_2  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.ENDS LM7912


* This is a copy of the LM7905 from regulators.lib.
* R22 changed from 500 -> 10.63k
*
.SUBCKT LM7915  1    2    3            
DD4           4   5   D_6V3_0 
DD2           6   2   D_3V9_0 
DD1           7   2   D_4V7_0 
DD3           8   3   D_6V3_0 
C2            9  10  5P
C1            2   9  15P
QTU15         10   9   3   Q_PNP_0 1.000
R17          11  12  4.2K
QTU22          3  10  13   Q_NPN_0 3.000
R18           8   5  15.65K
R20          13  14  1K
R19           4  14  75
QTU31         12  11   4   Q_NPN_1 1.000
R16          15   1  160
R24          16   1  1.8K
C3           17   1  10P
QTU30         18  12  15   Q_NPN_1 1.000
QTU29         10  16   1   Q_NPN_1 1.000
R15          19   1  400
QTU28         10  20  19   Q_NPN_1 1.000
R14          21   1  200
QTU27         17  20  21   Q_NPN_1 1.000
R11          22  23  1K
R10          24  25  1K
QTU19         18  27  26   Q_NPN_1 1.000
R9            2  18  7.1K
QTU8          16  18   2   Q_PNP_0 1.000
QTU7          28  18   2   Q_PNP_0 1.000
QTU6          18  18   2   Q_PNP_0 1.000
QTU5          11  29   2   Q_PNP_0 1.000
QTU4          20  29   2   Q_PNP_0 1.000
QTU3           1  29   2   Q_PNP_0 1.000
QTU2           1  29   2   Q_PNP_0 1.000
R13          28   1  400
R12          30   1  400
QTU18         29  29  31   Q_NPN_1 1.000
QTU1          29  29   2   Q_PNP_0 1.000
R6           31  32  6.5K
R7           32  27  5.6K
R8           27  26  950
QTU10         33   6  26   Q_PNP_0 1.000
QTU17         34  35  33   Q_PNP_0 1.000
R5           36   1  2K
QTU24         34  34  36   Q_NPN_1 1.000
R1           37   6  6.3K
R2           37  38  670
R3           38  35  550
QTU9          38  35   6   Q_PNP_0 1.000
R4           39   1  2K
QTU23         35  34  39   Q_NPN_1 1.000
QTU16          1   7  35   Q_PNP_0 1.000
JT1           7   1   1  J_2N3458_N 
QTU14          3  17  23   Q_PNP_0 1.000
QTU13         17  17  23   Q_PNP_0 1.000
QTU12         17  17  25   Q_PNP_0 1.000
QTU11          9  17  25   Q_PNP_0 1.000
QTU32          3  13  14   Q_NPN_2 10.000
QTU26          9  20  28   Q_NPN_1 1.000
QTU25         20  20  30   Q_NPN_1 1.000
QTU21          2  40  22   Q_NPN_1 1.000
QTU20          2  37  24   Q_NPN_1 1.000
R21           2  40  4.29K
R22          40   3  10.63k
R23          14   1  500M

.MODEL J_2N3458_N NJF( VTO=-3.05 BETA=699.53U LAMBDA=6M RD=1 RS=1 
+      CGD=2.81P CGS=2.91P M=227.1M PB=500M IS=114.41F 
+      VTOTC=-2.5M BETATCE=-500M KF=0 AF=1 )
.MODEL D_6V3_0  D( IS=10F N=1.24 BV=6.3 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_3V9_0  D( IS=10F N=1.24 BV=3.9 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_4V7_0  D( IS=10F N=1.24 BV=4.7 IBV=1M CJ0 = 1P TT = 10p )
.MODEL Q_PNP_0  PNP( IS=10F NF=1.04 NR=1.04 BF=50 CJC=1P CJE=2P
+      TF=10P TR=1N VAF=45)
.MODEL Q_NPN_0  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_1  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_NPN_2  NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.ENDS LM7915
*
*------------------------------------------------------------------------
*** Voltage regulators (positive/adjustable)
.subckt Lm117uC VIN ADJ VOUT
*
C1 VOUT 21 30P
C2 ADJ 21 30P
C3 27 26 5P
D1 VOUT 6 DZ63
D3 37 VIN DZ63
D4 31 38 DZ63
D5 ADJ VOUT DZ63
J1 VIN VOUT 6 NJ1
Q1 4 5 3 QP1 0.25
Q2 5 5 1 QP1 0.25
Q17 5 4 8 QN1
Q18 9 4 VOUT QN1
Q19 11 9 12 QN1
Q20 13 5 10 QP1
Q21 14 11 13 QP1
Q22 15 14 16 QN1
Q23 VOUT 9 13 QP1
Q25 VOUT 18 15 QP1
Q26 VIN 19 18 QN1
Q27 19 5 20 QP1
Q28 VOUT 21 19 QP1
Q29 21 VOUT 23 QN1
Q30 24 VOUT 25 QN1 10
Q31 21 24 15 QP1
Q32 24 24 15 QP1
Q33 15 5 17 QP1
Q34 VOUT 26 15 QP1
Q35 26 27 VOUT QN1
Q36 28 29 30 QN1
Q37 28 29 31 QN1
Q38 32 15 33 QN1 2
Q39 15 32 VIN QP1 2
Q40 32 32 VIN QP1 2
Q41 VIN 35 34 QN1 40
Q42 VIN 34 36 QN1 200
R1 1 VIN 310
R2 3 VIN 310
R3 4 6 125K
R13 9 4 130
R14 VOUT 8 180
R15 10 VIN 190
R16 VOUT 12 4.1K
R17 11 13 12.4K
R19 VOUT 14 5.8K
R20 VOUT 16 72
R21 17 VIN 82
R22 VOUT 18 5.1K
R23 20 VIN 5.6K
R25 23 ADJ 12K
R26 25 23 2.4K
R27 15 26 6.7K
R28 27 28 13K
R29 29 28 400
R30 31 30 160
R31 15 29 12K
R32 34 33 130
R33 35 15 370
R34 34 VOUT 160
R35 37 38 18K
R37 36 30 3
R38 VOUT 36 0.1
*
.MODEL NJ1 NJF (BETA=1E-3 VTO=-3)
.MODEL DZ60 D (BV=6.0 IBV=1M)
.MODEL DZ63 D (BV=6.3 IBV=1M)
.MODEL QN1 NPN (EG=1.22 BF=80 RB=100 CCS=2PF TF=.3NS TR=6NS CJE=3PF   
+ CJC=2PF VAF=100)
.MODEL QP1 PNP (BF=40 RB=20 TF=1NS TR=20NS CJE=6PF CJC=4PF VAF=100)
.MODEL QP12 PNP () 
.MODEL QN150 NPN () 
.ENDs
* This is the best of LMx17's subcicuits, thanks PSpice! 
* LM117 voltage regulator "macromodel" subcircuit
* created using Parts release 5.3 on 04/08/93 at 11:33
*
* connections:	 input
*		 |   adjustment pin
*		 |    |   output
*		 |    |   |
.SUBCKT LM117PSp IN ADJ OUT
*
* POSITIVE ADJUSTABLE VOLTAGE REGULATOR
*
JADJ IN ADJ ADJ JADJMOD	;ADJUSTMENT PIN CURRENT
VREF 4 ADJ 1.25
DBK IN 13 DMOD
*
* ZERO OF RIPPLE REJECTION
*
CBC 13 15 8e-010
RBC 15 5 1000
*
QPASS 13 5 OUT QPASSMOD
RB1 7 6 1
RB2 6 5 128.3
*
* CURRENT LIMITING
*
DSC 6 11 DMOD
ESC 11 OUT VALUE {5.646-0.1125*V(6,5)*V(13,5)}
*
* FOLDBACK CURRENT
*
DFB 6 12 DMOD
EFB 12 OUT VALUE {7.886-0.3727*V(13,5)+0.005097*V(13,5)*V(13,5)
+ -0.02*V(13,5)*V(6,5)}
*
EB 7 OUT 8 OUT 7.691
*
* ZERO OF OUTPUT IMPEDANCE
*
RP 9 8 100
CPZ 10 OUT 3.979e-006
*
DPU 10 OUT DMOD	;POWER-UP CLAMPLING DIODE
RZ 8 10 0.1
EP 9 OUT 4 OUT 100
RI OUT 4 100MEG
*
.MODEL QPASSMOD NPN (IS=30F BF=50 VAF=8.891 NF=2.612)
.MODEL JADJMOD NJF (BETA=5e-005 VTO=-1)
.MODEL DMOD D (IS=30F N=2.612)
.ENDS
*
.subckt LM317Psp 1 2 3
X1 1 2 3 LM117PSp
.ends
..............................................................................
*
.SUBCKT LM317    1    2    3
D4            4   3  D_Z6V0
D3            5   6  D_Z6V3
D2            7   1  D_Z6V3
D1            3   8  D_Z6V3
QT26          1  10   9  Q_NPN 20.0
QT25          1  11  10  Q_NPN 2.0
QT24_2       13  12   5  Q_NPN 0.1
QT24         13  12  14  Q_NPN 0.1
QT23         17  16  15  Q_NPN 1.0
QT21         19  18   3  Q_NPN 0.1
QT19         21   3  20  Q_NPN 1.0
QT17         23   3  22  Q_NPN 0.1
QT13          1  25  24  Q_NPN 0.1
QT11         16  27  26  Q_NPN 0.1
QT7          30  29  28  Q_NPN 0.1
QT5          29  31   3  Q_NPN 0.1
QT3          33  31  32  Q_NPN 0.1
QT22_2       17  17   1  Q_PNP 1.0
QT22         16  17   1  Q_PNP 1.0
QT20          3  19  16  Q_PNP 0.1
QT18         21  21  16  Q_PNP 0.1
QT16         23  21  16  Q_PNP 0.1
QT15          3  23  25  Q_PNP 0.1
QT12          3  24  16  Q_PNP 0.1
QT9          27  30  34  Q_PNP 0.1
QT6           3  29  34  Q_PNP 0.1
QT14         25  33  35  Q_PNP 0.1
QT10         16  33  36  Q_PNP 0.1
QT8          34  33  37  Q_PNP 0.1
QT4          31  33  38  Q_PNP 0.1
QT2          33  33  39  Q_PNP 0.1
R27           4   2  50
R26           9   3  100M
R25           9  14  2
R24           5  14  160
R23           7   6  18K
R22          10   3  160
R21          12  13  400
R20          18  13  13K
R19          16  11  370
R18          15  10  130
R17          16  12  12K
C3           19  18  5P
R16          16  19  6.7K
R15          20  22  2.4K
R14          22   4  12K
C2           23   4  30P
C1           23   3  30P
R13          24   3  5.1K
R12          26   3  72
R11          27   3  5.8K
R10          28   3  4.1K
R9           32   3  180
R8           34  30  12.4K
R7           31  29  130
R6            8  31  100K
R5            1  35  5.6K
R4            1  36  82
R3            1  37  190
R2            1  38  310
R1            1  39  310
JT1           1   3   8  J_N
*
.MODEL D_Z6V0 D( IS=10F N=1.04 BV=6.0 IBV=1M CJ0 = 1P TT = 10p )
.MODEL D_Z6V3 D( IS=10F N=1.04 BV=6.3 IBV=1M CJ0 = 1P TT = 10p )
.MODEL Q_NPN NPN( IS=10F NF=1.04 NR=1.04 BF=100 CJC=1P CJE=2P
+       TF=10P TR=1N VAF=90)
.MODEL Q_PNP PNP( IS=10F NF=1.04 NR=1.04 BF=50 CJC=1P CJE=2P
+      TF=10P TR=1N VAF=45)
.MODEL J_N NJF( VTO=-7 )
*
.ENDS LM317
* LM317MOT Voltage Reg. (Motorola)
*
.SUBCKT LM317MOT 1      2    3
*Connections  Input  Adj. Output
*LM317A voltage regulator - Motorola
J1 1 3 4 JN
Q2 5 5 6 QPL .1
Q3 5 8 9 QNL  .2
Q4 8 5 7 QPL .1
Q5 81 8 3 QNL .2
Q6 3 81 10 QPL .2
Q7 12 81 13 QNL  .2
Q8 10 5 11 QPL  .2 
Q9 14 12 10 QPL .2
Q10 16 5 17 QPL  .2
Q11 16 14 15 QNL .2
Q12 3 20 16 QPL .2
Q13 1 19 20 QNL .2
Q14 19 5 18 QPL .2
Q15 3 21 19 QPL .2
Q16 21 22 16 QPL .2
Q17 21 3 24 QNL   .2
Q18 22 22 16 QPL .2
Q19 22 3 241 QNL 2
Q20 3 25 16 QPL .2
Q21 25 26 3 QNL .2
Q22A 35 35 1 QPL 2
Q22B 16 35 1 QPL 2
Q23 35 16 30 QNL  2
Q24A 27 40 29 QNL .2
Q24B 27 40 28 QNL .2
Q25 1 31 41 QNL 5
Q26 1 41 32 QNL 50
D1 3 4 DZ
D2 33 1 DZ
D3 29 34 DZ
R1 1 6 310
R2 1 7 310
R3 1 11 230
R4 1 17 120
R5 1 18 5.6K
R6 4 8 125K
R7 8 81 135
R8 10 12 12.4K
R9 9 3 190
R10 13 3 3.6K
R11 14 3 5.8K
R12 15 3 110
R13 20 3 5.1K
R14 2 24 12.5K
R15 24 241 2.4K
R16 16 25 6.7K
R17 16 40 12K
R18 30 41 160
R19 16 31 170
R20 26 27 6.8K
R21 27 40 510
R22 3 41 200
R23 33 34 13K
R24 28 29 105
R25 28 32 4
R26 32 3 .1
C1 21 3 30PF
C2 21 2 30PF
C3 25 26 5PF
CBS1 5 3 2PF
CBS2 35 3 1PF
CBS3 22 3 1PF
.MODEL JN NJF(BETA=1E-4 VTO=-7)
.MODEL DZ D(BV=6.3)
.MODEL QNL NPN(EG=1.22 BF=80 RB=100 CCS=1.5PF TF=.3NS TR=6NS CJE=2PF
+ CJC=1PF VAF=100)
.MODEL QPL PNP(BF=40 RB=20 TF=.6NS TR=10NS CJE=1.5PF CJC=1PF VAF=50)
.ENDS LM317MOT
*
*
*
*LM317 Voltage Reg. (Texas Inst)
*
.SUBCKT LM317TI 1      2    3
*Connections  Input  Adj. Output
*LM317 voltage regulator - Texas Instruments
J1 1 3 4 JN
Q2 5 5 6 QPL .1
Q3 5 8 9 QNL  .2
Q4 8 5 7 QPL .1
Q5 81 8 3 QNL .2
Q6 3 81 10 QPL .2
Q7 12 81 13 QNL  .2
Q8 10 5 11 QPL  .2 
Q9 14 12 10 QPL .2
Q10 16 5 17 QPL  .2
Q11 16 14 15 QNL .2
Q12 3 20 16 QPL .2
Q13 1 19 20 QNL .2
Q14 19 5 18 QPL .2
Q15 3 21 19 QPL .2
Q16 21 22 16 QPL .2
Q17 21 3 24 QNL   .2
Q18 22 22 16 QPL .2
Q19 22 3 241 QNL 2
Q20 3 25 16 QPL .2
Q21 25 26 3 QNL .2
Q22A 35 35 1 QPL 2
Q22B 16 35 1 QPL 2
Q23 35 16 30 QNL  2
Q24A 27 40 29 QNL .2
Q24B 27 40 28 QNL .2
Q25 1 31 41 QNL 5
Q26 1 41 32 QNL 50
D1 3 4 DZ
D2 33 1 DZ
D3 29 34 DZ
R1 1 6 310
R2 1 7 310
R3 1 11 190
R4 1 17 82
R5 1 18 5.6K
R6 4 8 100K
R7 8 81 130
R8 10 12 12.4K
R9 9 3 180
R10 13 3 4.1K
R11 14 3 5.8K
R12 15 3 72
R13 20 3 5.1K
R14 2 24 12K
R15 24 241 2.4K
R16 16 25 6.7K
R17 16 40 12K
R18 30 41 130
R19 16 31 370
R20 26 27 13K
R21 27 40 400
R22 3 41 160
R23 33 34 18K
R24 28 29 160
R25 28 32 3
R26 32 3 .1
C1 21 3 30PF
C2 21 2 30PF
C3 25 26 5PF
CBS1 5 3 2PF
CBS2 35 3 1PF
CBS3 22 3 1PF
.MODEL JN NJF(BETA=1E-4 VTO=-7)
.MODEL DZ D(BV=6.3)
.MODEL QNL NPN(EG=1.22 BF=80 RB=100 CCS=1.5PF TF=.3NS TR=6NS CJE=2PF
+ CJC=1PF VAF=100)
.MODEL QPL PNP(BF=40 RB=20 TF=.6NS TR=10NS CJE=1.5PF CJC=1PF VAF=50)
.ENDS LM317TI
*
*LM317 Voltage Reg. (Motorola)
.SUBCKT LM317MOT2  1     2     3
*Connections     Input  Adj. Output
*LM317 voltage regulator
J1 1 3 4 JN 
Q2 5 5 6 QPL .25   
Q3 5 8 9 QNL    
Q4 8 5 7 QPL .25   
Q5 81 8 3 QNL   
Q6 3 81 10 QPL  
Q7 12 81 13 QNL 
Q8 10 5 11 QPL  
Q9 14 12 10 QPL 
Q10 16 5 17 QPL 
Q11 16 14 15 QNL
Q12 3 20 16 QPL 
Q13 1 19 20 QNL 
Q14 19 5 18 QPL 
Q15 3 21 19 QPL 
Q16 21 22 16 QPL
Q17 21 3 24 QNL 
Q18 22 22 16 QPL
Q19 22 3 241 QNL 10 
Q20 3 25 16 QPL 
Q21 25 26 3 QNL 
Q22A 35 35 1 QPL 2  
Q22B 16 35 1 QPL 2 
Q23 35 16 30 QNL 2 
Q24A 27 40 29 QNL   
Q24B 27 40 28 QNL   
Q25 1 31 41 QNL 40  
Q26 1 41 32 QNL 200 
D1 3 4 DZ   
D2 33 1 DZ  
D3 29 34 DZ 
R1 1 6 310  
R2 1 7 310  
R3 1 11 190 
R4 1 17 82  
R5 1 18 5.6K    
R6 4 8 125K 
R7 8 81 130 
R8 10 12 12.4K  
R9 9 3 180  
R10 13 3 4.1K   
R11 14 3 5.8K   
R12 15 3 72 
R13 20 3 5.1K   
R14 2 24 12K    
R15 24 241 2.4K 
R16 16 25 6.7K  
R17 16 40 12K   
R18 30 41 160   
R19 16 31 170   
R20 26 27 13K   
R21 27 40 400   
R22 3 41 160    
R23 33 34 18K   
R24 28 29 160   
R25 28 32 3 
R26 32 3 .1 
C1 21 3 30PF    
C2 21 2 30PF    
C3 25 26 5PF    
.MODEL JN NJF(BETA=1E-4 VTO=-7) 
.MODEL DZ D(BV=6.3) 
.MODEL QNL NPN(EG=1.22 BF=80 RB=100 CCS=2PF TF=.3NS TR=6NS CJE=3PF  
+ CJC=2PF VAF=100)   
.MODEL QPL PNP(BF=40 RB=20 TF=1NS TR=20NS CJE=6PF CJC=4PF VAF=100)   
.ENDS   LM317MOT2
*
*
*
* MANUFACTURERS PART NO.= SG137A   (SILICON GENERAL)
* SUBTYPE: REGULATOR
* THIS FILE CONTAINS A PRE-RAD TEMPERATURE DEPENDENT MACROMODEL OF THE
* SG137A.
*
* PLEASE NOTE THE FOLLOWING:
*
* THIS MODEL CAN BE USED FROM -55 C TO 125 C WITH THE .TEMP
* STATEMENT.  IT INCLUDES POWER-UP AND POWER-DOWN EFFECTS.    IT IS
* NECESSARY TO SET ITL1=300  ITL2=300 WITH THE .OPTIONS COMMAND FOR 100%
* CONVERGENCE.  THESE  SETTINGS DETERMINE THE NUMBER OF ITERATIONS
* ALLOW FOR THE  CALCULATION OF THE DC AND BIAS PT VALUES WHEN THE
* STARTING POINT  IS CONSIDERED "BLIND" OR AN "EDUCATED GUESS".
* OTHER SETTINGS MAY WORK, BUT HAVE NOT BEEN TESTED YET.
*
* RIPPLE REJECTION, OUTPUT IMPEDANCE, QUIESCENT CURRENT, LINE
* TRANSIENT, DROPOUT, AND LOAD TRANSIENT RESPONSE ARE MODELED BASED
* ON LABORATORY MEASUREMENTS.  THE CORRELATION IS QUITE GOOD.
* CURRENT LIMITING AND ADJUSTMENT CURRENT BASED ON DATA SHEET
* INFORMATION ARE MODELED ACCURATELY.
*
*
*------------------------------------------------------------------
*
*
.SUBCKT LM337   1  2   3    4
*               |  |   |    |
*              ADJ |   |    |
*                 OUT  |    |
*                     IN    |
*                          GND(REFERNCE)
*** VOLTAGE REFERENCE SECTION ***
LR 1 24 0.2709 m=1 TC1=7.8864E-4 TC2=-2.8391E-5
RR 24 5 98.2994 TC=-0.0063, 6.2251E-5
CR 1 6 3P
RCR 6 7 150K
DZR 7 5 DZR
.MODEL DZR D (IS=1E-14 RS=0 N=1 TT=0 CJO=0.1P VJ=1 M=.5 EG=1.11 XTI=3 KF=0
+ AF=1 FC=.5 BV=1.25 IBV=1E-10 ISR=0 NR=2 IKF=9.9999E+13 NBV=0.0001
+ IBVL=0 NBVL=1 TIKF=0 TBV1=2.2444E-6 TBV2=6.5556E-8 TRS1=0 TRS2=0)
RZR 7 5 1MEG
DZ1 8 7 DZ1
.MODEL DZ1 D(
+         IS = 1E-14
+         RS = 1
+          N = 1
+         TT = 0
+        CJO = 1P
+         VJ = 1
+          M = .5
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         BV = 1
+        IBV = 1E-10
+        ISR = 0
+         NR = 2
+        IKF = 9.9999E+13
+        NBV = 0.0001
+       IBVL = 0
+       NBVL = 1
+       TIKF = 0
+       TBV1 = -0.002847
+       TBV2 = 3.4722E-6
+       TRS1 = 0
+       TRS2 = 0
+ )
RQ 8 3 1.7546MEG TC=4.5212E-4,5.6515E-6
*** QUIESCENT CURRENT SECTION ***
FQ  1 3 VQ1 0.0625M
EQ1 24 100 1 7 1
VQ1 24 25 DC 0
RQ1 25 100 1 TC=-3.9528E-4,-1.1597E-5
*** ERROR AMPLIFIER ***
RIN 7 23 100K
E1  11 3 23 7 600
ROE1 9 11 10
D+ 9 13 DC
V+ 14 3 -1
E+ 13 14 1 3 1
.MODEL DC D(
+         IS = 1E-14
+         RS = 0
+          N = 1
+         TT = 0
+        CJO = 10P
+         VJ = 1
+          M = .5
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         BV = 9.9999E+13
+        IBV = 1E-10
+        ISR = 0
+         NR = 2
+        IKF = 9.9999E+13
+        NBV = 1
+       IBVL = 0
+       NBVL = 1
+       TIKF = 0
+       TBV1 = 0
+       TBV2 = 0
+       TRS1 = 0
+       TRS2 = 0
+ )
D- 12 9 DC
V- 12 3 DC 1
RP 9 10 151
CP 10 3 0.01U
E2 15 3 10 3 1
***
RB1 15 16 50
RB2 16 19 500 TC=-1.9327E-4,3.3434E-6
*** SHORT CIRCUIT AND FOLDBACK CURRENT SECTION ***
DSC 16 17 DMOD
ESC 17 3 POLY(1),(2,3) 2.447 -0.01
DFB 16 18 DMOD
EFB 18 3 POLY(1),(2,3) 12.5955 -1.2275 0.0457 -5.9169E-4
***
QP 20 19 3 QMOD
.MODEL QMOD NPN(
+         IS = 1E-14
+         BF = 500
+         NF = 1
+        VAF = 9.9999E+13
+        IKF = 9.9999E+13
+        ISE = 0
+         NE = 1.5
+         BR = 1
+         NR = 1
+        VAR = 9.9999E+13
+        IKR = 9.9999E+13
+        ISC = 0
+         NC = 2
+         RB = 0
+        IRB = 9.9999E+13
+        RBM = 0
+         RE = 0
+         RC = 0
+        CJE = 0
+        VJE = .75
+        MJE = .33
+         TF = 0
+        XTF = 0
+        VTF = 9.9999E+13
+        ITF = 0
+        PTF = 0
+        CJC = 0
+        VJC = .75
+        MJC = .33
+       XCJC = 1
+         TR = 0
+        CJS = 0
+        VJS = .75
+        MJS = 0
+        XTB = 0
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         NK = .5
+        ISS = 0
+         NS = 1
+        QCO = 0
+        RCO = 0
+         VO = 10
+      GAMMA = 1E-11
+       TRE1 = 0
+       TRE2 = 0
+       TRB1 = 0
+       TRB2 = 0
+       TRM1 = 0
+       TRM2 = 0
+       TRC1 = 0
+       TRC2 = 0
+ )
*** DROPOUT VOLTAGE SECTION ***
RDO 23 22 0.1
DDO1 22 21 DDO
DDO2 21 20 DDO
.MODEL DDO D(
+         IS = 1E-14
+         RS = 0
+          N = 0.9687
+         TT = 0
+        CJO = 0
+         VJ = 1
+          M = .5
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         BV = 9.9999E+13
+        IBV = 1E-10
+        ISR = 0
+         NR = 2
+        IKF = 9.9999E+13
+        NBV = 1
+       IBVL = 0
+       NBVL = 1
+       TIKF = 0
+       TBV1 = 0
+       TBV2 = 0
+       TRS1 = 0
+       TRS2 = 0
+ )
***
RO 23 2 0.0017 TC=-0.07894, 0.001136
DDIS 3 23 DDIS
.MODEL DDIS D(
+         IS = 1E-14
+         RS = 0
+          N = 1
+         TT = 0
+        CJO = 1PF
+         VJ = 1
+          M = .5
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         BV = 9.9999E+13
+        IBV = 1E-10
+        ISR = 0
+         NR = 2
+        IKF = 9.9999E+13
+        NBV = 1
+       IBVL = 0
+       NBVL = 1
+       TIKF = 0
+       TBV1 = 0
+       TBV2 = 0
+       TRS1 = 0
+       TRS2 = 0
+ )
.MODEL DMOD D(
+         IS = 1E-14
+         RS = 0
+          N = 1
+         TT = 0
+        CJO = 0
+         VJ = 1
+          M = .5
+         EG = 1.11
+        XTI = 3
+         KF = 0
+         AF = 1
+         FC = .5
+         BV = 9.9999E+13
+        IBV = 1E-10
+        ISR = 0
+         NR = 2
+        IKF = 9.9999E+13
+        NBV = 1
+       IBVL = 0
+       NBVL = 1
+       TIKF = 0
+       TBV1 = 0
+       TBV2 = 0
+       TRS1 = 0
+       TRS2 = 0
+ )
.ENDS LM337
*
* LT1009 model
* This is a selfmade model from the LTspice Yahoo group.
*          ____
* +5V o---<____>-----o--- 2.5V
*                    | REF
*                    |
*                   ---
*                   /_\--o ADJ
*                    |
*                    | MINUS
*                   ---
*
* Adjust pin -----------------
* Posive terminal --------    |
* Negative terminal -     |   |
*                    |    |   |
.subckt LT1009XY   MINUS REF ADJ
Q1 REF N001 MINUS 0 N
Q2 REF N004 N001 0 N
Q3 N001 N005 MINUS 0 N
Q4 N004 N007 N005 0 N
Q5 N005 N005 MINUS 0 N
Q6 N007 N007 N005 0 N
Q11 REF REF N013 0 N
Q12 N010 N012 N011 0 N
Q13 N012 N012 MINUS 0 N
Q10 N006 N014 N010 0 N
Q9 N009 N015 N010 0 N 3.63
Q7 N004 N006 N003 0 P
Q8 N007 N009 N003 0 P
R1 N004 N002 10K 
R2 N008 N009 24K  
R3 N008 N006 24k  
R4 N013 N014 6.6k  
R5 N014 N015 500 
R6 ADJ N015 30k  
R7 N015 N012 6.6k 
R8 N011 MINUS 720  
V1 N016 0 20
R9 N016 REF 3.6k  
Q7b N008 N008 REF 0 P
Q7a N003 N008 REF 0 P
R10 MINUS 0 1µ
C3 REF N002 20p
C1 N006 N004 30p
.model N NPN(BF=125 Cje=.5p Cjc=.5p Rb=500 NF=1.074)
.model P LPNP(BF=25 Cje=.3p Cjc=1.5p Rb=250)
.ends
*****************************************************************************
* TL431 MACROMODEL ***************3-26-92************************************
* REV N/A ****************************************************************DBB
*****************************************************************************
*               REFERENCE
*               |  ANODE
*               |  |  CATHODE
*               |  |  |
*.SUBCKT  TL431 1  2  3
* Reverse symbol
* Anode Cathode Ref   adjusted to LTSPICE symbol
.SUBCKT  TL431 2 3 1
V1  6  7  DC  1.4V
I1  2  4  1E-3
R1  1  2  1.2E6
R2  4  2  RMOD 2.495E3
R3  5  7  .2
D1  3  6  DMOD1
D2  2  3  DMOD1
D3  2  7  DMOD2
E1  5  2  POLY(2)  (4,2)  (1,2)  0  710  -710
.MODEL RMOD RES (TC1=1.4E-5 TC2=-1E-6)
.MODEL DMOD1 D (RS=.3)
.MODEL DMOD2 D (RS=1E-6)
.ENDS  TL431
* TL431A behavioral model by analog@ieee.org
.SUBCKT TL431_A A K R
R1 R A 1e6
D4 A 4 2V5
D5 A K Dc
D1 R K Dc
G2 K 4 6 A 90m
G1 A 5 R 4 1
C1 5 A 1n Rpar=1k
R2 6 5 700k
D2 4 R Dc
D3 A 6 Di
C2 K 6 40p Rser=6k Rpar=400k
*
.model Di D(Ron=10m)
.model Dc D(Ron=7 Vfwd=.6 Vrev=36)
.model 2V5 D(Ron=.13 Vfwd=.6 Vrev=2.5 Roff=7k)
.ENDS  TL431_A
* Model developed by Helmut Sennewald  6/27/2004
* This TL431 model has been developed from the schematic in the datasheet.
* It agrees with most of the test circuits and covers
* Tempco, C-load stability, AC gain, reverse diode, noise, transient, Zout
*         
*                 Ref   
*              Catho|de
*           Anode | |
*               | | |  
.SUBCKT TL431A  A K R
Q1 N003 N002 N001 0 NPN1 2
Q2 N002 N002 A 0 NPN1 1
Q3 N010 N010 N008 0 PNP1
Q4 N011 N010 N009 0 PNP1 1
* adjust tempco
R3 N001 A 800 TC1=0.00048
R4 N004 N003 7.2k
R5 N004 N002 2.4k
R6 N005 N004 3.28k
Q5 K R N005 0 NPN1 1
Q6 N006 N003 A 0 NPN1 1
R7 N007 N006 3k
C1 N006 N003 15p
Q7 N010 N005 N007 0 NPN1 1
R8 K N008 800
R9 K N009 800
Q8 N011 N012 A 0 NPN1 1
R10 N002 N012 1k
D1 A N011 D3
Q9 K N011 N014 0 NPN1 2
R11 N014 N013 150
Q10 K N013 A 0 NPN1 10
R12 N013 A 10k
C2 K N011 15p
D2 A K D1
D3 N011 N005 D2
* adjust output voltage with Is
.MODEL NPN1 NPN(Is=0.9e-14 BF=100 VAF=100 TF=0.5e-9 RB=50 IKF=10m KF=1e-16  AF=1 RE=10)
.MODEL PNP1 PNP(Is=1e-14 BF=50 VAF=50 TF=1e-8 IKF=2m KF=1e-16 AF=1)
.MODEL D1 D(Is=1e-13 Rs=10 CJ0=20p)
.MODEL D2 D(Is=1e-13 Rs=10 CJ0=2p BV=5 IBV=10u)
.MODEL D3 D(Is=1e-13 Rs=10 CJ0=2p )
.ENDS  TL431A
.SUBCKT TL_431 6 7 11
* A K FDBK
.MODEL DCLAMP D (IS=13.5N RS=25M N=1.59
+ CJO=45P VJ=.75 M=.302 TT=50.4N BV=34 IBV=1M)
V1 1 6 2.495
R1 6 2 15.6
C1 2 6 .5U
R2 2 3 100
C2 3 4 .08U
R3 4 6 10
G2 6 8 3 6 1.73
D1 5 8 DCLAMP
D2 7 8 DCLAMP
V4 5 6 2
G1 6 2 1 11 0.11
.ENDS
*
* TL431 behavioral model by analog@ieee.org
* Modifications: D6 added, R1 increased to 8Meg, model 2V5 changed to 1V25
.subckt TLV431AS A K R
R1 R A 8e6
D4 A 4 1V25
D5 A K Dc
D1 R K Dc
G2 K 4 6 A 90m
G1 A 5 R 4 1
C1 5 A 1n Rpar=1k
R2 6 5 700k
D2 4 R Dc
D3 A 6 Di
C2 K 6 40p Rser=6k Rpar=400k
D6 A R Dc
.model Di D(Ron=10m)
.model Dc D(Ron=7 Vfwd=.6 Vrev=36)
.model 1V25 D(Ron=.13 Vfwd=.6 Vrev=1.25 Roff=7k)
.ends
*
*SPICE_NET
.SUBCKT TLV431 6 7 11
*             A K FDBK
.MODEL DCLAMP D (IS=13.5N RS=25M N=1.59 
+ CJO=45P VJ=.75 M=.302 TT=50.4N BV=36V IBV=1MA)
.MODEL DCL2 D RS=660K
V1 1 6 1.24
R1 6 2 15.6
C1 2 6 .5U
R2 2 3 100
C2 3 4 1.3U
R3 4 6 8
G2 6 8 3 6  .86
D1 5 8 DCLAMP
D2 7 8 DCLAMP
D4 6 8 DCLAMP
*V4 5 6 2
V4 5 6 1.2
G1 6 2 1 11 0.11
VCLAMP 9 6 14.5
D3  7 9 DCL2
* Add-ons
Rinp 11 6 8e6
Din1 11 7 DCLAMP
Din2 6 11 DCLAMP
DKA 6 7 DCLAMP
.ENDS
*
*Zetex ZR431L Spice Model v1.0 Last Revised 21/10/05
*
*NOTE: This is a simplified model.  Do not rely on this model for 
*validation of circuit stability.  It does not accurately replicate 
*stability boundary conditions when the device is operated with 
*additional load capacitance.  Check the circuit stability by normal 
*breadboarding techniques.
*
.SUBCKT ZR431L 1 3 2
*Connections  VzGndVref
*
*Input current
Rin 2 3 Rmod1 1.127E7
D1 3 2 Dmod1
D2 2 1 Dmod1
Cin 2 3 10E-12
*
*Quiescent current
E1 50 3 2 3 1
D8 50 51 Dmod1
Rq 51 52 Rmod4 31E3
Vq 52 3 0
F1 1 3 Vq 1
Ro 1 3 1.5E6
*
*Reference voltage
Iref 3 21 1.2405E-3
Rref 21 3 Rmod2 1000
*
*Voltage dependence
G1 21 3 POLY(1) 1 3 0 1.57E-6 -0.97e-7
*
*Gain
G2 3 31 2 21 1e-7
Rt2  3 31 100E6
Rt3  3 32 3E6
Ct1 31 32 3E-13
D3 31 3  Dmod1
D4 3 31  Dmod1
*
*Output
*Q1 5 42 3 Qmod1
Cr1 7 31 1.5e-14
G3 41 3 31 3 0.8
Rc1 6 7 5
Rc2 7 5 5
D6 3 41 Dmod1
D7 3 1 Dmod1
L1 1 6 10nH
D9 5 41 Dmod2
*
.MODEL Qmod1 NPN BF=220 CJC=3E-12 CJE=3E-12
.MODEL Rmod1 RES (TC1=2.95E-3 TC2=-5E-7)
.MODEL Rmod2 RES (TC1=1.5e-5 TC2=-3.5e-7)
.MODEL Rmod3 RES (TC1=-2.5E-3 TC2=2E-5)
.MODEL Rmod4 RES (TC1=1.7E-3 TC2=0)
.MODEL Dmod1 D IS=5E-15 RS=4 BV=22
.MODEL Dmod2 D IS=1E-18 RS=.01
.ENDS  ZR431L
*
* Selfmade model of the LM334 from National Semiconductor or ST
* Helmut Sennewald
*
* Pin order: v+  v-  R
.SUBCKT LM334 v+ v- R
Q4 N002 N001 v+ 0 pnp1
Q5 N003 N001 v+ 0 pnp1
Q6 R N001 v+ 0 pnp1 14
Q1 N003 N003 R 0 npn1 14
Q2 N002 N003 N004 0 npn1
Q3 N001 N002 R 0 npn1
C1 N002 N004 50p
R2 N004 v- 1
R8 v+ v- 1G
C2 v+ v- 10p
C3 N003 v- 1p
C4 R v- 1p
.model npn1 NPN(Is=1e-15 BF=200 TF=1e-9 Cjc=0.5e-12 Cje=1e-12 VAF=100 Rb=100 Re=5)
.model pnp1 PNP(Is=1e-15 BF=100 TF=1e-7 Cjc=0.5e-12 Cje=1e-12 VAF=100 Rb=100 Re=5)
.ENDS  LM334
*
* LM385.sub 
* V1.01
* Self made model based on the LT1004-1.2 model.
* Helmut Sennewald
*
* If the circuit has convergence problems,
* use the following options.
* .options itl1=500 itl2=500 
*
* The Anode has pin-list order 1 
*       Reference ______
*       Cathode _____   |
*       Anode ____   |  |
*                 |  |  |
.subckt LM385     A  K  FB
R0 A K 1e7  ; DC-convergence
*R00 A R 1e9
Q1 K N001 A 0 N 5
Q3 N001 N003 K 0 P
Q4 N003 N003 N002 0 P
Q5 N003 N005 N004 0 N 1
R2 N004 A 500
R3 N001 A 100k
R4 K N002 7.5k
C1 N001 N003 20p
Q6 N005 N008 N006 0 N 4
Q7 N005 N007 K 0 P
R5 N006 A 60k
C2 N005 N007 20p
Q8 N008 N008 A 0 N 1
R6 K N008 600k
Q9 N009 N008 A 0 N
Q10 N010 N012 N009 0 N 7.43
Q11 N007 N011 N009 0 N
Q12 N007 N010 K 0 P
Q13 N010 N010 K 0 P
Q14 A FB N013 0 P
R7 N012 N013 300k
R8 N011 N012 50k
R9 K N011 200k
D1 A K DD
CC A K 5p
.model N NPN(BF=120 Cje=.5p Cjc=.5p Rb=500 NF=1.059 IKF=1m)
.model P LPNP(BF=25 Cje=.3p Cjc=1.5p Rb=250 NF 1.061)
.model DD D(Is=1e-12 Rs=5 Cjo=10p Tt=100n Ibv=0.1m Bv=6.3)
.ends