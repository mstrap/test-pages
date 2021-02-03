# Tracing the modified state of a file

When the reason for the **modified** state of a specific file is
unclear, following procedure allows to debug details for this file.

### Compare with git status

Give `git status` a try and see whether the same modification is present
there. If so, you may still run through this procedure, but likely the
answer to this question is found elsewhere (reason may be a wrong
`.git/config` or EOL-related issues).

If invoking `git status` does not show the same modification or even
resets the modification in SmartGit, the resulting debug information
should be sufficient to understand the difference between SmartGit's
status detection and Git's status.

### Procedure

  - Shutdown SmartGit.

  - Add `smartgit.statusscanner.trace`=\<relative-path\>
    to [smartgit.properties](https://www.syntevo.com/doc/display/SG170/System+Properties)
    (in the settings directory, see About dialog).  
    `<relative-`path\> is the repository-relative path of the file for
    which the modification should be traced. On Windows, also replace
    backslashes by forward slashes.
    
    <div>
    
    Example
    
    <div>
    
    On Windows, for example for file `C:\vss\Project\FOO\bar\file` with
    repository root `C:\vss\Project`, you should add line:
    
    `smartgit.statusscanner.trace`=FOO/bar/file
    
    </div>
    
    </div>

  - Get rid of the `log` directory inside the settings directory.

  - Restart SmartGit.

  - Open the offending repository and wait until the Refresh has
    finished and the modified file is showing up.

  - Make sure the files inside the `log` directory contain debug lines
    for the `smartgit.status.index` category.  
    You may use `grep "smartgit.status.index" log.txt*` to find out.

  - ZIP the `log` directory and send to `smartgit@syntevo.com`, together
    with an explanation of the problem.

### Dump traced file contents

On top of tracing the modified state of a file, you can also dump the
file contents of working tree and index. To enable this functionality,
add following system property
to [smartgit.properties](https://www.syntevo.com/doc/display/SG170/System+Properties)
(in the settings directory, see About dialog).

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` java
smartgit.status.index.dump.level=FINEST
```

</div>

</div>
