RELAY FLAG (double-turn in battle)
----------------------------------
ORIG:	C2/A08C	20 5A A3    JSR $A35A
NEW:	C2/A08C	4C 00 FA    JMP $FA00

$C2/FA00

AF 00 FC 7E LDA $7EFC00   ;load monster's mortal status
89 C0 00    BIT #$00C0	  ;check if dead
F0 3F       BEQ $3F	  ;branch if not dead
AF 80 FC 7E LDA $7EFC80
89 C0 00    BIT #$00C0
F0 36       BEQ $36
AF 00 FD 7E LDA $7EFD00
89 C0 00    BIT #$00C0
F0 2D       BEQ $2D
AF 80 FD 7E LDA $7EFD80
89 C0 00    BIT #$00C0
F0 24       BEQ $24
AF 00 FE 7E LDA $7EFE00
89 C0 00    BIT #$00C0
F0 1B       BEQ $1B
AF 80 FE 7E LDA $7EFE80
89 C0 00    BIT #$00C0
F0 12       BEQ $12
AF 00 FF 7E LDA $7EFF00
89 C0 00    BIT #$00C0
F0 09       BEQ $09
AF 80 FF 7E LDA $7EFF80
89 C0 00    BIT #$00C0
D0 28       BNE $28

AF F0 FF 7F LDA $7EFFF0   ;load one-time limit flag
C9 01 00    CMP #$0001    ;check if second turn
F0 1F       BEQ $1F       ;branch if at second turn

A6 C8       LDX $C8       ;load current character slot to X
BF 1E 00 7E LDA $7E001E,x ;load equipped accessory from X
C9 A7 00    CMP #$00A7    ;check if Relay Flag
D0 14       BNE $14       ;branch if not

BF 44 00 7E LDA $7E0044,x ;load turn
09 10 00    ORA #$0010    ;set double-turn bit
9F 44 00 7E STA $7E0044,x 

A9 01 00    LDA #$0001    ;set one-time limit flag
8F F0 FF 7F STA $7FFFF0
80 07       BRA $07

A9 FF FF    LDA #$FFFF    ;null one-time limit flag
8F F0 FF 7F STA $7FFFF0

A6 54       LDX $54
20 5A A3    JSR $A35A
4C 8F A0    JMP $A08F


KURIBO'S SHOE
-------------
ORIG:	C0/14F6	A0 6C 00    LDY #$006C
		80 03       BRA $03
NEW:	C0/14F6	5C A0 FA C2 JMP $C2FAA0
		EA          NOP

$C2/FAA0

AF 0E F8 7F LDA $7FF80E   ;load Mario's equipped accessory
C9 AA       CMP #AA       ;check if Kuribo's Shoe
F0 20       BEQ $20       ;branch if it is
AF 22 F8 7F 
C9 AA 
F0 18 
AF 36 F8 7F 
C9 AA 
F0 10 
AF 4A F8 7F 
C9 AA 
F0 08 
AF 5E F8 7F 
C9 AA 
D0 07 

A0 D8 00    LDY #$00D8    ;load extended jumping height
5C FE 14 C0 JMP $C014FE   ;return to code

A0 6C 00    LDY #$006C    ;load original jumping height
5C FE 14 C0 JMP $C014FE   ;return to code


RUBBER SHOES
------------
(1st range)

ORIG: C2/6713	A0 01 00    LDY #$0001
NEW : C2/6713	4C 00 FB    JMP $FB00

$C2/FB00

AE 50 07    LDX $0750     ;load current character slot to X
BF 1E 00 7E LDA $7E001E,x ;load equipped accessory
29 FF 00    AND #$00FF    ;isolate
C9 A8 00    CMP #$00A8    ;check if Rubber Shoes
F0 06       BEQ $06       ;branch if it is

A0 01 00    LDY #$0001 
4C 16 67    JMP $6716

A0 01 00    LDY #$0001
A9 1E 00    LDA #$001E    ;load 30 frame range
4C 18 67    JMP $6718

(2nd range)

ORIG: C2/672D	A0 02 00    LDY #$0002
NEW : C2/672D	4C 30 FB    JMP $FB30

$C2/FB30

AE 50 07    LDX $0750
BF 1E 00 7E LDA $7E001E,x
29 FF 00    AND #$00FF
C9 A8 00    CMP #$00A8
F0 06       BEQ $06

A0 02 00    LDY #$0002
4C 30 67    JMP $6730

A0 02 00    LDY #$0002
A9 00 1E    LDA #$001E
4C 32 67    JMP $6732


PYRO GLOVES
-----------
(maximum # of fireballs)

$C2/FB70

AF 0E F8 7F LDA $7FF80E
C9 AD 00    CMP #$00AD
D0 0B       BNE $0B
A9 40 00    LDA #$0040
85 E2       STA $E2
20 B2 29    JSR $29B2
4C 7F 2C    JMP $2C7F
B7 60       
85 E2 
20 B2 29 
4C 7F 2C 

(1st range between fireballs)

$C2/FB90

AF 0E F8 7F 
C9 AD 00 
D0 0A 
A9 04 00 
9F 06 00 40 
4C 5F 0C 
A9 07 00 
9F 06 00 40 
4C 5F 0C 

(2nd range)

$C2/FBC0

AF 0E F8 7F 
C9 AD 00 
D0 0A 
A9 04 00 
1A 
0A 
85 E0 
4C B7 67 
A9 07 00 
1A 
0A 
85 E0 
4C B7 67 


RELAY FLAG (check if monsters are dead)
---------------------------------------
$C2/FC00

AF 00 FC 7E 
89 C0 00 
F0 53 
AF 80 FC 7E 
89 C0 00 
F0 4A 
AF 00 FD 7E 
89 C0 00 
F0 41 
AF 80 FD 7E 
89 C0 00 
F0 38 
AF 00 FE 7E 
89 C0 00 
F0 2F 
AF 80 FE 7E 
89 C0 00 
F0 26 
AF 00 FF 7E 
89 C0 00 
F0 1D 
AF 80 FF 7E 
89 C0 00 
D0 06 
20 DF 07 
4C 1A 27 
AE 04 07 
BD 50 07 
AA 
BF 44 00 7E 
29 EF 00 
9F 44 00 7E 
20 DF 07 
4C 1A 27 


RELAY FLAG (the running part)
-----------------------------
$C2/FC80

29 07 
F0 04 
5C 01 B8 C0 
E0 00 60 
D0 46 
AF 0E F8 7F 
C9 A7 
F0 20 
AF 22 F8 7F 
C9 A7 
F0 18 
AF 36 F8 7F 
C9 A7 
F0 10 
AF 4A F8 7F 
C9 A7 
F0 08 
AF 5E F8 7F 
C9 A7 
D0 12 
AF 0D F8 7F 
C9 95 
D0 04 
A9 10 
80 02 
A9 20 
5C 2F B8 C0 
AF 0E F8 7F 
C9 95 
D0 04 
A9 08 
80 02 
A9 10 
5C 2F B8 C0 


CEMENT CAP
----------
(Mario changes to grey when entering an area)

$C2/FD00

AF 0E F8 7F 
29 FF 00 
C9 95 00 
D0 14 
B5 00 
C9 98 79 
D0 03 
69 1D 00 
AA 
C8 
C8 
A9 1D 00 
5C EC 87 C0 
B5 00 
AA 
C8 
C8 
A9 1D 00 
5C EC 87 C0 

(disable object interaction)

$C2/FD40

AF 0E F8 7F 
C9 95 
D0 10 
B5 59 
29 F0 
C9 80 
F0 08 
A9 00 
85 80 
5C 2C CD C9 
B5 59 
29 F0 
5C 2C CD C9 

(Mario changes grey when closing menu after equipping item)

$C2/FD70

AF 0E F8 7F 
29 FF 00 
C9 95 00 
D0 13 
A0 02 21 
A2 B6 79 
A9 1D 00 
54 7E E5 
E2 20 
AB 
5C 75 08 C0 
A0 02 21 
A2 98 79 
A9 1D 00 
54 7E E5 
E2 20 
AB 
5C 75 08 C0 

(Mario can walk on molten lava)

$C2/FDC0

C0 0B 40 
D0 11 
AF 0E F8 7F 
29 FF 00 
C9 95 00 
D0 05 
08 
5C B9 C1 C0 
B5 00 
D9 00 00 
08 
5C B7 C1 C0 


EXIT FIELDS
-----------
Mario's Pipehouse (1D3AD6)
10 A0 81 11 00 0C 22 61 81 
24 A1 82 07 04 06 6F 60 81 

Rooms 1-4 (1D72E0)
25 A1 04 69 05 05 58 E1 81 

24 A1 04 59 01 04 6A 63 81 
27 A1 01 4C 01 06 2F A1 01 
26 A1 07 49 0A 18 25 A3 01 

25 A1 18 26 02 08 49 28 01 
27 A1 0C 1C 06 09 1A 66 81 

25 A1 07 30 A1 01 4D 21 01 
26 A1 09 17 06 0D 1C E5 81 
28 A1 01 19 0B 0C 1D A6 01 

LAYOUTS
-------
4D FE 81 2E 0F 3A 00 00 00 00 00 00 00 00 00 00 00 00 
4D FE 80 19 1A 2D 00 00 00 00 00 00 00 00 00 00 00 00 
4D FE 96 00 33 17 00 00 00 00 00 00 00 00 00 00 00 00 
4D FE 81 00 14 18 00 00 00 00 00 00 00 00 00 00 00 00 
