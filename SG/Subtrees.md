# Subtrees

Subtrees allow to integrate contents from other repositories into
sub-folders of your main repository. They are an alternative to
[Submodules](Submodules).

## Subtrees in the UI

Refs belonging to subtrees will be denoted in the **Branches** view by a
*folder*-symbol. The root commits of a subtree will be denoted the same
way in the Log **Graph**.

## Basic Subtree operations

To add a new subtree, select the root directory of the repository in the
**Repositories** view and invoke **Remote|Subtree|Add**.

To merge (or cherry-pick) a subtree use the **Merge**
(or **Cherry-Pick**) command. SmartGit will understand whether the
source commit is a subtree and in this case perform a subtree merge (or
cherry-pick).

To reset your main repository to a certain subtree, first **Check Out**
the branch which should be reset. Then, in the **Branches** view, select
the subtree branch to which your main repository should be reset to and
invoke **Subtree|Reset** from the context menu.

<div>

<div>

If there are already existing subtrees in your main repository you will
have to add corresponding remotes for these subtrees using
**Remote|Add**.

</div>

</div>

## Synchronizing changes back to the subtree repository

After having applied changes to files in your main repository which
actually belong to a subtree repository, you can "synchronize" these
changes back to the subtree repository using the **Split** command:

1.  **Check Out** the main repository's branch which should be split
    back.

2.  In the **Branches** view, select the subtree branch to which the
    changes should be split back and invoke **Subtree|Split** from the
    context menu. The commits created by the *Split*-command will be
    written to the **Subtree-Branch to update**.  
    
    1.  if you have selected a local subtree branch, SmartGit will
        pre-populate the **Subtree-Branch to update** field with the
        selected branch's name
    
    2.  if you have selected a remote subtree branch, you will have to
        select **Subtree-Branch to update** or enter the name of a new
        branch there; in either case the selected branch will then be
        updated/created
        
        <div>
        
        <div>
        
        SmartGit will not actually split changes back to this
        particular *branch* but the branch selection serves primarily
        to identify to which *subtree* the changes should be split back.
        The underlying Git command will then detect the appropriate
        subtree commits onto which the new commits will be split back.
        
        </div>
        
        </div>

3.  To push changes back to your remote subtree repository, you will
    have to set up tracking between the local subtree branch which has
    just been updated/created in step 2 and the remote subtree branch.
    
    1.  In the **Branches** view, select both the local and remote
        subtree branch and invoke **Set Tracked Branch** from the
        context menu.
    
    2.  The **Branches** will now denote ahead/behind commits for the
        local subtree branch.
    
    3.  Verify these ahead/behind commits also in the **Graph**.
    
    4.  Push back the subtree commits by selecting the local subtree
        branch in the **Branches** view and invoking **Push** from the
        context menu.
        
          

  

  

<div class="pageSectionHeader">

## Attachments:

</div>

<div class="greybox" data-align="left">

![](images/icons/bullet_blue.gif)
[submodule-skipped.png](attachments/43745493/43745476.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-staged.png](attachments/43745493/43745477.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-unchanged.png](attachments/43745493/43745478.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-uninitialized.png](attachments/43745493/43745479.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-unknown.png](attachments/43745493/43745480.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-url-mismatch.png](attachments/43745493/43745481.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-missing.png](attachments/43745493/43745482.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-modified.png](attachments/43745493/43745483.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-modified-added.png](attachments/43745493/43745484.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-modified-staged.png](attachments/43745493/43745485.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-nested-root.png](attachments/43745493/43745486.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-removed.png](attachments/43745493/43745487.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-added.png](attachments/43745493/43745488.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-assume-unchanged.png](attachments/43745493/43745489.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-conflict.png](attachments/43745493/43745490.png)
(image/png)  
![](images/icons/bullet_blue.gif)
[submodule-empty.png](attachments/43745493/43745491.png) (image/png)  
![](images/icons/bullet_blue.gif)
[submodule-intent-to-add.png](attachments/43745493/43745492.png)
(image/png)  

</div>
