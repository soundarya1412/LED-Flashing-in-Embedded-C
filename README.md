# LED-Flashing-in-Embedded-C
#include <lpc17xx.h> 
void delay(unsigned int ms)
{
unsigned int i,j;
for(i=0;i<ms;i++)
for(j=0;j<20000;j++);
}
int main() 
{
SystemInit(); 
10
1
LPC_GPIO2->FIODIR = 0x00000000; 
LPC_GPIO2->FIODIR = 0xffffffff; 
while(1)
{
LPC_GPIO2->FIOSET = 0xffffffff; 
delay (100);
LPC_GPIO2->FIOCLR = 0xffffffff; 
delay (100);
}
}
