# Debugging SSL-related problems

Various built-in SmartGit functionality will connect to *https* URLs,
for example:

  - **Check for New Version**
  - **Hosting Provider** integrations
  - the SVN bridge

When experiencing problems here,  it can be helpful to debug Java's
networking layer. To do that, first add the following system property to
the [smartgit.properties](System_Properties) file:

  - for SmartGit up to version 18.2:
    
    <div class="code panel pdl" style="border-width: 1px;">
    
    <div class="codeContent panelContent pdl">
    
    ``` java
    javax.net.debug=ssl
    ```
    
    </div>
    
    </div>

  - for SmartGit version 18.2 and higher:
    
    <div class="code panel pdl" style="border-width: 1px;">
    
    <div class="codeContent panelContent pdl">
    
    ``` java
    javax.net.debug=ssl:handshake
    ```
    
    </div>
    
    </div>

After that, restart SmartGit from the command line and pipe the output
to a file:

  - On Windows: execute `<install-dir>\bin\smartgitc.exe > dump.txt`.
  - On MacOS: execute `<install-dir>/Contents/MacOS/SmartGit >
    dump.txt`.
  - On Linux: execute `<install-dir>/bin/smartgit.sh > dump.txt`.

Finally, verify that `dump.txt` contains SSL-related output.

*How to send the dump.txt file*: Compress the `dump.txt` file as a *zip*
or *tar/gzip* archive, and also include the zipped `log` directory from
SmartGit's settings directory. Send this archive, as well as a short
description of how to reproduce the problem, to <smartgit@syntevo.com>.
