
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM
'''
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'U' 
WAIT:JNB TI, WAIT
CLR TI 
END


'''
### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'U' 
WAIT:JNB TI, WAIT
CLR TI 
END


```
### (ii) Serial Port to Transfer a Message

```
#include<reg51.h>
void main(void)
{
unsigned char msg[]="UDAI";
unsigned char i;
TMOD=0X20;//TIMER 1,MODE 2
TH1=0XFC;
SCON=0X40;
TR1=1;
for (i=0; i<17;i++)
{
SBUF= msg[i];
while(TI==0);
TI=0;
}
while(1);
}



```

### OUTPUT:

<img width="1656" height="653" alt="Screenshot 2025-10-14 220829" src="https://github.com/user-attachments/assets/d89b5fec-c643-4546-97a3-77e7d6327c88" />
<img width="1660" height="650" alt="image" src="https://github.com/user-attachments/assets/4fc9ffae-6a43-433b-81b3-1ad4e4247f7b" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
