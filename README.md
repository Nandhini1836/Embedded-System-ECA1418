ECA14 – EMBEDDED SYSTEMS LAB

Experiment 1 – Flashing of LED Using AT89C51 Microcontroller Using Proteus
ORG 0000H
UP: SETB P2.0
    ACALL DELAY
    CLR P2.0
    ACALL DELAY
    SJMP UP
DELAY: MOV R4,#35
H1: MOV R3,#255
H2: DJNZ R3,H2
    DJNZ R4,H1
    RET
END

Experiment 2 – Generation of Square Wave Using Proteus
ORG 0000H
UP: SETB P2.0
    ACALL DELAY
    CLR P2.0
    ACALL DELAY
    SJMP UP
DELAY: MOV R4,#35
H1: MOV R3,#255
H2: DJNZ R3,H2
    DJNZ R4,H1
    RET
END

Experiment 3 – Stepper Motor Using AT89C51 Using Proteus
ORG 0000H
UP: MOV P2,#09H
    ACALL DELAY
    MOV P2,#0CH
    ACALL DELAY
    MOV P2,#06H
    ACALL DELAY
    MOV P2,#03H
    ACALL DELAY
    SJMP UP
DELAY: MOV R4,#18
H1: MOV R3,#255
H2: DJNZ R3,H2
    DJNZ R4,H1
    RET
END
Important sequence to remember:
09H → 0CH → 06H → 03H → Repeat

Experiment 4 – 7 Segment Display Using AT89C51 Using Proteus
ORG 000H
UP: MOV P2,#0C0H
    ACALL DELAY
    MOV P2,#0F9H
    ACALL DELAY
    MOV P2,#0A4H
    ACALL DELAY
    MOV P2,#0B0H
    ACALL DELAY
    MOV P2,#99H
    ACALL DELAY
    MOV P2,#92H
    ACALL DELAY
    MOV P2,#82H
    ACALL DELAY
    MOV P2,#0F8H
    ACALL DELAY
    MOV P2,#80H
    ACALL DELAY
    MOV P2,#90H
    ACALL DELAY
DELAY: MOV R5,#10
H1: MOV R4,#180
H2: MOV R3,#255
H3: DJNZ R3,H3
    DJNZ R4,H2
    DJNZ R5,H1
    RET
END
Important values to remember:
0 → C0H
1 → F9H
2 → A4H
3 → B0H
4 → 99H
5 → 92H
6 → 82H
7 → F8H
8 → 80H
9 → 90H

Experiment 5 – Arduino Based Manual Electronic Counter Using Proteus
int x0,x1,x2,x3,x4,x5,x6,x7,x8,x9;
int delay_time=200;

void setup() {
  pinMode(12, INPUT_PULLUP);
  pinMode(1,OUTPUT);
  pinMode(2,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
}

void loop() {

  int sensorVal = digitalRead(12);

  if (sensorVal == LOW) {
    x0=true;
  }

  while(x0){
    zero();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x1=true;
      x0=false;
    }
  }

  while(x1){
    one();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x2=true;
      x1=false;
    }
  }

  while(x2){
    two();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x3=true;
      x2=false;
    }
  }

  while(x3){
    three();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x4=true;
      x3=false;
    }
  }

  while(x4){
    four();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x5=true;
      x4=false;
    }
  }

  while(x5){
    five();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x6=true;
      x5=false;
    }
  }

  while(x6){
    six();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x7=true;
      x6=false;
    }
  }

  while(x7){
    seven();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x8=true;
      x7=false;
    }
  }

  while(x8){
    eight();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x9=true;
      x8=false;
    }
  }

  while(x9){
    nine();
    sensorVal = digitalRead(12);

    if (sensorVal == LOW) {
      x0=true;
      x9=false;
    }
  }
}

void zero()
{
  for(int i=1;i<7;i++)
  {
    digitalWrite(i,HIGH);
  }
  digitalWrite(7,LOW);
  delay(delay_time);
}

void one()
{
  digitalWrite(1,LOW);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
  digitalWrite(6,LOW);
  digitalWrite(7,LOW);
  delay(delay_time);
}

void two()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,HIGH);
  digitalWrite(3,LOW);
  digitalWrite(4,HIGH);
  digitalWrite(5,HIGH);
  digitalWrite(6,LOW);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void three()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,HIGH);
  digitalWrite(5,LOW);
  digitalWrite(6,LOW);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void four()
{
  digitalWrite(1,LOW);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void five()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,LOW);
  digitalWrite(3,HIGH);
  digitalWrite(4,HIGH);
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void six()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,LOW);
  digitalWrite(3,HIGH);
  digitalWrite(4,HIGH);
  digitalWrite(5,HIGH);
  digitalWrite(6,HIGH);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void seven()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
  digitalWrite(6,LOW);
  digitalWrite(7,LOW);
  delay(delay_time);
}

void eight()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,HIGH);
  digitalWrite(5,HIGH);
  digitalWrite(6,HIGH);
  digitalWrite(7,HIGH);
  delay(delay_time);
}

void nine()
{
  digitalWrite(1,HIGH);
  digitalWrite(2,HIGH);
  digitalWrite(3,HIGH);
  digitalWrite(4,HIGH);
  digitalWrite(5,LOW);
  digitalWrite(6,HIGH);
  digitalWrite(7,HIGH);
  delay(delay_time);
}


Experiment 6 – Arduino to 16x2 LCD Display Using Proteus
#include <LiquidCrystal.h>
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);
void setup()
{
  lcd.begin(16, 2);
  lcd.print("put your message here");
}
void loop()
{
  for (int i=0; i<13; i++)
  {
    lcd.scrollDisplayLeft();
    delay(700);
  }
}
Remember:
LCD → 16 columns × 2 rows
Pins → 7, 8, 9, 10, 11, 12
Scroll delay → 700 ms

Experiment 7 – Serial Communication Using Arduino with Proteus
void setup()
{
  Serial.begin(9600);
}

int number = 0;

void loop()
{
  Serial.print("Number is ");
  Serial.println(number);
  delay(500);
  number++;
}

Experiment 8 – Gas Sensor MQ-2 in Proteus Using Arduino
#define GreenLed 13
#define Sensor A0
void setup()
{
  pinMode(13,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(A0,INPUT);
  Serial.begin(9600);
}
void loop()
{
  int value = analogRead(A0);
  Serial.print("Analogic Value coming from the sensor : ");
  Serial.println(value);
  delay(100);
  if(value>600)
  {
    digitalWrite(13,HIGH);
  }
  else
  {
    digitalWrite(13,LOW);
  }

  delay(20);
}

Experiment 9 – Ultrasonic Sensor in Proteus Using Arduino
int trig = 10;
int echo = 9;
long duration;
int cm;
void setup() {
pinMode(trig, OUTPUT);
pinMode(echo, INPUT);
Serial.begin(9600);
}
void loop() {
digitalWrite(trig, LOW);
delayMicroseconds(10);
digitalWrite(trig, HIGH);
delayMicroseconds(10);
digitalWrite(trig, LOW);
delayMicroseconds(10);
duration = pulseIn(echo, HIGH);
cm = (duration/2) * 0.034;
Serial.print(" Distance = ");
Serial.print(cm);
Serial.println(" cm");
}


Experiment 10 – PIR Sensor in Proteus Using Arduino
int Status = 13;
int sensor = 12;
void setup() {
Serial.begin(9600);
pinMode(sensor, INPUT);
pinMode(Status, OUTPUT);
}
void loop() {
long state = digitalRead(sensor);
Serial.println(state);
if(state == HIGH) {
digitalWrite(Status, HIGH);
Serial.println("Motion detected!");
delay(1000);
}
else {
digitalWrite(Status, LOW);
Serial.println("Motion absent!");
delay(1000);
}
}


Experiment 11 – Study of GPIO & Bit Addressing in AT89C51
#include <reg51.h>
sbit LED1 = P1^0;
sbit LED2 = P1^1;
void delay()
{
unsigned int i,j;
for(i=0;i<200;i++)
for(j=0;j<1000;j++);
}
void main()
{
while(1)
{
LED1 = 1;
LED2 = 0;
delay();
LED1 = 0;
LED2 = 1;
delay();
}
}


Experiment 12 – Embedded C Program to Multiply Two 16-Bit Binary Numbers
#include <reg51.h>
void main()
{
while(1)
{
unsigned int num1,num2;
unsigned long int product;
num1=0x2222;
num2=0xBBBB;
product=(unsigned long int)num1*num2;
P0=product&0xff;
P1=(product&0xff00)>>8;
P2=(product&0xff0000)>>16;
P3=(product&0xff000000)>>24;
}
}


Experiment 13 – Embedded C Program to Add an Array of 16-Bit Numbers and Store the 32-Bit Result in Internal RAM

#include <reg51.h>
void main(void)
{
unsigned int i;
unsigned int array[5]={0x1111,0x2222,0x8888,0x4444,0xABCD};
unsigned long sum=0;
for(i=0;i<5;i++)
{
sum=sum+array[i];
}
P0=(unsigned char)(sum&0xFF);
P1=(unsigned char)((sum>>8)&0xFF);
P2=(unsigned char)((sum>>16)&0xFF);
while(1);
}


Experiment 14 – Embedded C Program to Display "Hello World" Message
#include <reg51.h>
#include <stdio.h>
void main(void)
{
SCON=0x50;
TMOD=0x20;
TH1=0xFD;
TR1=1;
TI=1;
while(1)
{
printf("Hello World ! \n");
}
}


Experiment 15 – Embedded C Program to Convert Hexadecimal Data to Decimal and Display the Digits on Ports P0, P1 and P2

The manual heading says 0xCFH, but the printed program contains inconsistent code (0x08 and an invalid/incomplete-looking conversion sequence).

A clean Keil C version for converting 0xCF = 207 into decimal digits is:

#include <reg51.h>
void main(void)
{
unsigned char hexa=0xCF;
unsigned char hundreds,tens,units;
hundreds=hexa/100;
tens=(hexa/10)%10;
units=hexa%10;
P0=units;
P1=tens;
P2=hundreds;
while(1);
}


Experiment 16 – Serial Interrupt Using UART (Keyboard Input) in Keil
#include <reg51.h>
#include <stdio.h>
void serial_ISR(void) interrupt 4
{
char ch;
if(RI)
{
RI=0;
ch=SBUF;
printf("\n>>> INTERRUPT RECEIVED: ");
printf("%c\n",ch);
}
}
void delay(void)
{
unsigned int i;
for(i=0;i<50000;i++);
}
void main(void)
{
SCON=0x50;
TMOD=0x20;
TH1=0xFD;
TR1=1;
IE=0x90;
TI=1;
while(1)
{
printf("Hello World\n");
delay();
}
}


Experiment 17 – UART Interfacing Using Interrupt in Keil
#include <reg51.h>
void serial_ISR(void) interrupt 4
{
if(RI)
{
P1=SBUF;
RI=0;
}
}
void main()
{
TMOD=0x20;
TH1=0xFD;
SCON=0x50;
TR1=1;
ES=1;
EA=1;
while(1);
}


Experiment 18 – Generation of PWM Using Timer Interrupt
#include <reg51.h>
sbit PWM=P1^0;
unsigned char count=0;
unsigned char duty=100;
void timer0_ISR(void) interrupt 1
{
TH0=0xFC;
TL0=0x66;
count++;
if(count<duty)
PWM=1;
else
PWM=0;
if(count>=200)
count=0;
}
void main()
{
TMOD=0x01;
TH0=0xFC;
TL0=0x66;
IE=0x82;
TR0=1;
while(1);
}



Experiment 19 – Blinking LEDs Using Software Delay Routine in LPC2148 Kit
#include "lpc214x.h"
void delay(unsigned int k);
void main(void)
{
IODIR0=0xFFFFFFFF;
PINSEL0=0;
while(1)
{
IOSET0=0x0000ff00;
delay(1000);
IOCLR0=0x0000ff00;
delay(1000);
}
}
void delay(unsigned int k)
{
unsigned int i,j;
for(j=0;j<k;j++)
for(i=0;i<=800;i++);
}



Experiment 20 – Program to Read the Switch and Display in the LEDs Using LPC2148 Kit
#include "lpc214x.h"
int main(void)
{
unsigned int sw_sts;
IODIR0=0x0000ff00;
PINSEL0=0;
while(1)
{
sw_sts=IOPIN0;
IOSET0=0x0000ff00;
IOCLR0=sw_sts>>8;
}
}



Experiment 21 – Display a Number in Seven Segment LED in LPC2148 Kit
#include <LPC214X.H>
#define DS3 1<<13
#define DS4 1<<12
#define SEG_CODE 0xFF<<16
unsigned char const seg_dat[]={0x3F,0x6,0x5B,0x4F,0x66,0x6D,0x7D,0x7,0x7F,0x67};
void delayms(int n)
{
int i,j;
for(i=0;i<n;i++)
{for(j=0;j<5035;j++);}
}
int main(void)
{
unsigned char count;
PINSEL0=0;
PINSEL1=0;
IODIR0=SEG_CODE|DS3|DS4;
IOSET0=SEG_CODE|DS3;
IOCLR0=DS4;
count=0;
IOCLR0=SEG_CODE;
IOSET0=seg_dat[count]<<16;
while(1)
{
delayms(1000);
count++;
if(count>9) count=0;
IOCLR0=SEG_CODE;
IOSET0=seg_dat[count]<<16;
}
}



Experiment 22 – Serial Transmission and Reception Using On-Chip UART in LPC2148 Kit
#include <lpc214x.h>
void UART0_Init(void)
{
PLL0CON=0;
PLL0FEED=0xAA;
PLL0FEED=0x55;
VPBDIV=1;
PINSEL0|=0x5;
U0FCR=0;
U0LCR=0x83;
U0DLL=0x27;
U0DLM=0;
U0LCR=3;
}
void sout(unsigned char dat1)
{
while(!(U0LSR&0x20));
U0THR=dat1;
}
int main(void)
{
int dat;
UART0_Init();
do
{
if(U0LSR&1)
{
dat=U0RBR;
sout(dat);
}
}while(1);
}


Experiment 23 – Access an Internal ADC and Display the Binary Output in LEDs in LPC2148 Kit
#include <LPC214X.H>
#define LEDS 0xFF<<8
#define AD0_1 1<<24
#define CLK_DIV 1<<8
#define PDN 1<<21
#define SOC 1<<24
#define BURST 1<<16
#define DONE 1<<31
void delay(unsigned int k)
{
unsigned int i,j;
for(j=0;j<k;j++)
for(i=0;i<=800;i++);
}
void adc_init()
{
unsigned long int ADC_CH;
ADC_CH=0|1<<1;
AD0CR=SOC|PDN|CLK_DIV|ADC_CH|BURST;
}
unsigned int adc_read(unsigned char channel)
{
unsigned int aval;
unsigned long int val;
if(channel==1) val=AD0DR1;
else if(channel==2) val=AD0DR2;
else if(channel==3) val=AD0DR3;
val=val>>6;
val=val&0x3FF;
aval=val;
return aval;
}
int main(void)
{
unsigned int tp1;
IODIR0=LEDS;
PINSEL0=0;
PINSEL1=0|AD0_1;
adc_init();
do
{
tp1=adc_read(1);
tp1=tp1>>2;
IOSET0=LEDS;
IOCLR0=tp1<<8;
delay(1000);
}while(1);
}



Experiment 24 – Modeling Clock-Driven Concurrent Processes Using SC_THREAD and wait() in SystemC
#include <systemc.h>
SC_MODULE(ClockExample)
{
sc_in<bool> clk;
void process()
{
while(true)
{
wait();
std::cout<<"Time: "<<sc_time_stamp()<<" - Clock Triggered"<<std::endl;
}
}
SC_CTOR(ClockExample)
{
SC_THREAD(process);
sensitive<<clk.pos();
}
};
int sc_main(int argc,char* argv[])
{
sc_clock clock("clock",1,SC_NS);
ClockExample module("module");
module.clk(clock);
sc_start(5,SC_NS);
return 0;
}


Experiment 25 – Producer–Consumer Problem Using SystemC
#include <systemc.h>
SC_MODULE(Producer) {
sc_fifo_out<int> out;
void produce() {
for(int i=1;i<=5;i++) {
cout<<"Produced: "<<i<<endl;
out.write(i);
wait(1,SC_SEC);
}
}
SC_CTOR(Producer) {
SC_THREAD(produce);
}
};
SC_MODULE(Consumer) {
sc_fifo_in<int> in;
void consume() {
int value;
while(true) {
in.read(value);
cout<<"Consumed: "<<value<<endl;
wait(1,SC_SEC);
}
}
SC_CTOR(Consumer) {
SC_THREAD(consume);
}
};
int sc_main(int argc,char* argv[]) {
sc_fifo<int> fifo(5);
Producer producer("Producer");
Consumer consumer("Consumer");
producer.out(fifo);
consumer.in(fifo);
sc_start(10,SC_SEC);
return 0;
}



Experiment 26 – Transaction Level Modeling (TLM) Using SystemC
#include <systemc>
#include <tlm>
#include <tlm_utils/simple_initiator_socket.h>
#include <tlm_utils/simple_target_socket.h>
using namespace sc_core;
using namespace tlm;
using namespace std;
struct Target:sc_module {
tlm_utils::simple_target_socket<Target> socket;
SC_CTOR(Target):socket("socket") {
socket.register_b_transport(this,&Target::b_transport);
}
void b_transport(tlm_generic_payload& trans,sc_time& delay) {
int* data=(int*)trans.get_data_ptr();
cout<<"Target received: "<<*data<<endl;
delay+=sc_time(10,SC_NS);
}
};
struct Initiator:sc_module {
tlm_utils::simple_initiator_socket<Initiator> socket;
SC_CTOR(Initiator):socket("socket") {
SC_THREAD(thread_process);
}
void thread_process() {
tlm_generic_payload trans;
sc_time delay=SC_ZERO_TIME;
int data=555;
trans.set_data_ptr(reinterpret_cast<unsigned char*>(&data));
trans.set_data_length(sizeof(data));
cout<<"Initiator sending: "<<data<<endl;
socket->b_transport(trans,delay);
wait(delay);
}
};
int sc_main(int argc,char* argv[]) {
Initiator initiator("initiator");
Target target("target");
initiator.socket.bind(target.socket);
sc_start();
return 0;
}

Experiment 27 – Binary Semaphore in SystemC
#include <systemc.h>
SC_MODULE(binary_semaphore) {
int sem;
sc_event ev;
void task1() {
while(true) {
wait(1,SC_SEC);
if(sem==1) {
sem=0;
cout<<"Task1 Entered Critical Section at "<<sc_time_stamp()<<endl;
wait(2,SC_SEC);
sem=1;
ev.notify();
}
else {
wait(ev);
}
}
}
void task2() {
while(true) {
wait(2,SC_SEC);
if(sem==1) {
sem=0;
cout<<"Task2 Entered Critical Section at "<<sc_time_stamp()<<endl;
wait(1,SC_SEC);
sem=1;
ev.notify();
}
else {
wait(ev);
}
}
}
SC_CTOR(binary_semaphore) {
sem=1;
SC_THREAD(task1);
SC_THREAD(task2);
}
};
int sc_main(int argc,char* argv[]) {
binary_semaphore obj("Binary_Semaphore");
sc_start(10,SC_SEC);
return 0;
}



Experiment No. 28 – Counting Semaphore in SystemC
#include <systemc.h>
SC_MODULE(counting_semaphore) {
int sem;
void task() {
while(true) {
wait(1,SC_SEC);
if(sem>0) {
sem--;
cout<<"Task Accessing Resource at "<<sc_time_stamp()<<" Remaining: "<<sem<<endl;
wait(2,SC_SEC);
sem++;
}
}
}
SC_CTOR(counting_semaphore) {
sem=2;
SC_THREAD(task);
SC_THREAD(task);
SC_THREAD(task);
}
};
int sc_main(int argc,char* argv[]) {
counting_semaphore obj("Counting");
sc_start(10,SC_SEC);
return 0;
}
