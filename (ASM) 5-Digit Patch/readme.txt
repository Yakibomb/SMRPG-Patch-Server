HEXADECIMAL TO DECIMAL CONVERSION FOR BATTLE HP NUMERALS

C2/FA00 A9 00 00    LDA #$0000              
C2/FA03 85 D2       STA $D2    [$00:00D2]   
C2/FA05 85 D4       STA $D4    [$00:00D4]   
C2/FA07 85 D8       STA $D8    [$00:00D8]   
C2/FA09 A9 01 00    LDA #$0001              
C2/FA0C 8D 50 22    STA $2250  [$00:2250]   
C2/FA0F A5 D0       LDA $D0    [$00:00D0]   
C2/FA11 C9 10 27    CMP #$2710              
C2/FA14 30 18       BMI $18    [$FA2E]      
C2/FA16 8D 51 22    STA $2251  [$00:2251]   
C2/FA19 A9 10 27    LDA #$2710              
C2/FA1C 8D 53 22    STA $2253  [$00:2253]   
C2/FA1F A9 05 00    LDA #$0005              
C2/FA22 85 D8       STA $D8    [$00:00D8]   
C2/FA24 AD 06 23    LDA $2306  [$00:2306]   
C2/FA27 85 D3       STA $D3    [$00:00D3]   
C2/FA29 AD 08 23    LDA $2308  [$00:2308]   
C2/FA2C 85 D0       STA $D0    [$00:00D0]   
C2/FA2E C9 E8 03    CMP #$03E8              
C2/FA31 30 1C       BMI $1C    [$FA4F]      
C2/FA33 8D 51 22    STA $2251  [$00:2251]   
C2/FA36 A9 E8 03    LDA #$03E8              
C2/FA39 8D 53 22    STA $2253  [$00:2253]   
C2/FA3C A5 D8       LDA $D8    [$00:00D8]   
C2/FA3E D0 05       BNE $05    [$FA45]      
C2/FA40 A9 04 00    LDA #$0004              
C2/FA43 85 D8       STA $D8    [$00:00D8]   
C2/FA45 AD 06 23    LDA $2306  [$00:2306]   
C2/FA48 85 D3       STA $D3    [$00:00D3]   
C2/FA4A AD 08 23    LDA $2308  [$00:2308]   
C2/FA4D 85 D0       STA $D0    [$00:00D0]   
C2/FA4F C9 64 00    CMP #$0064              
C2/FA52 30 1C       BMI $1C    [$FA70]      
C2/FA54 8D 51 22    STA $2251  [$00:2251]   
C2/FA57 A9 64 00    LDA #$0064              
C2/FA5A 8D 53 22    STA $2253  [$00:2253]   
C2/FA5D A5 D8       LDA $D8    [$00:00D8]   
C2/FA5F D0 05       BNE $05    [$FA66]      
C2/FA66 AD 06 23    LDA $2306  [$00:2306]   
C2/FA69 85 D4       STA $D4    [$00:00D4]   
C2/FA6B AD 08 23    LDA $2308  [$00:2308]   
C2/FA6E 85 D0       STA $D0    [$00:00D0]   
C2/FA70 C9 0A 00    CMP #$000A              
C2/FA73 30 1C       BMI $1C    [$FA91]      
C2/FA75 8D 51 22    STA $2251  [$00:2251]   
C2/FA78 A9 0A 00    LDA #$000A              
C2/FA7B 8D 53 22    STA $2253  [$00:2253]   
C2/FA7E A5 D8       LDA $D8    [$00:00D8]   
C2/FA80 D0 05       BNE $05    [$FA87]      
C2/FA87 AD 06 23    LDA $2306  [$00:2306]   
C2/FA8A 85 D5       STA $D5    [$00:00D5]   
C2/FA8C AD 08 23    LDA $2308  [$00:2308]   
C2/FA8F 85 D0       STA $D0    [$00:00D0]   
C2/FA91 85 D6       STA $D6    [$00:00D6]   
C2/FA93 A5 D8       LDA $D8    [$00:00D8]   
C2/FA95 D0 05       BNE $05    [$FA9C]      
C2/FA9C A9 05 00    LDA #$0005              
C2/FA9F 38          SEC                     
C2/FAA0 E5 D8       SBC $D8    [$00:00D8]   
C2/FAA2 F0 0B       BEQ $0B    [$FAAF]      
C2/FAA4 3A          DEC A                   
C2/FAA5 9B          TXY                     
C2/FAA6 AA          TAX                     
C2/FAA7 B5 D2       LDA $D2,x  [$00:00D2]   
C2/FAA9 09 FF 00    ORA #$00FF              
C2/FAAC 95 D2       STA $D2,x  [$00:00D2]   
C2/FAAE BB          TYX                     
C2/FAAF A9 01 00    LDA #$0001              
C2/FAB2 8D 60 30    STA $3060  [$00:3060]   
C2/FAB5 60          RTS                     

CALL DECIMALS FROM SA-1 MIRROR

C2/FAD0 AD D2 30    LDA $30D2  [$00:30D2]   
C2/FAD3 95 00       STA $00,x  [$00:00D2]   
C2/FAD5 AD D4 30    LDA $30D4  [$00:30D4]   
C2/FAD8 95 02       STA $02,x  [$00:00D4]   
C2/FADA AD D6 30    LDA $30D6  [$00:30D6]   
C2/FADD 95 04       STA $04,x  [$00:00D6]   
C2/FADF AD D8 30    LDA $30D8  [$00:30D8]   
C2/FAE2 95 06       STA $06,x  [$00:00D8]   
C2/FAE4 60          RTS                     

SET TILE INDEXES FROM DECIMALS

C2/FB00 A5 66       LDA $66    [$00:0066]   
C2/FB02 9F 0C 00 40 STA $40000C,x[$40:320C] 
C2/FB06 AA          TAX                     
C2/FB07 A5 D2       LDA $D2    [$00:00D2]   
C2/FB09 9F 46 00 40 STA $400046,x[$40:2446] 
C2/FB0D A5 D4       LDA $D4    [$00:00D4]   
C2/FB0F 9F 48 00 40 STA $400048,x[$40:2448] 
C2/FB13 A5 D6       LDA $D6    [$00:00D6]   
C2/FB15 9F 4A 00 40 STA $40004A,x[$40:244A] 
C2/FB19 A5 D8       LDA $D8    [$00:00D8]   
C2/FB1B 9F 4C 00 40 STA $40004C,x[$40:244C] 
C2/FB1F BF 4F 00 40 LDA $40004F,x[$40:244F] 
C2/FB23 29 FE FF    AND #$FFFE              
C2/FB26 9F 4F 00 40 STA $40004F,x[$40:244F] 
C2/FB2A E6 60       INC $60    [$00:0060]   
C2/FB2C 4C 4F 0C    JMP $0C4F  [$00:0C4F]   

DAMAGE x17

C2/FE10 C2 20       REP #$20                
C2/FE12 A5 C2       LDA $C2    [$00:00C2]   
C2/FE14 F0 0C       BEQ $0C    [$FE22]      
C2/FE16 38          SEC                     
C2/FE17 E5 C4       SBC $C4    [$00:00C4]   
C2/FE19 F0 02       BEQ $02    [$FE1D]      
C2/FE1B 10 03       BPL $03    [$FE20]      
C2/FE1D A9 01 00    LDA #$0001              
C2/FE20 85 C2       STA $C2    [$00:00C2]   
C2/FE22 0A          ASL A                   
C2/FE23 0A          ASL A                   
C2/FE24 0A          ASL A                   
C2/FE25 0A          ASL A                   
C2/FE26 65 C2       ADC $C2    [$00:00C2]   
C2/FE28 85 C2       STA $C2    [$00:00C2]   
C2/FE2A E2 20       SEP #$20                
C2/FE2C 4C 93 C2    JMP $C293  [$00:C293]   

CLEAR 5th 'MISS' TILE

C2/FE50 A9 43 00    LDA #$0043              
C2/FE53 85 D6       STA $D6    [$00:00D6]   
C2/FE55 A9 10 00    LDA #$0010              
C2/FE58 4C A2 30    JMP $30A2  [$00:30A2]   

SET GREEN HEALING/BLUE PSYCHOPATH BIT FOR 5th TILE

C2/FE70 A9 10 10    LDA #$1010              
C2/FE73 04 D2       TSB $D2    [$00:00D2]   
C2/FE75 04 D4       TSB $D4    [$00:00D4]   
C2/FE77 04 D6       TSB $D6    [$00:00D6]   
C2/FE79 4C 6F 30    JMP $306F  [$00:306F]   

STORE 9999 to HP

C2/FE90 C2 20       REP #$20                
C2/FE92 A9 0F 27    LDA #$270F              
C2/FE95 8F 01 F8 7F STA $7FF801[$7F:F801]   
C2/FE99 8F 03 F8 7F STA $7FF803[$7F:F803]   
C2/FE9D 8F 15 F8 7F STA $7FF815[$7F:F815]   
C2/FEA1 8F 17 F8 7F STA $7FF817[$7F:F817]   
C2/FEA5 8F 29 F8 7F STA $7FF829[$7F:F829]   
C2/FEA9 8F 2B F8 7F STA $7FF82B[$7F:F82B]   
C2/FEAD 8F 3D F8 7F STA $7FF83D[$7F:F83D]   
C2/FEB1 8F 3F F8 7F STA $7FF83F[$7F:F83F]   
C2/FEB5 8F 51 F8 7F STA $7FF851[$7F:F851]   
C2/FEB9 8F 53 F8 7F STA $7FF853[$7F:F853]   
C2/FEBD 6B          RTL                     
