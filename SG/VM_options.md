# VM options

Certain configuration of SmartGit has to be done by *VM options*, in
files called `smartgit.vmoptions`. Usually you will want to specify VM
options just for your account (current user):

  - **Windows:** `%APPDATA%\syntevo\SmartGit\smartgit.vmoptions`
    (`%APPDATA%` is the path defined in the environment variable
    `APPDATA`)
  - **Linux:** `~/.smartgit/smartgit.vmoptions`
  - **MacOS:** `~/Library/Preferences/SmartGit/smartgit.vmoptions`

Alternatively (but **not recommended**), VM options can also be
specified system-wide in following files:

  - **Windows:** the global file is `bin\smartgit.vmoptions` in
    SmartGit's installation directory
  - **Linux:** the global file is `bin/smartgit.vmoptions` in SmartGit's
    installation directory
  - **MacOS:** the global file is `Contents/MacOS/smartgit.vmoptions` in
    SmartGit's installation directory `SmartGit.app`

The `smartgit.vmoptions` file contains a list of additional VM options
which should be passed to the Java VM. VM options are basically
arguments to Java and every argument must be declared on a separate
line.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` java
-Xmx2048M
-Xms1024M
```

</div>

</div>

</div>

</div>

## Location of the Settings Directory

The *settings* contains SmartGit's settings. See [Installation and
Files](Installation-and-Files_1704364.html#InstallationandFiles-installation)
for information about the default location and contents of the settings
directory. On Windows and Linux, you can change its location by
modifying the VM option `-Dsmartgit.settings`.

<div>

Note

<div>

Changing the settings directory's location is *not* supported on MacOS

</div>

</div>

Within the value of `smartgit.settings`, certain Java system properties
are allowed, such as `user.home`. Another accepted value is the special
`smartgit.installation` property, which refers to the SmartGit
installation directory.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

To tell SmartGit to store its settings in the subdirectory `.settings`
of the SmartGit installation directory, add follow line to
`smartgit.vmoptions`:

`-Dsmartgit.settings=${smartgit.installation}\.settings` (Windows)

`-Dsmartgit.settings=${smartgit.installation}/.settings` (Linux)

</div>

</div>

## Location of the Updates Directory

The *Updates* directory contains downloaded program updates. See
[Installation and
Files](Installation-and-Files_1704364.html#InstallationandFiles-installation)
for information about the default location and contents of the *Updates*
directory. On Windows and Linux, you can change its location by
modifying the VM option `-Dsmartboot.sourceDirectory`.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

To tell SmartGit to store its program updates in the subdirectory
`.updates` of the SmartGit installation directory, add follow line to
`smartgit.vmoptions`:

`-Dsmartgit.settings=.updates`

</div>

</div>

## Used Java Runtime Environment

You can check **Help|About**, page **Information** to see which **Java
Version** SmartGit is using. Depending on the operating system, you can
change the Java VM as follows:

### Windows

Use the Windows environment variable `SMARTGIT_JAVA_HOME` to tell
SmartGit which 64-bit JRE to use.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

To tell SmartGit to use the Java 8 JRE located at in `C:\Program
Files\Java\jre8`, set the environment variable
`SMARTGIT_JAVA_HOME=C:\Program Files\Java\jre8`.

</div>

</div>

## Memory Limit

The memory limit (also known as maximum heap size) specifies how much
RAM the SmartGit process is allowed to use. The memory limit can be
configured by the VM option `-Xmx`.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

To change the maximum memory limit to 1GB, add following line to
`smartgit.vmoptions`:

`-Xmx1024m`

</div>

</div>

If the set value is too low, SmartGit may run out of memory during
memory-intensive operations.

## Extended PATH

On Linux and MacOS, you can extend the PATH used by SmartGit (and all
processes invoked by SmartGit, especially Git itself) by
adding `path=/additional/path` to `smartgit.vmoptions`. This `path=`
lines can be used multiple times and will be **appended** to the PATH in
the order of occurrence.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

To make the file `/usr/local/bin/git-lfs` accessible without full path
specification, add following line to `smartgit.vmoptions`:

`path=/usr/local/bin`

</div>

</div>

<div>

<div>

Do not specify the file path, but its parent directory's path - as for
all usual path modifications\!

</div>

</div>
