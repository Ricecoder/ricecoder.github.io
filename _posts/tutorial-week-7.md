##[How to Authenticate GitHub on the Terminal with Git](https://help.github.com/articles/caching-your-github-password-in-git/)

Maybe you've just signed up for GitHub and installed Git to use on your command line or perhaps you have been using 
both for a while but never set up your terminal so you wouldn't have to retype your username and password every time you 
`git push`. There are two methods to do this: Connecting over HTTPS which is recommended by GitHub, and connecting over SSH.
This tutorial will use the HTTP method.

1. First you need to verify that you have osxkeychain installed on your computer. You can do this by typing the following command 
into your terminal.

`$ git credential-osxkeychain` 

If it _is_ available it will return:

`Usage: git credential-osxkeychain <get|store|erase>`

Move to step 3.

If _not_ it will return:

`git: 'credential-osxkeychain' is not a git command. See 'git --help'.`

2. If it is _NOT_ installed then install it using curl in the terminal like this:
```
$ curl -s -O \
https://github-media-downloads.s3.amazonaws.com/osx/git-credential-osxkeychain
```
This will download the helper. Next type:

`chmod u+x git-credential-osxkeychain`

This will fix the permissions so it can run.

3. Once you have it installed we need to move it to the same directory that Git is in. 

```
$ sudo mv git-credential-osxkeychain \ 
"$(dirname $(which git))/git-credential-osxkeychain"
```
`sudo` is a command giving you ultimate authority to move the helper. `which git` gets the command path (location) of git
so that we can move the helper there.

At this point your terminal will ask for a password. This is the password to your computer and not the password you use for github.

4. The last step is to tell Git to use the helper aka osxkeychain globally.

`$ git config --global credential.helper osxkeychain`

5. Now the next time you are asked to enter your username and password for Github it will store this information in your keychain 
so you will no longer be required to type it in anymore.
