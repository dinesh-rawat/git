# How can I fix & solve merge conflicts?

![](https://s3-eu-west-1.amazonaws.com/froala-eu/temp_files%2F1544087929446-1.png)

if you keep a couple of things in mind, solving conflicts is easy as pie:

### Keep calm? <span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f600.svg);"> </span>

Git always allows you to go back to the state before the conflict occurred. With a simple "**git merge --abort**",  you can always undo the merge and start over again.

**How do I Know I Have a Conflict? <span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f631.svg);"> </span> **

When calling "git status", you'll see a special **Unmerged paths** category.  All of the items in this category are in a conflict state and need to be dealt with:

![](https://s3-eu-west-1.amazonaws.com/froala-eu/temp_files%2F1544088507557-2.png)

**Understand When & Why a Conflict Happens?<span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f61c.svg);"> </span> **

Conflicts occur when the same file was changed in contradictory ways.  If two people _just_ work on the same file, Git can most likely figure things out on its own. 

The most common situation when it _cannot_ do this is when the **exact same lines were edited** in that file. In that case, Git has no way of knowing what's correct - you'll have to look at the changes and decide how you want the file to finally look.

**A Conflict is Just an Annotation <span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f61e.svg);"> </span> **

It helps to realize that a conflict is nothing magical. In the concerned file, Git simply marks the areas that were edited in contradictory ways:

![](https://s3-eu-west-1.amazonaws.com/froala-eu/temp_files%2F1544093697458-3.png)

This helps you understand which edits were made - and even on which branches.

**Solving Means Choosing & Editing <span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f601.svg);"> </span> **

Your job now is to condition the file to its desired state. There are a couple of ways to do this:

**(a)** You can simply open the file in an editor, search for the conflict markers (see above image) and make any necessary modifications. When you're done, the file needs to look exactly as you _want_ it to look.  
**(b)** Alternatively, you can tell Git that you'll simply go with one of the edited versions, called "ours" or "theirs". 

    git checkout --ours path/to/conflict-file.css

**Wrap Up <span class="fr-emoticon fr-deletable fr-emoticon-img" style="background: url(https://cdnjs.cloudflare.com/ajax/libs/emojione/2.0.1/assets/svg/1f60e.svg);"> </span> **

When you've successfully solved all conflicts, you need to do two more things:

**(1)** Mark each conflicted file as solved. A simple "**git add <filepath>**" does this for you.  
**(2)** Commit the resolution just as you would commit any other change with the "**git commit**" command.
