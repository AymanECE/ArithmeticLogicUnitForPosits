
Posit1 : 0 111 0 101 00101011 = 2^(29)  x ( 1 + 43/2^8)

Posit2 : 0 11 0 010 100010100 = 2^(18) x ( 1 + 276/2^9)



First start by normalizing the fractions 2^8 + 43 = 299 / 2^8 
and fraction 2 becomes 788/ 2^9, 

Now shift fraction to the right by one to get common denominators in both fractions. we get 394/ 2^8 . 


Now we move to the division step.

I check if i can divide 299 by 394 i cant , so i shift left 299 by one and get 598, decrement exponent 1 by one and
check again if i can divide or not ( this is done using a for loop). so i will now move on to divide 
598 (01001010110) by 394 (0110001010) and obtain 1 with a remainder of 204 (011001100)

Now I hahve to deal with a remainder, I will create a vector bit of size 16 bits 
and i will start to shift and fill this 8 bit vector, so I start by shifting 204 to the left 
I get 408 > 394 so "1" and remainder 14 i shift 14 i get 28 < 394 so "10" , then 56<394 so "100" then 112 so "1000"
then 224 so "10000" then 448 > 394 so "100001" with remainder 54 shift i get 108  so "1000010" again we get 216 and 
" 10000100" which is 8 bits and i continue so on, from vivado i get " 1000010001100"

okay now i have a quotient of 1 with " 1000010001100", if my quotient is not 1 i add quotient -1 to my exponents 
Now i calculate the number of bits allocated to regime , exponent and fraction as previously done in the multiplication.

Now my exponent is 29-1 - 18 = 10 ( the -1 comes from shifting the mantissa at the begining ) .

so 1 bit for regime , 3bits for exponent and we get 10bits for fraction
so my answer 2^10 x ( 1+  10000100010/ 2^11 ) = 1554 

expected answer = 1554 so my answer is correct. 

