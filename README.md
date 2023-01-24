 Exp-6-Synchornous-counters - up counter and down counter 
 AIM: To implement 4 bit up and down counters and validate  functionality.
 HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
 SOFTWARE REQUIRED:   Quartus prime
 THEORY 

 UP COUNTER 
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



 DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
 Procedure
1.Create module projectname(input ,output) to start the verilog programming.

2.create a if loop condition to increase the count in counter_up function.

3.Similarly, create another loop for the down counter.

4.End the verilog program using keyword endmodule.

5.Get the timing diagram and RTL realization diagram for respective Counters.
/* write all the steps invloved */



 PROGRAM 

Up counter :
module uc(input clk,input reset,output[0:3]counter);

reg[0:3] counter_up;

always@(posedge clk or posedge reset)

begin

if(reset)

counter_up<=4'd0;

else

counter_up<=counter_up+4'd1;

end

assign counter=counter_up;

endmodule

Down counter:

module dc(input clk,input reset,output[0:3]counter);

reg[0:3] counter_down;

always@(posedge clk or posedge reset)

begin

if(reset)

counter_down<=4'd0;

else

counter_down<=counter_down-4'd1;

end

assign counter=counter_down;

endmodule






Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: J.B.Viniya
RegisterNumber: 22008831







 RTL LOGIC UP COUNTER AND DOWN COUNTER  





![Screenshot (31)](https://user-images.githubusercontent.com/121683551/214357116-86cae843-324f-416f-a1d0-551430f9f1d0.png)



![Screenshot (32)](https://user-images.githubusercontent.com/121683551/214357219-46258ab1-c548-4bf3-8894-bc5858e485a4.png)

 TIMING DIGRAMS FOR COUNTER  



![Screenshot (33)](https://user-images.githubusercontent.com/121683551/214357312-e20c37ba-dbba-428e-b1ee-895703e5aa02.png)


 TRUTH TABLE 



![Screenshot (34)](https://user-images.githubusercontent.com/121683551/214357445-713a93c9-2d0e-487b-9461-66b0eb7ed43d.png)


![Screenshot (35)](https://user-images.githubusercontent.com/121683551/214357508-4ae73554-69b2-4fd0-aba0-098c12abf413.png)

 RESULTS 
