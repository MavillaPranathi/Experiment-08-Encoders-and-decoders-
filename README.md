# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
/* write all the steps invloved */



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
```
Developed by: m.pranathi
RegisterNumber: 212222240064
*/
MULTIPLEXER

module nmux(a,s,y);
input[3:0]a;
input[1:0]s;
output reg y;
always @ (a,s)
begin
case(s)
   2'b00:y=a[0];
   2'b01:y=a[1];
   2'b10:y=a[2];
   2'b11:y=a[3];
endcase
end
endmodule

DEMULTIPLEXER

module dmux(input in, input [1:0] sel, output reg [3:0] out);
  always @(in or sel) begin
    case(sel)
      2'b00: out = 4'b0001;
      2'b01: out = 4'b0010;
      2'b10: out = 4'b0100;
      2'b11: out = 4'b1000;
      default: out = 4'b0000; // Default case
    endcase
  end
endmodule

```
### RTL LOGIC  

MULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/47e611ee-b616-4a62-b308-bb64cd19b095)

DEMULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/c0d569f2-04cb-4183-b88a-a06ded526550)

### TIMING DIGRAMS  

MULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/f80f3990-0d12-43ec-aee2-77c86498ef98)

DEMULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/489900f6-13ec-4b98-8c6e-c8ff8b60ae41)

### TRUTH TABLE 

MULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/15696d5d-4643-40f2-be79-72286cfd10c1)

DEMULTIPLEXER

![image](https://github.com/varsha-2005/Exercise-07-Multiplexer-and-De-multiplexer/assets/119288183/427d79fe-98ad-4b7f-9825-421cc9b12cdd)

### RESULTS 
Therefore multiplexer and demultiplexer is executed successfully.
