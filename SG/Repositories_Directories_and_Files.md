# Repositories, Directories and Files

The Repositories view shows all repositories known to SmartGit and, for
repositories opened in this window, the directory structure (and their
states). The Files view displays the status of your working tree (and
Index). The primary directory states are listed in [Primary Directory
States](#Repositories,DirectoriesandFiles-directory.states), and
possible states of submodules in [Submodule
States](#Repositories,DirectoriesandFiles-submodule.states). Every
primary and submodule state may be combined with additional states,
which are listed in [Additional Directory
States](#Repositories,DirectoriesandFiles-directory.badges). The
possible file states are listed in [File
States](#Repositories,DirectoriesandFiles-file.states).

## Repository Management

To add existing or new local repositories to SmartGit, please take a
look at the section [Repository-Related](Repository-Related).

## File Filtering

The **Files** view of the main window can be filtered by file state and
name. The state filters can be set using the small toolbar buttons above
the table as well as the menu items in the **View** menu. By default, if
committable files (e.g. *index-only changed* or *untracked*) are hidden,
the background turns to light-red as a reminder to not forget about
them. If this annoys you because you permanently have untracked files in
your working, you should consider to mark them as ignored. If this is no
option for you, you can deactivate this coloring feature in the
Preferences (page **User Interface**, option **Use background color for
the file table to indicate certain states**).

To filter by name, use the input field (or
*\<Ctrl/Cmd\>+\<F\>*-keystroke) above the file table. The context menu
allows to enable regular expressions and save patterns for later usage
or delete them. Even if unchanged files are hidden, they can be found by
filtering by name - the files matching by name but not by state are
shown in gray, while a light-yellow background indicates the
name-filtering state.

## Primary Directory States

<div class="table-wrap">

<table>
<tbody>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704330.png" />
</div></td>
<td>Default</td>
<td>Directory is present in the repository (more precisely: there is at least one versioned file below this directory stored in the repository).</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704339.png" />
</div></td>
<td>Unversioned</td>
<td>Directory (and contained files) are present in the working tree, but have not been added to the repository yet. Use <strong>Stage</strong> to add the files to the repository.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704331.png" />
</div></td>
<td>Ignored</td>
<td>Directory is not present in the repository (exists only in the working tree) and is marked as to be ignored.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704333.png" />
</div></td>
<td>Missing</td>
<td>Directory is present in the repository, but does not exist in the working tree. Use <strong>Stage</strong> to remove the files from the repository or <strong>Discard</strong> to restore them in the working tree.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704329.png" />
</div></td>
<td>Conflict</td>
<td>Repository contains conflicting files (only displayed on the root directory). Use <strong>Resolve</strong> to resolve the conflict.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704332.png" />
</div></td>
<td>Merge</td>
<td>Repository is in 'merging' or 'rebasing' state (only displayed on the root directory). Either <strong>Commit</strong> the merge/rebase or use <strong>Discard</strong> to cancel the merge/rebase.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704334.png" />
</div></td>
<td>Root/Submodule</td>
<td>Directory is either the repository root or a submodule root, see <a href="#Repositories,DirectoriesandFiles-submodule.states">Submodule States</a>.</td>
</tr>
</tbody>
</table>

</div>

## Submodule States

<div class="table-wrap">

<table>
<tbody>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704334.png" />
</div></td>
<td>Submodule</td>
<td>Unchanged submodule.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704337.png" />
</div></td>
<td>Modified in working tree</td>
<td>Submodule in working tree points to a different commit than the one registered in the repository. Use <strong>Stage</strong> to register the new commit in the Index, or <strong>Reset</strong> to reset the submodule to the commit registered in the repository.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704335.png" />
</div></td>
<td>Modified in Index</td>
<td>Submodule in working tree points to a different commit than the one registered in the repository, and this changed commit has been staged to the Index. <strong>Commit</strong> this change or use <strong>Discard</strong> to revert the Index.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704336.png" />
</div></td>
<td>Modified in WT and Index</td>
<td>Submodule in working tree points to a different commit than the one in the Index, and the staged commit in the Index is different from the one in the repository. Use either <strong>Stage</strong> to register the changed commit in the Index (overwriting the Index change), <strong>Discard</strong> to revert the Index, or <strong>Reset</strong> to reset the submodule to the commit registered in the Index.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704338.png" />
</div></td>
<td>Foreign repository</td>
<td>Nested repository is not registered in the parent repository as submodule. Use <strong>Stage</strong> to register (and add) the submodule to the parent repository.</td>
</tr>
</tbody>
</table>

</div>

## Additional Directory States

<div class="table-wrap">

<table>
<tbody>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704327.png" />
</div></td>
<td>Direct Local Changes</td>
<td>There are local (or Index) changes within the directory itself.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704328.png" />
</div></td>
<td>Indirect Local Changes</td>
<td>There are local (or Index) changes in one of the subdirectories of this directory.</td>
</tr>
</tbody>
</table>

</div>

## File States

<div class="table-wrap">

<table>
<tbody>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704350.png" />
</div></td>
<td>Unchanged</td>
<td>File is under version control and neither modified in working tree nor in Index.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704351.png" />
</div></td>
<td>Unversioned</td>
<td>File is not under version control, but only exists in the working tree. Use <strong>Stage</strong> to add the file or <strong>Ignore</strong> to ignore the file, or <strong>Commit</strong> to commit it right away.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704342.png" />
</div></td>
<td>Ignored</td>
<td>File is not under version control (exists only in the working tree) and is marked to be ignored.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704347.png" />
</div></td>
<td>Modified</td>
<td>File is modified in the working tree. Use <strong>Stage</strong> to add the changes to the Index or <strong>Commit</strong> the changes immediately.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704349.png" />
</div></td>
<td>Staged</td>
<td>File is modified and the changes have been staged to the Index. Either <strong>Commit</strong> the changes or <strong>Unstage</strong> changes to the working tree.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704346.png" />
</div></td>
<td>Staged Modified</td>
<td>File is modified in the working tree and in the Index in different ways. You may <strong>Commit</strong> either Index changes only or working tree changes plus Index changes.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704346.png" />
</div></td>
<td>Staged, WT as HEAD</td>
<td>File is modified in the working tree and in the Index in different ways, but the working tree state is identical to the HEAD state. Using <strong>Stage</strong> will turn the file back to unchanged again.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704347.png" /></p>
</div></td>
<td>Modified (File Mode)</td>
<td>The content of the file is not modified, but the executable bits are set different than in the repository. Refer to <a href="#Repositories,DirectoriesandFiles-file.states.how-to-fix-modified-file-mode">Fixing 'Modified (File Mode)' on Windows</a> on how to fix that state on Windows.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704347.png" /></p>
</div></td>
<td>Modified (EOLs only)</td>
<td>The content of the file is modified, but only differs in line endings from the Index state. This state will only be determined/show up if <a href="System_Properties">smartgit.refresh.inspectEol</a> system property is set.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704347.png" /></p>
</div></td>
<td>Modified (EOLs only,<br />
not stageable)</td>
<td>The content of the file is modified, but only differs in line endings from the Index state; but, due to the Git configuration (usually <code>core.autocrlf</code>) this modification can't be staged.<br />
Usually, when trying to stage, Git will issue a warning <code>warning: LF will be replaced by CRLF in ...</code> here. This state will only be determined/show up if <a href="System_Properties">smartgit.refresh.inspectEol</a> system property is set.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704340.png" />
</div></td>
<td>Added</td>
<td>File has been added to Index. Use <strong>Unstage</strong> to remove from the Index.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704348.png" /></p>
</div></td>
<td>Removed</td>
<td>File has been removed from the Index. Use <strong>Unstage</strong> to un-schedule the removal from the Index.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/5275734.png" /></p>
</div></td>
<td>Renamed</td>
<td>File is scheduled for addition and has been detected as renamed, see <a href="Preferences_1704353.html#Preferences-refresh">Preferences, section Refresh</a></td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/5275736.png" /></p>
</div></td>
<td>Renamed (untracked)</td>
<td>File is untracked and has been detected as renamed, see <a href="Preferences_1704353.html#Preferences-refresh">Preferences, section Refresh</a></td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/19923031.png" height="16" /></p>
</div></td>
<td>Renamed (modified)</td>
<td>File is scheduled for addition, has been detected as renamed (in the Index) and – on top of that – is modified in the working tree. Use will probably want to use <strong>Stage</strong> to add the working tree changes to the Index.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/5275735.png" /></p>
</div></td>
<td>Rename Source</td>
<td>File is the added (or missing) source of a detected <strong>Renamed</strong> or <strong>Renamed (untracked)</strong> file</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704344.png" /></p>
</div></td>
<td>Missing</td>
<td>File is under version control, but does not exist in the working tree. Use <strong>Stage</strong> or <strong>Remove</strong> to remove from the Index or <strong>Discard</strong> to restore in the wirking tree.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704345.png" /></p>
</div></td>
<td>Added Modified</td>
<td>File has been added to the Index and there is an additional change in the working tree. Use <strong>Commit</strong> to either commit just the addition or commit addition and change.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704344.png" /></p>
</div></td>
<td>Added Missing</td>
<td>File has been added to the Index, but the file is missing in the working tree. Use <strong>Commit</strong> to either commit just the addition or <strong>Stage</strong> to undo the addition.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<img src="attachments/1704326/1704343.png" />
</div></td>
<td>Intent-to-Add</td>
<td>File is planned to be added to the Index. Use <strong>Add</strong> or <strong>Stage</strong> to add actually or <strong>Discard</strong> to revert to untracked.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/1704341.png" /></p>
</div></td>
<td>Conflicted</td>
<td>A merge-like command resulted in conflicting changes. Use the <strong>Conflict Solver</strong> to fix the conflicts.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/10715574.png" /></p>
</div></td>
<td>Assume-Unchanged</td>
<td>File has the <em>Assume Unchanged</em> flag set. Use <strong>Toggle 'Assume Unchanged'</strong> to clear this flag.</td>
</tr>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/10715575.png" /></p>
</div></td>
<td>Skipped</td>
<td>File has the <em>Skip Worktree</em> flag set. Use <strong>Toggle 'Skip Worktree'</strong> to clear this flag.</td>
</tr>
<tr class="even">
<td><div class="content-wrapper">
<p><img src="attachments/1704326/10715572.png" /></p>
</div></td>
<td>Inaccessible</td>
<td>File's working tree content is not accessible and hence its state can't be evaluated. This usually happens if another application has an exclusive file system lock on this file. To resolve, shutdown all applications which might possibly lock this file.</td>
</tr>
</tbody>
</table>

</div>

## File table "duplicate(\!)" marker

If the file table shows a **duplicate(\!)** marker after a file name,
this means that you are on Windows or on MacOS with case-insensitive
file name and your repository contains the same file, just with changed
case. Such a constellation does not work well for (Smart)Git, so you
should resolve the problem of duplicate files. The easiest way will
probably be to fix this on a case-sensitive file system.

## Fixing 'Modified (File Mode)' on Windows

On Windows, the *Modified (File Mode)* state is usually caused due to a
misconfiguration of your local repository, when not having
`core.filemode` configuration option explicitly set to `false` (the
default value is `true`).

Hence, if this option in not present in `.git/config` of your
repository, invoke `git config core.filemode false` in the root
directory of your repository to fix this problem.

<div class="pageSectionHeader">

## Attachments:

</div>

<div class="greybox" data-align="left">

![](images/icons/bullet_blue.gif)
[directories-badge-local-direct.png](attachments/1704326/1704327.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-badge-local-indirect.png](attachments/1704326/1704328.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-conflict.png](attachments/1704326/1704329.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-default.png](attachments/1704326/1704330.png) (image/png)  
![](images/icons/bullet_blue.gif)
[directories-ignored.png](attachments/1704326/1704331.png) (image/png)  
![](images/icons/bullet_blue.gif)
[directories-merge.png](attachments/1704326/1704332.png) (image/png)  
![](images/icons/bullet_blue.gif)
[directories-missing.png](attachments/1704326/1704333.png) (image/png)  
![](images/icons/bullet_blue.gif)
[directories-root.png](attachments/1704326/1704334.png) (image/png)  
![](images/icons/bullet_blue.gif)
[directories-submodule-modified-index.png](attachments/1704326/1704335.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-submodule-modified-wt-index.png](attachments/1704326/1704336.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-submodule-modified-wt.png](attachments/1704326/1704337.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-submodule-unscanned.png](attachments/1704326/1704338.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[directories-unversioned.png](attachments/1704326/1704339.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[files-added.png](attachments/1704326/1704340.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-conflict.png](attachments/1704326/1704341.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-ignored.png](attachments/1704326/1704342.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-intent-to-add.png](attachments/1704326/1704343.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-missing.png](attachments/1704326/1704344.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-modified-added.png](attachments/1704326/1704345.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[files-modified-staged.png](attachments/1704326/1704346.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[files-modified.png](attachments/1704326/1704347.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-removed.png](attachments/1704326/1704348.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-staged.png](attachments/1704326/1704349.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-unchanged.png](attachments/1704326/1704350.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-unversioned.png](attachments/1704326/1704351.png) (image/png)  
![](images/icons/bullet_blue.gif)
[renamed.png](attachments/1704326/5275734.png) (image/png)  
![](images/icons/bullet_blue.gif)
[renamed-source.png](attachments/1704326/5275735.png) (image/png)  
![](images/icons/bullet_blue.gif)
[renamed-untracked.png](attachments/1704326/5275736.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-inaccessible.png](attachments/1704326/10715572.png) (image/png)  
![](images/icons/bullet_blue.gif)
[assume-unchanged.png](attachments/1704326/10715573.png) (image/png)  
![](images/icons/bullet_blue.gif)
[files-assume-unchanged.png](attachments/1704326/10715574.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[files-skipped.png](attachments/1704326/10715575.png) (image/png)  
![](images/icons/bullet_blue.gif)
[renamed-modified.png](attachments/1704326/19923031.png) (image/png)  

</div>
