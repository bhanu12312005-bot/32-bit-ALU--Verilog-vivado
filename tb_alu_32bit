`timescale 1ns / 1ps

module alu_32bit_tb;

    reg [31:0] A;
    reg [31:0] B;
    reg [3:0] ALU_Sel;
    wire [31:0] Result;

    alu_32bit uut (
        .A(A),
        .B(B),
        .ALU_Sel(ALU_Sel),
        .Result(Result)
    );

    initial begin

        // Addition
        A = 32'h0000000A;
        B = 32'h00000005;
        ALU_Sel = 4'b0000;
        #10;

        // Subtraction
        A = 32'h0000000A;
        B = 32'h00000005;
        ALU_Sel = 4'b0001;
        #10;

        // AND
        A = 32'h0000000F;
        B = 32'h00000003;
        ALU_Sel = 4'b0010;
        #10;

        // OR
        A = 32'h0000000F;
        B = 32'h00000003;
        ALU_Sel = 4'b0011;
        #10;

        // XOR
        A = 32'h0000000F;
        B = 32'h00000003;
        ALU_Sel = 4'b0100;
        #10;

        // NOT
        A = 32'h0000000F;
        B = 32'h00000000;
        ALU_Sel = 4'b0101;
        #10;

        // Left Shift
        A = 32'h00000001;
        B = 32'h00000002;
        ALU_Sel = 4'b0110;
        #10;

        // Right Shift
        A = 32'h00000010;
        B = 32'h00000002;
        ALU_Sel = 4'b0111;
        #10;

        // Comparison
        A = 32'h00000005;
        B = 32'h0000000A;
        ALU_Sel = 4'b1000;
        #10;

        $finish;

    end

endmodule
