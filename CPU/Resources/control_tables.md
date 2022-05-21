# 🎛️Control Tables

## Computational Analysis of Control Unit

| Function | OPcode | ALUsrc | ALUop | Mem Read | Mem Write | Reg Write |Mem to Reg | Reg Dst | Branch | Jump |
| -------- | ------ | ------ | ----- | -------- | --------- | --------- | --------- | ------- | ------ | ---- |
| `And`    | 0000   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Or`     | 0001   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Xor`    | 0010   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Nor`    | 0011   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Add`    | 0100   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Sub`    | 0101   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Less`   | 0110   | 0      | 1     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Beq`    | 0111   | 0      | 1     | 0        | 0         |   0       |         0 |       0 |      1 |     0|
| `Addi`   | 1100   | 1      | 0     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Subi`   | 1101   | 1      | 0     | 0        | 0         |   1       |         0 |       1 |      0 |     0|
| `Lw`     | 1000   | 1      | 0     | 1        | 0         |   1       |         1 |       0 |      0 |     0|
| `Sw`     | 1001   | 1      | 0     | 0        | 1         |   0       |         x |       x |      0 |     0|
| `Jump`   | 1111   | x      | x     | x        | 0         |   0       |         0 |       x |      0 |     1|

## ALU Control

<table>
<thead>
<tr>
<th colspan="6">Input Opcode</th>
<th colspan="4">Output Opcode</th>
</tr>
</thead>
<thead>
<tr>
<th></th><th>ALUOp</th><th>I1</th><th>I2</th><th>I3</th><th>I4</th>
<th>O1</th><th>O2</th><th>O3</th><th>Enable</th>
</tr>
</thead>
<tbody>

<tr>
<td></td>
<td>0</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>0</td>
</tr>

<tr>
<tr>
<td><code>And</code></td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td><code>Or</code></td>

<td>1</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
</tr>

<tr>
<td><code>Xor</code></td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Nor</code></td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>

<tr>
<td><code>Add</code></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Sub</code></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Less</code></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Beq</code></td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
</tr>

<tr>
<td><code>Addi</code></td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Subi</code></td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>1</td>
<td>1</td>
</tr>

<tr>
<td><code>Lw</code></td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>

<tr>
<td><code>Sw</code></td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
</tr>
<tr>
<td><code>Jump</code></td>

<td>x</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>x</td>
<td>x</td>
<td>x</td>
<td>x</td>
</tr>
</tbody>
</table>
