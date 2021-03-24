P1: 0 1111  0 111 0000010 =1.108 x 10^12

P2 :0 1111  0 101 1000111 =1.755 x10^11

F1 is the fraction part of P1 ( 0000010)
F2 is the fraction part of P2 ( 1000111)
es = 3
total exponent 1 = 32 + 5 = 39
total exponent 2 = 32+7 = 37


now add 1 to F2/2^8 = 71/128 + 1 = 199/128 = 11000111
Now shift it by 2 to the right(difference in exponents) we get , 00110001 (ignore the 128 denominator )
Trim off and we are left with 00110001 to subtract from 00000010.

when we subtract them we get a negative result so we have to do the following


 we  add the 1 to F1

we get 1+ 0000010=10000010 
now i can subtract 10000010 - 00110001= 01010001 
and we get  01010001 = 81

Now i need to return it to a posit form, so I will shift 01010001  left by one and decrement the total exponent
so now i will get 10100010  - 10000000  =  00100010 , I will remove 128 ( which represents a full 1 )  so now I have 00100010, and 
I have 7 bits to represent my fraction which works out nicely by removing hte most significant bit.

Result is calculated as follows: 
- Take regime of bigger number
- Take exponent of bigger number
- Check if my fraction of bigger number is smaller than that of the second number after the shifting is 
done to my second fraction.
- If shifted(F2+256) > F1 , we add 256 to F1, PLU_result=subtract (F1+256 ) - shifted(F2+256), now 
we are sure that our result is positive.(Notice the 256 comes from 2^(nb of bits used for fraction seperately), here they are equal to 2^8 both) 
- Now i need to get that 1 from ( 1 + F1/2^nbofbits ) back, so i shift  PLU_result to the left by one, decrement the exponent of P1 by 1. Then I subtract 256 from PLU_Result.
- After all this is done, our number is ready to be represented as

0 1111 0 110 0100010