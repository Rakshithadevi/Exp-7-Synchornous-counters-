# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
```
1. Create module projectname(input ,output) to start the verilog programming.
2. create a if loop condition to increase the count in counter_up function.
3. Similarly, create another loop for the down counter.
4. End the verilog program using keyword endmodule.
5. Get the timing diagram and RTL realization diagram for respective Counters.
```

### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: 
RegisterNumber:  
*/
```
### up counter:
```
```
module uc(input CLK,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule
```
```
### down counter:
```
```
module dc(input CLK,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge CLK or posedge reset)
begin
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule
```



### UP COUNTER:

### RTL LOGIC UP COUNTER :
![image](https://user-images.githubusercontent.com/94165326/169743046-8b6f9f9d-a45e-43cf-8bc5-3558c2ffdc95.png)











### TIMING DIGRAMS FOR COUNTER : 
![image](https://user-images.githubusercontent.com/94165326/169743159-f9b79ca9-b8be-4dda-a78a-a32050956bb2.png)
![image](https://user-images.githubusercontent.com/94165326/169743182-40bf9ec3-cbb9-48e4-98e7-3c9aff11b0c1.png)





### TRUTH TABLE:
![image](https://user-images.githubusercontent.com/94165326/169743095-ea914803-542d-4dfc-bb43-237c4c8f43fe.png)



### DOWN COUNTER:


### RTL LOGIC DOWN COUNTER  :
![image](https://user-images.githubusercontent.com/94165326/169743212-003249e1-a71f-4667-9c56-63be0333e0da.png)

### TIMING DIGRAMS FOR COUNTER :
![image](https://user-images.githubusercontent.com/94165326/169743239-8c174197-8513-4df4-934e-c6549ce01f0e.png)
![image](https://user-images.githubusercontent.com/94165326/169743262-280be7a9-a927-4fb7-9f34-b7facb1ba66d.png)

### TRUTH TABLE:
![image](https://user-images.githubusercontent.com/94165326/169743295-2fe7cef3-f2fa-476c-a136-09ccca9735d6.png)








### RESULTS 
Thus 4 bit up and down counters is implemented and its functionality is validated.
