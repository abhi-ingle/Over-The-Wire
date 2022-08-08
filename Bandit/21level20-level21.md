### Level20-Level21

<hr>
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
<hr/>

<b>Solution</b><br/>

<p>
<ol>

<li>First we need to activate a port to listen for connections.<br/>
We will choose port 5000.</li>
<li>The suconnect- setuid binary will make a connection with port 5000 and as soon as it will get the password from port 5000 of the current level.It will return password of the next level</li>
<li>Open two terminals:
    <ul>
    <li>In one terminal using netcat make port 5000 to listen for connections<br/>
    <code>nc -lp 5000</code></li>
    <li>In another terminal run suconnect by specifying the port number along side.</li>
    <li>The password is returned in the netcat terminal.</li>
    </ul>
</li>

![bandit20-21-1](https://user-images.githubusercontent.com/88927842/183335943-290bed26-4579-4704-aa1e-c4a0f34e437a.png)

![bandit20-21-2](https://user-images.githubusercontent.com/88927842/183335965-dcf94d15-7e88-478f-af77-fd6acfb54874.png)


</p>
</ol>
<hr/>