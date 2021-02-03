# Debugging

# General advices/preparations

Always try to investigate problems with a fresh SmartGit setup:

  - on Windows, use the *Portable* bundle:
    <https://www.syntevo.com/smartgit/download/>
  - on macOS and Linux, temporary use a new
    [smartgit.settings](https://www.syntevo.com/doc/display/SG/VM+options#VMoptions-settings-dir.change-location)
    directory

<div>

Why?

<div>

SmartGit has plenty of **Preferences** options and even more **Low-Level
Properties** which may sometimes affect the behavior of operations in
non-obvious ways. This is especially true if the behavior you are
experiencing is unexpected and/or looks like a bug.

</div>

</div>

Also, before investigating a problem, restart SmartGit with clean logs:

  - locate the [Installation and
    Files](https://www.syntevo.com/doc/display/SG/Installation+and+Files)
    in the **Help|About** dialog
  - from sub-directory `logs/` remove all `log.txt*` files

When sending logs to us, make sure they are **compressed** either with
*ZIP* or *7z*. This prevents the logs from becoming inlined into the
email.

# Enabling debug logging for certain keys

To enable debug logging for a certain key `foo.bar`, first decide the
log-level – whether it should be fine (`DEBUG`) or as fine as
possible `TRACE`. Usually SmartGit support will tell you. After that
add the corresponding line to `smartgit.properties` (in the Settings
directory, see [Installation and
Files](https://www.syntevo.com/doc/display/SG/Installation+and+Files)).
Depending on the log-level this will be either:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">

**DEBUG logging**

</div>

<div class="codeContent panelContent pdl">

``` java
log4j.foo.bar=DEBUG
```

</div>

</div>

Or:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">

**TRACE logging**

</div>

<div class="codeContent panelContent pdl">

``` java
log4j.foo.bar=TRACE
```

</div>

</div>

After that, restart SmartGit and repeat the operation for which debug
logging should be collected and shutdown SmartGit again.

Now `logs/log.txt.0` should contain `DEBUG` lines for the specified key.

<div>

<div>

If asked by support to enable debug logging for key `foo.bar`, always be
sure to use `log4j` prefix, i.e. `log4j.foo.bar`.

</div>

</div>
