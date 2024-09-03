first , i decompiled the given pyc file back to a .py file and looked at the code consisting of two encrypt functions 
the second enc func has "^" which will xor the bytes of the input 
xor ing it once more will decrypt it 
the first one  for the case of the string passed to it but the output also remains of the same case so we can use the same check of for the case the operation it does is the following after checking the case 

-- decompiler output 
def encrypt(text, shift): cipher = '' for c in text: if c.isupper(): cipher += chr((ord(c) + shift - 65) % 26 + 65) elif c.islower(): cipher += chr((ord(c) + shift - 97) % 26 + 97) else: cipher += c return cipher

sorry for the indentation monstrosity ,  i am lazy 

wht you have to focus on is 
this code 

cipher += chr((ord(c) + shift - 65) % 26 + 65)

and what its reverse is 

deph += chr((ord(c) - shift - 65) % 26 + 65)

(replace 65 with 97 for the corresponding if condition)

make a code with these conditions pass the enc text and you get the decrypted flag 

input :- "w:~=Qwc=Qy?v^Ql?}Q`w"

output flag :- t4k3_th3_r1sK_w1n_it

things learned:-  not a lot 



