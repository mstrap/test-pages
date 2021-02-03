# Git-Flow Light

Git-Flow Light is a SmartGit-specific subset of Git-Flow which just
deals with **Development** and **Feature** branches.

### Develop Branch

The single 'develop' branch (named by default `develop`) contains the
ongoing development line. It contains all finished improvements and
fixes.

### Feature Branches

For each new (non-trivial) improvement which should be added to the
ongoing development line, a separate 'feature' branch is created (named
by default, e.g. `feature/my-feature`). This temporary branch will be
used to work independently on this particular improvement ('feature').
If one thinks the feature is done, the commits from the 'feature' branch
are integrated (either merged or rebased) into the
[develop](#Git-FlowLight-flow.develop) branch and the feature branch
will usually be deleted. This way all feature branches in a repository
indicate the features which are currently worked on.

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` text
o ... [> develop] merged feature A
| \
|  o ... a feature commit
|  |
o  | ... a develop commit
| /
o  ... another develop commit
```

</div>

</div>

### Configuration

To start using Git-Flow Light for your repository, invoke
**Branch|Git-Flow|Configure**, select **Light** type here and adjust the
branch names. For existing repositories, you will usually set `master`
as your development branch.

Regarding available commands, have a look at [the main Git-Flow
documentation](https://www.syntevo.com/doc/display/SG/Git-Flow#Git-Flow-Git-FlowCommandsflow.commands).
