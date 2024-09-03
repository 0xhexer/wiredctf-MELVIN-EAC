yo man this 
this was *"**curses**"

disclaimer - used chat gpt (for function analysis)
also, i wouldn't have been able to solve this without the hints given by senior


took a lot of time but
oh well learned a lot along the way 
what i did 
read the name 
don't bother solving this 
and thought 
then i have to solve this 

hint - find decompiler (or something like that )

first i tried using file cmd on the given file (it is an ELF exec and is gcc compiled which means source file was c code )

decompiled the code using decompiler explorer 

used the output of angr to continue with rest of the (me crying) trying to find the flag

used chat gpt to understand functions 

after some time of reading found that the function of checking if the password is correct does not influence the output , also the if condition just before the get_flag func will never be true no matter
the input 

my first thought after reading and understanding was if i can run the getflag() and its dependent function independently or if i can bypass the checkup and if function  i will be able to get the flag 

but that thought was crushed with gcc doing gcc things "error" curses _----_

next i thought about gdb (with setting breakpoint at the cmp statement (je or jne idk))
but instantly dismissed that thought because even though i worked with gdb before , never before have i done it on a complex code and it would be a pain in the a** 

although i am sure that i will be able to find the answer and that too without using the way intended by the hint given

and now is where my dear respected senior comes in (although i forgot his name "sorry")

i know that output is dependent on the switch statement with v4 (for loop outside switch statement runs 4 times )
v4 if i remember correctly is the char at address v2 of v0 converted to unassigned integer (only whole num) and v0 is the copy of a0 (the value passed to the function getfilename() )
(also v2+= 1 each time of the for loop )

and the getfilename is called 3 times with 3 diff but constant a0 values 

The hint that senior gave me was what i think is 
that convert the constant a0 arg into hex and iterate through it 

i tried but flag was not right but i seeked advice from him again and 
what he said was is it necessary for it itrate it from begining to end 

and then i remembered something that i have heard but something that i have heard in a video but haven't understood it some long time ago that c uses stack memory lifo 

man this was sooo enlightening (seriously , although i could have used better wording )

Iterated through the hex in the opposite order chose the strings from switch and case statement
accordingly and finally got the strings that i so desperately searched for like a long lost lover
ahhh the bliss


i dont remember the exact flag but it should be like 

wired{fear_leads_to_dark_side}

or something like that 














