
0 1111 0 101 0001001 = (4096) x (2^5) x ( 1+ 9/ 128) = 140288
-
0 1111 0 101 0000101= (4096) x (2^5) x (1+ 5/128) = 136192


we have to add one to the second fraction
so 0000101 becomes 10000101  = 133 now i see that this is bigger than F1, so like previously add one to F1
we get 10001001 and we have 10000101 = 139, now subtract

we get 00000100 = 4 , now we need to remove one by shifting left first . We need to shift it left by 5, so i need 
to decrement the exponent by 5 as well. Then after shifting we get 10000000, now remove the one
we get 0000000.

How will our units know to shift by 5 ? Well, I need to remove 128 which is 2^7 from 2^2 =4 




and take the exponent 101 remove 5 we get 000 as well 
so our answer will be

0 1111 0 000 0000000 = 4096 , when we subtract the above numbers we get the exact number here.



My try: 
howmuch :=0;
for i in range 0 to nbofbitsforfaction loop
	if to_integer(PLU_Result) <= shift_left(to_unsigned(1,nbofbits),nbofbitfraction1-1) then
	PLU_Result := shift_left(PLU_Result,1);
	howmuch :=howmuch + 1;
	