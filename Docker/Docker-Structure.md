<style>
.md0{margin-top: 150px;}
.md1{margin-top: 75px;}
.md2{margin-top: 50px;}
.md3{margin-top: 25px;}
.md4{margin-top: 10px;}
.tbl1 td#header{background-color: D1ECCF}
.tbl1 tr#header{background-color: D1ECCF}
</style>


# [<span style="color:black;">Docker Structure</span>](Docker.md)
[Basic](Docker-Basic.md) | 
[Structure](Docker-Structure.md) | 
[Script](Docker-Script.md)


<div class="md3"></div>
<a href="#Config">Config</a> - 
<a href="#file-track">File Track</a> - 
<a href="#File-level">File level</a> - 
<a href="#Location">Location</a> - 
<a href="#Operation">Operation</a>






<div class="md1"></div>

## Config

#### Level

Local
<br>
Global
<br>
System
<br>
worktree

#### Object
user
<br>
color highlighting
<br>
default editor
<br>
default merge tool







<div class="md0"></div>

## File Track

#### Work directory

#### Stage

#### Repository






<div class="md0"></div>

## File level

#### Repository

#### Branch

#### Tag

#### Version





<div class="md0"></div>

## Location

#### Local

#### Remote




<div class="md0"></div>

## Operation

#### Start a working area

| Command | Explain |
| ------ | ------ |
| init | <span align="right" dir="rtl"> Create an empty Docker repository or reinitialize an existing one <span>  |
| clone | <span align="right" dir="rtl"> Clone a repository into a new directory <span>  |

<div class="md1"></div>

#### Work on the current change

| Command | Explain |
| ------ | ------ |
| add | <span align="right" dir="rtl"> Add file contents to the index <span>  |
| mv | <span align="right" dir="rtl"> Move or rename a file, a directory, or a symlink <span>  |
| restore | <span align="right" dir="rtl"> Restore working tree files <span>  |
| rm | <span align="right" dir="rtl">  Remove files from the working tree and from the index <span>  |
| sparse-checkout | <span align="right" dir="rtl"> Initialize and modify the sparse-checkout <span>  |

<div class="md1"></div>

#### Examine the history and state 

| Command | Explain |
| ------ | ------ |
| bisect | <span align="right" dir="rtl"> Use binary search to find the commit that introduced a bug <span>  |
| diff | <span align="right" dir="rtl"> Show changes between commits, commit and working tree, etc <span>  |
| grep | <span align="right" dir="rtl"> Print lines matching a pattern <span>  |
| log | <span align="right" dir="rtl"> Show commit logs <span>  |
| show | <span align="right" dir="rtl">  Show various types of objects <span>  |
| status | <span align="right" dir="rtl"> Show the working tree status <span>  |

<div class="md1"></div>

#### grow, mark and tweak your common history

| Command | Explain |
| ------ | ------ |
| branch | <span align="right" dir="rtl"> List, create, or delete branches <span>  |
| commit | <span align="right" dir="rtl"> Record changes to the repository <span>  |
| merge | <span align="right" dir="rtl"> Join two or more development histories together <span>  |
| rebase | <span align="right" dir="rtl"> Reapply commits on top of another base tip <span>  |
| reset | <span align="right" dir="rtl"> Reset current HEAD to the specified state <span>  |
| switch | <span align="right" dir="rtl"> Switch branches <span>  |
| tag | <span align="right" dir="rtl"> Create, list, delete or verify a tag object signed with GPG <span>  |

<div class="md1"></div>

#### Collaborate

| Command | Explain |
| ------ | ------ |
| fetch | <span align="right" dir="rtl"> Download objects and refs from another repository <span>  |
| pull | <span align="right" dir="rtl"> Fetch from and integrate with another repository or a local branch <span>  |
| push | <span align="right" dir="rtl"> Update remote refs along with associated objects <span>  |