# Fixing the Git configuration for a local repository shared between different operating systems

<div>

<div>

This article is just about sharing the same **local** repository between
different operating system, i.e. accessing a shared folder from these
different systems.

</div>

</div>

Certain Git configuration (like `core.ignoreCase`) must be set correctly
for the underlying operating system to have Git operating properly. When
sharing your repository with a different operating system (this happens
quite frequently when using virtual machines), there may be no single
correct configuration and you have to carefully decide which Git
configuration should be used.

## Configure core.ignoreCase for shared repository

Problems will only arise when sharing a case-sensitive file system
(default for Linux) with a case-insensitive operating system (Windows).
In this case, `core.ignoreCase=false` is usually the safer default. To
fix, invoke **Open Git-Shell** for the problematic repository and
invoke:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` java
$ git config --unset core.ignoreCase
```

</div>

</div>

To be sure that there is no global `core.ignoreCase` configuration left
somewhere else, make sure the output of following command is empty:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` java
$ git config core.ignoreCase
```

</div>

</div>

Finally, to disable further warnings on the other case-insensitive
operating system, invoke:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` java
git config smartgit.warning.git-core-ignorecase-mismatch false
```

</div>

</div>

## Configure core.ignoreCase for copied repository, which isn't shared anymore

Things are different if the repository has just been copied from a
different operating system but isn't shared anymore. In this case, there
*is* a correct configuration for your current operating system:

  - Windows: `git config core.ignoreCase=true`
  - MacOS: `git config core.ignoreCase=true` (unless you are using an
    older, case-sensitive file system)
  - Linux: `git config --unset core.ignoreCase`
