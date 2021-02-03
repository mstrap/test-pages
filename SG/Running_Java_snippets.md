# Running Java snippets

To debug, we may sometimes send you small Java snippets to run, usually
compressed in a ZIP file. To run these snippets, you need to have a
SmartGit installation on your system which also comes with its own
runtime environment:

1.  Uncompress the ZIP file contents to a temporary directory,
    e.g. `c:\temp\debug`

2.  Open a command line/terminal, `cd` to this directory and invoke:
    
    <div class="code panel pdl" style="border-width: 1px;">
    
    <div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">
    
    **Usage**
    
    </div>
    
    <div class="codeContent panelContent pdl">
    
    ``` java
    {jre}/bin/java -classpath . {classname} > out.txt 
    ```
    
    </div>
    
    </div>
    
    Substitute `{classname`} by the class name we have asked you to run
    and `{jre`} by the path to SmartGit's JRE. Depending on your
    operating system, you will find the JRE at:
    
    1.  **Windows**: \<smartgit-installation\>\\jre
    
    2.  **Linux**: \<smartgit-installation\>/jre
    
    3.  **MacOS**: \<smartgit.app\>/Contents/Resources/jre
    
      
    
    <div class="code panel pdl" style="border-width: 1px;">
    
    <div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">
    
    **Example**
    
    </div>
    
    <div class="codeContent panelContent pdl">
    
    ``` java
    "C:\Program Files (x86)\SmartGit\jre\bin\java.exe" -classpath . NioFileSystemWalk c:\temp\repo true > out.txt 
    ```
    
    </div>
    
    </div>

3.  If there is an error printed which is not related to a wrong command
    line usage, also pipe `stderr` to a separate file:
    
    <div class="code panel pdl" style="border-width: 1px;">
    
    <div class="codeContent panelContent pdl">
    
    ``` java
    {jre}/bin/java -classpath . {classname} > out.txt 2> err.txt
    ```
    
    </div>
    
    </div>

4.  You may investigate both `out.txt` (and `err.txt`) yourself to
    figure out possible problems.

5.  Finally, send us compressed `out.txt` (and `err.txt`) to
    smartgit@syntevo.com.
