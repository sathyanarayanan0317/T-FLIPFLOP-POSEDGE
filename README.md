# T-FLIPFLOP-POSEDGE

**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/458a68fe-2d08-4a9d-ac4f-7ae0480ce0bd)

 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/cdd7fb32-539f-4b66-bb8d-f305a153c886)

 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**

/* write all the steps invloved */

~~~
1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.
~~~

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: RegisterNumber:
*/
~~~
module Tflipflop( input clk, rst_n, input t,
output reg q,
output q_bar
);
always@(posedge clk) 
begin // for synchronous reset
  //WRITE THE CONDITION OF TOGGLE FLIPFLOP HERE WITH RESET AND 
  //IMPLEMENT THE T LOGIC BY CONDITIONAL OPERATOR
if(!rst_n)
q<=0;
else 
begin
q<=(t?~q:q);
end
end
assign q_bar = ~q;
endmodule

Developed by : SATHYANARAYANAN M - 212224040300
~~~
**RTL LOGIC FOR FLIPFLOPS**


![329697108-61fd3809-f780-4197-8567-a2bc1e0d7e74](https://github.com/04Varsha/T-FLIPFLOP-POSEDGE/assets/149035374/dc18e2ee-f2c9-47c5-a373-bbea78e0ff03)

**TIMING DIGRAMS FOR FLIP FLOPS**

![329697143-2a9c5ea9-5f76-41ed-ad92-eaa4d4bfccc0](https://github.com/04Varsha/T-FLIPFLOP-POSEDGE/assets/149035374/3320aeff-f20e-477b-af67-a641267cbf27)

**RESULTS**
Thus the program executed successfully.
