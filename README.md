# Exp-6-Synchornous-counters - up counter and down counter 
### AIM:To implement 4 bit up and down counters and validate  functionality.
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

1.Create a new project in QuartusII software.

2.Name the project as uc for upcounter and dc for down counter. 

3.Create a new verilog hdl file in the project file. 

4.Name the module as dc and uc for down counter and up counter. 

5.Within the module declare input and output variables. 

6.Create a loop using if-else with condition parameter as reset value. 

7.End the loop. 

8.End the module.

### PROGRAM 

Program for flipflops  and verify its truth table in quartus using Verilog programming.

Developed by: E.Kamalesh

RegisterNumber: 212222100019

#### UP COUNTER
```
module sync(clk,A);
input clk;
output reg [0:2]A;
always@(posedge clk)
begin
    A[0]=(((A[1])&(A[2]))^A[0]);
	 A[1]=(A[2])^(A[1]);
	 A[2]=1^A[2];
end 
endmodule
```
#### DOWN COUNTER
```
module exp6a(clk,A);
input clk;
output reg [0:2]A;
always@(posedge clk)
begin
    A[0]=(((~A[1])&(~A[2]))^(A[0]));
	 A[1]=(~A[2])^(A[1]);
	 A[2]=1^A[2];
end 
endmodule 
```
### RTL LOGIC UP COUNTER AND DOWN COUNTER  

#### UP COUNTER
![242543316-d6f15412-afd6-4cc6-9acb-71b9cbb948f1](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/0256856b-977b-498b-93f7-a4ed336a630b)



#### DOWN COUNTER
![242543621-8220be78-da1b-4e46-b38c-d4018e2cd6a0](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/33a56d3d-24d0-4ead-883c-ff4b845d1caa)


### TIMING DIGRAMS FOR COUNTER  

#### UP COUNTER
![242543767-bc0090bc-bd2d-429f-b8fd-26a979742ef0](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/5b6bd309-e0a6-4ff9-82a3-0667fe6551bd)

#### DOWN COUNTER
![242543962-647beabe-25df-42ad-a174-afe29c526bc7](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/261c48d5-ca70-41cc-acbe-1b64b6b0e0ce)



### TRUTH TABLE 

#### UP COUNTER
![242544421-00b10a18-f220-4cae-8fe4-26d86c120eaf](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/93f92215-2396-49fc-ac92-1d7e82bf5389)

#### DOWN COUNTER
![242547948-b4c938b8-53ca-4e54-8741-e15551defd78](https://github.com/kamalesh2509/Exp-7-Synchornous-counters-/assets/120444689/e21da70a-8553-4edc-9e74-dc171f6a1bb2)



### RESULTS 
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
