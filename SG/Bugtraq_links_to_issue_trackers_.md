# Bugtraq (links to issue trackers)

If you have set up a so called *Bugtraq Configuration*, SmartGit will
detect issue IDs in commit messages and display links to the issue
tracker in this case. The Bugtraq configuration is stored either in the
`.gitbugtraq` file in your repository root (for all users of the
repository) or in your repositories' `.git/config` (just for you). It
consists of a named `bugtraq` section which basically defines a regular
expression to match issue IDs in your commit message and an URL template
to open when clicking at such an issue link.

<div class="panel" style="border-width: 1px;">

<div class="panelHeader" style="border-bottom-width: 1px;">

**Example**

</div>

<div class="panelContent">

An example configuration for the *JIRA* issue tracker at URL
`https://host/jira` for a project called 'SG' looks like the following.

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` text
[bugtraq "jira"]
 url = https://host/jira/browse/SG-%BUGID%
 logRegex = SG-(\\d+)                   
```

</div>

</div>

The above example will make only the issue numbers as links (i.e.
without `SG-`). Alternatively, if you want to have the entire issue ID
as link (i.e. with `SG-`), you may use:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` text
[bugtraq "jira"]
 url = https://host/jira/browse/%BUGID%
 loglinkregex = SG-\\d+
 logregex = \\d+            
```

</div>

</div>

For multiple *JIRA* projects, a configuration could look like:

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` text
[bugtraq "jira"]
 projects = SG
 url = https://host/jira/browse/%PROJECT%-%BUGID%
 loglinkregex = %PROJECT%-\\d+
 logregex = \\d+            
```

</div>

</div>

Another example configuration (e.g. for a trouble ticketing system)
where IDs like '\#213' should be matched only at the beginning of a
commit message. Note that the logregex needs to be put in quotes,
because '\#' serves as a comment character in Git configuration files.

<div class="code panel pdl" style="border-width: 1px;">

<div class="codeContent panelContent pdl">

``` text
[bugtraq "otrs"]
 url = "https://otrs/index.pl?Action=AgentTicketZoom;TicketID=%BUGID%"
 logregex = "^#[0-9]{1,5}"            
```

</div>

</div>

</div>

</div>

The `logRegex` must contain only one matching group '()' matching the
issue ID. You can use additional non-matching groups '(?:)' for other
parts of your regex (or '(?i)' for case insensitive matching). For more
details refer to the complete specification at
<https://github.com/mstrap/bugtraq>.
