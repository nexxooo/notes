# TD S 12
## exo 1 
**and $t3, $t4, $t5**

|opcode|rs|rt|rd|shamt|funct|
|---|---|---|---|---|---|
000000|01100|01101|01011|00000|100100|

**ori $t6, $t7, 0xFF**
|opcode|rs|rt|I|
|---|---|---|---|
|001101|01111|01110|0000000011111111|

**sub $a0, $a1, $a2** ==> Rd <-- Rs - Rt

|opcode|rs|rt|rd|shamt|funct|
|---|---|---|---|---|---|
|000000|00101|00110|00100|00000|100010|

beq $s4, $s5, -4 ==> beq Rs, Rt, Etq 

|opcode|rs|rt|I|
|---|---|---|---|
|000100|10100|10101|1111111111111100

## exo 2 
0000 0001 0001 0010 0011 0000 0010 0000

## TD2 
### exo1
* li $t0,7
* add $v0,t0,t1 // sub $v0,$v0,$t2 
* add $t1, $t1, $t2 // sub $v0, $t0, $t1 
* addi $v0, $t0, 4 
* beq $v0, $zero, label 
* lw \$v0 ,10($t3)

### exo2 

~~~
.data
...

.text
main:
lw $t1, b 
lw $t2, c 
lw $t3, d 

add $t3, $t3, $t2 
add $t2, $t2 , $t1
sub $t2, $t2, $t4

add $t0, $t2, $t3
~~~
~~~
.data 
...
.text
main:
blt $t2, $t3, choix1
j choix2

choix1:
add $t4, $t4, $t2 
j exit

choix2:
add $t4, $t4, $t3
j exit

exit:
sw $t4, k
...
~~~

~~~
.data 
...

.text 
main:
...
boucle:
blt $s1, $s2, compteur
j exit 

compteur:
addi $s3, 1 
addi $s1, 2 
j boucle

exit:
...
~~~
~~~
foo:
li $t0, 2 
bgt $a0, $t0, cas1
j sinon

    cas1:
    mul $a0, $a0, $t0
    add $a0, $a0, $a1
    j return

    cas sinon:
    sub $a0, $a0, $a1
    j return

return:
...
~~~

### exo 3 
~~~
.data
f: word 2 
g: word 3 
y: word 0

.text
__start:
lw $a0, f
lw $a1, g

jal sum 

la $t0, $v0
sw $t0, y

addiu $v0, $zero, 10
syscall

sum:
add $v0, $a1, $a2 
jr $ra 
~~~

## Memoire cache
### Spatitaux temporel

temporel --> utilisation répéter (boucle for)

spatial --> utilisation de voisin (tableau)

### ex 1.3 
* 40 
* (3*0.8 + 41 * 0.2) = 10,6 --> l1 vers ram 
* (5*0.9 + 42 * 0.1) = 8.7 --> L2 vers ram 
(3 * 0.8 + (1+8.7)*0.2) = 4.34 
    

