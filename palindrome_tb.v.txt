`timescale 1ns/1ps

module tb_palindrome_detector;

reg clk;
reg reset;
reg x;
wire y;

palindrome_detector uut (
    .clk(clk),
    .reset(reset),
    .x(x),
    .y(y)
);

// Clock generation
always #5 clk = ~clk;

initial
begin
    clk = 0;
    reset = 1;
    x = 0;

    #10 reset = 0;

    // Input sequence: 1 0 0 1 (palindrome)
    #10 x = 1;
    #10 x = 0;
    #10 x = 0;
    #10 x = 1;

    // Input sequence: 1 1 0 1 (not palindrome)
    #10 x = 1;
    #10 x = 1;
    #10 x = 0;
    #10 x = 1;

    // Input sequence: 0 1 1 0 (palindrome)
    #10 x = 0;
    #10 x = 1;
    #10 x = 1;
    #10 x = 0;

    #50 $finish;
end

endmodule