# Add a Different Drive to FileBrowser on Windows
This is how to add a different drive to FileBrowser using Windows and Symlinks.
<br>I used this solution to connect users to VHDs to limit their capacity.

I made this cause like I had this problem, and maybe you do to or something.
<br>The solution was on Github somewhere but had like a broken link to it-

## Pre-Requisites:
- A working FileBrowser. <br>
- A different drive/VHD to connect to.

## First, we need the Command Prompt.
- Open up an Admin CMD and navigate to your FileBrowser folder.<br>
You can also go inside of the Users folder, or any folder you please.

## Second, the Command itself.
- Now we want a <b>Directory Symbolic Link</b>(DSL for brevity) so we use this:<br>
``` mklink /d linknamehere driveletter:\folder ```<br>

- This makes a Directory Symbolic Link at the CMD location.
> For example if your CMD says its at `D:\FileBrowser\users>`, the DSL will be made there.<br>

## Example:
- If we did: ```D:\FileBrowser\users> mklink /d origin F:\target```

This would make a DSL Folder called `origin` inside of `D:\FileBrowser\users`<br>
that would connect it to `F:\target`.<br>

If you gave a user the <b>scope</b> of `\users\origin` they will now see <br>inside of `F:\target` instead along with its current storage size.
