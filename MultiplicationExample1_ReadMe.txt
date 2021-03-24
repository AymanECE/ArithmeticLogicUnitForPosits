
P1= 0 1111 0 101 00101011 = (2^32) * (2^5) * ( 1 + 43/256). TE1 = 2^37

P2=0 111 0 010  100010100 = (2^24) * ( 2^2) * ( 1+ 276/512). TE2 = 2^26

Lets say we have the above numbers and we want to multiply them . 



now ( 1 + 43/256) = (299/256) and ( 1+ 276/512) = (788/512)

we shift the second posit by 1 to the right which is equivalent to dividing by 2 , to have a common denominator with the first posit.  

so we get (299/256) and (394/256).|||| 299 = 0100101011 , 394 =0110001010 

TE1 * TE2 =  (2^37) * (2^(26)) = 2^(37+26)= 2^63

Now we multiply 299 and 394 and we get 117806 and the denominator becomes 2^16.

Now i have to remove subtract 2^16 from the numerator tog et our one, as a result we get 117806 - 2^16 =  (1+ 52270/2^16)
 52270=1100110000101110
Now I need to figure out how many fraction bits I am left with as I surely dont have 18bits ( fraction 1 and2 are represented in 9bits so i need 18 bits to represent 
the full range ) 
Other Method is to shift then subtract one, so i take 117806 and shift it 14 times, 
: 011100110000101110 becomes 000000000000000111 now i remove 2
Now we have to move on to dealing with TE1 * TE2 , how many regime bits do i now have? 

To determine that, my USEED is 2^3 = 8 , I do the modulo of 63 by 8 and get 7, this 7 represents the number of regime bits I have. The remainder which is 63-56 = 7 is represented
 using the exponents bit, this leaves me with 16-1 -7 -1 - 3 = 4 bits for my fraction . So I will have to shift my fraction by 18-4 = 14 bits to the right.
As a result I will have left 1100, 

0 1111111 0 110 1100 = 2^61 * ( 1 + 12/16) = 1.61409 x10^19, but if my fraction bit was 1101 we would get =1.6717 x 10^19 which is closer to the needed value
The multiplication of the original numbers gives us = 1.65797 x 10^19.

Need  1101 instead of 1100, does this mean something is wrong in my calculations?

