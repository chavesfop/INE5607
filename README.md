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

###Carregamento de constantes
Constantes no MIPS, tem no máximo 16bits, portanto para<br />

32bits:<br />
<table>
<tr><th colspan="3">Desejamos carregar por exemplo: 0xFFFFAAAA</th></tr>
<tr><td>ori</td><td>$t0,$zero,0xFFFF</td><td>0x0000FFFF</td></tr>
<tr><td>sll</td><td>$s0,$t0,16</td><td>0xFFFF0000</td></tr>
<tr><td>ori</td><td>s0,$s0,0xAAAA</td><td>0xFFFFAAAA</td></tr>
</table>

###Instruções de tomada de decisão if-then-else
<ul>
<li>Desvios</li>
<li>If-then-else</li>
<li>Comparadores</li>
<li>Switch</li>
</ul>

#####Rótulos / Labels
<p>Apontam um endereço de memória por um nome especificado.<br />
<b>label</b>: add $s1,$s2,$s0<br />
agora quando referenciado label, sabemos que vai pra parte do processamento que tem <b>label</b>: no início.</p>


#####Desvios
<p>A label deve estar em até 2^16 instruções para continuar sendo identificada, pois as instruções ocupam 16 bits.</p>

######Desvio condicional<br />
<p>
beq: branch on equal<br />
beq $s0, $s1, Igual <i>#Se $s0==$s1, desvie para o endereço do label Igual</i>
</p>
<p>
bne: branch on not equal<br />
bne $s0, $s1, Diferente <i>#Se $s0!=$s1, desvie para o endereço do label Diferente</i>
</p>

######Desvio incondicional<br />
<p>
j (Jump)<br />
j Fim # Desvie para o endereço do label Fim<br />
O jump deve estar em uma instrução a 2^26, pois a operação ocupa 6 bits.
</p>
