```
org 100h

.data
quotient dw 0h
remainder dw 0h


.code
mov AX,8
mov BX,4 
mov CX,0

       
repeat:     
           
        SUB AX,BX   
        INC quotient
        MOV CX,quotient 
        MOV remainder,AX
        CMP AX,BX
        JGE repeat 

ret       


```
