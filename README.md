# verilog
module muxtwo(out,a,b,sl);
  input a,b,sl;
  output out;
  reg out;
    always@(sl or a or b)
      if(!sl) out=a;
      else out=b;
endmodule

module led(clk,rst,led)
input clk,rst
output reg[7:0] led
reg[25:0] count
  always@(posedge clk)
    if(rst) led<=8'b10000000
  always@(posedge clk)
    if(reg[25]==1)
      begin
      if(led==8'b00000001)
        led<=8'b10000000
      else
        led<={led[0],led[7:1]}
      end
endmodule      
