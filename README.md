# INE5607
Organização e Arquitetura de Computadores
<br />
##MIPS
###Operações aritméticas
<ul><li>add</li>
    <li>addi</li>
    <li>sub</li>
    <li><strike>subi</strike> (não existe, utiliza addi, com um parametro negativo)</li>
</ul>

###Operações lógicas
<table>
<tr><th>Operação</th><th>Operador C / Java</th><th>Instrução MIPS</th></tr>
<tr><td>Binary Shift Left</td><td align="center"> << </td><td>sll</td></tr>
<tr><td>Binary Shift Right</td><td align="center"> >> </td><td>srl</td></tr>
<tr><td>Bit-by-bit AND </td><td align="center"> & </td><td>and, andi</td></tr>
<tr><td>Bit-by-bit OR</td><td align="center"> | </td><td>or,ori</td></tr>
<tr><td>Bit-by-bit NOT</td><td align="center"> ~ </td><td>nor<span style="color:red;">*</span></td></tr>
<tr><td colspan="3"><span style="color:red;">*</span>para realizar o nor realizar um not, deve-se fazer: nor $s0,$s0,$zero. <br /> 
                    de outra forma nor equivale a x = ~(x|y)
    </td>
</tr>
</table>


