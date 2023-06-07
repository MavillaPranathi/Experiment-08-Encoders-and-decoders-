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
ENCODER

module enc(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

DECODER

module deco(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```
### RTL LOGIC
### ENCODER

![244051105-33299991-1c4a-4807-a14b-8179aa2b23d9](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/0d5efb04-34d6-48b2-93b9-5c50c8ac0ad6)

### DECODER

![244049195-43ee1d0e-09e6-4535-93b0-74abed121ec8](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/37bb323a-e5fa-47d0-8ecd-25a606d09371)

### TIMING DIAGRAMS
### ENCODER

![244051146-948ee50a-8ca6-43d1-8e73-56c081183e0d](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/724ba263-5f0d-4c12-aa51-400b0cccd23d)

### DECODER

![244050482-b7adb8f7-4ddc-4abb-b6fc-42a135a3ca59](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/3d52cb1e-46c2-4d83-be89-7d02bea35994)

### TRUTH TABEL
### ENCODER

![244050550-41362149-4614-4357-b019-30f9fa0e7f30](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/d8a81c2d-11b4-4150-864d-95aa234f7610)

### DECODER

![244050584-741c6ae9-aef3-497a-a8c3-74fad71a30c6](https://github.com/MavillaPranathi/Experiment-08-Encoders-and-decoders-/assets/118343610/4643ec4f-6846-4ad0-bf5f-cf116b046b77)

### RESULT
Thus the program to design encoder and decoder is successfully completed.
