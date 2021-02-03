# Command-Line Options

This section gives an overview of the various options SmartGit can be
started with. These options should be given as parameters to the
SmartGit launcher. The launcher to be used depends on your platform:

  - **Windows** `bin\smartgit.exe` or `bin\smartgitc.exe`. The first one
    is meant for regular usage, while the second one will print
    additional information on the console while the program runs.
  - **MacOS** `SmartGit <version-number>.app/Contents/MacOS/SmartGit`
  - **Linux** `bin/smartgit.sh`

In the following, we'll use `smartgitc.exe` as an example to explain the
available options. Substitute it with the respective launcher for your
platform if you're not using Windows.

There may be additional options available that mainly serve debugging
purposes and are therefore not documented here.

## Options "-?" and "--help"

With either of the two following commands you can print all command-line
options on the console that are specifically supported by the version of
SmartGit you're using:

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe -?`

`smartgitc.exe --help`

</div>

</div>

<div>

Note

<div>

On Windows, make sure to call `smartgitc.exe` (with 'c' on the end),
otherwise when calling `smartgit.exe` this parameter has no effect,
since the SmartGit process won't be attached to any console to print the
help output to.

</div>

</div>

## Option "--open"

This option launches SmartGit and opens the repository in the specified
location. It's the default option and may be omitted.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --open C:\path\to\repository`

</div>

</div>

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --cwd C:\path --open to\repository`

</div>

</div>

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe .`

</div>

</div>

## Option "--cwd"

This option sets the current working directory, which affects the path
given in the `open`, `log` and `blame` option (see below) as follows:

  - If the `open`, `log` or `blame` options are specified without their
    own path arguments, the path given with the `cwd` option will be
    used as argument for `open` or `log`.
  - If the `open`, `log` or `blame` options are specified with relative
    paths, these relative paths will be resolved against the path given
    with the `cwd` option.
  - If the `open`, `log` or `blame` options are specified with absolute
    paths, the path given with the `cwd` option is ignored.

The path given with the `cwd` option must be an absolute path. If the
path is relative, it will be ignored.

## Option "--log"

This option opens SmartGit's Log window for the repository or file in
the specified location. The main window is not opened.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --log C:\path\to\repository\path\to\file`

</div>

</div>

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --cwd C:\path --log to\repository`

</div>

</div>

## Option "--blame"

This option opens SmartGit's Blame window for the specified file.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --blame C:\path\to\repository\path\to\file`

</div>

</div>

When adding a colon with the line number at the file end, it will scroll
to the specified line.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --blame C:\path\to\repository\path\to\file:400`

</div>

</div>

## Option "--investigate"

This option opens the built-in DeepGit for the specified file. When
adding a colon with the line number at the file end, it will scroll to
the specified line.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --investigate C:\path\to\repository\path\to\file:400`

</div>

</div>

## Option "--anchor-commit"

This option can be optionally specified in addition to
"--log", "--blame" and "--investigate" and defines the *anchor commit*
of the Log. The anchor commit will be made visible and preselected in
the **Commits** view.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

`smartgitc.exe --log C:\path\to\repository\path\to\file
--anchor-commit=10de7ee0313e79c406d729f4c3e11f286df54f05`

</div>

</div>

## Option "--write-default-theme-file"

Use this option to create the file `own.theme` in the SmartGit [settings
directory](https://www.syntevo.com/doc/display/SU/VM+Options) (the exact
file path is displayed) as starting base for creating a SmartGit theme.
You can rename or move the file.

The file contains *key=value* lines, a leading \# comments out the line.
The most keys should be self-explaining. The value usually is a color
defined as `#rrggbb` using hexadecimal values, but it also can be name
of another key which makes it easier to create a couple of named colors
instead of having to write the same `#rrggbb` value for different
controls. *inherit* means to inherit the color from the parent control,
*default* forces the control to use its default color from the operating
system. You can SmartGit tell to load this file by selecting it in the
preferences:

![](attachments/1704363/10715267.png)

###### Example

To create a theme that uses a green background color for selection,
uncomment the line

    #selection.background=#5968B2

by removing the leading \# and change the value to a green value:

    selection.background=#3DAF3F

and restart SmartGit.

<div class="pageSectionHeader">

## Attachments:

</div>

<div class="greybox" data-align="left">

![](images/icons/bullet_blue.gif)
[theme-custom.png](attachments/1704363/10715267.png) (image/png)  

</div>
