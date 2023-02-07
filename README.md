<h1>Defending Against A buffer Overflow Attack</h1>


<h2>Description</h2>
In this lab, I learned to defend against a buffer overflow attack. Buffer overflow attacks make use of various vulnerabilities in the stack. These attacks take malicious user input, put it onto the stack, and affect the local variables that are stored on the stack.
<br />



<h2>Environments Used </h2>

- <b>Windows Server 2016 Datacenter</b> 

<h2>Utilities and Language </h2>

- <b>PuTTY</b>

<h2>Program walk-through:</h2>

<p align="center">
Select the PuTTY icon <br/>
<img src="https://i.postimg.cc/K8HQFbWT/Screen-Shot-2023-02-06-at-8-27-58-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
  
<br />
Once the PuTTY window is up click open  <br/>
<img src="https://i.postimg.cc/VN7J2sHy/Screen-Shot-2023-02-06-at-8-31-05-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
In the PuTTY window type in the username and password.  <br/>
<img src="https://i.postimg.cc/LhdDf3zV/Screen-Shot-2023-02-06-at-8-35-07-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
Type in the following commands<br>
gcc -g /root/Documents/vulnerable.c -o vulnerable -fno-stack-protector <br>
gdb vulnerable <br>
break main <br>
r <br>
info register <br> <br>
following this type "q" then hit return 
<img src="https://i.postimg.cc/cLdxBy1V/Screen-Shot-2023-02-06-at-8-40-28-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />






<br />
Now type in "disas" to disassemble and hit enter then type "q" and return to continue
<img src="https://i.postimg.cc/qBYQK4wv/Screen-Shot-2023-02-06-at-8-43-56-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
Now in the window type in "x/10xw 'rsp value'" to find the memory address | type in the rsv value obatined in the steps prior<br>
Type in "next" thrice to move on after yyou type in the rsv value
<img src="https://i.postimg.cc/wBj9nSrn/Screen-Shot-2023-02-06-at-8-49-42-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Now in the terminal type in the "x/10xw 'rsp value'" again followed by the following commands <br>
next <br>
p/x 'age value' (age value is obtained by previously typing next)
<img src="https://i.postimg.cc/4NN6q4GX/Screen-Shot-2023-02-06-at-8-53-35-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Now from the desktop open another PuTTY window and proceed by clicking open then entering the login and password
<img src="https://i.postimg.cc/m2n0rgTS/Screen-Shot-2023-02-06-at-8-58-59-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />








<br />
In the ner PuTTy terminal window execute the following command to exploit an attack using the attack.c file  <br>
gcc -g /root/Documents/attack.c -o attack <br>
./attack | ./vulnerable <br>
<img src="https://i.postimg.cc/Bvrd5xN6/Screen-Shot-2023-02-06-at-9-07-28-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />














