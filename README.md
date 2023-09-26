How to create SSH on Git



Git Commands:

-          git init- initialises a new Git repository

-          git clone- creates a copy of a Git repository on your local machine

-          git add- stages changes or files for the next commit

-          git commit –m – records the changes in the Git repository with a commit message

-          git status- shows the current status of the working directory, including staged and unstaged changes

-          git log- displays a log of all commits in the repository

-          git branch- lists all the branches in the repository

-          git checkout- switches to a different branch

-          git pull- fetches changes from a remote repository and merges then into the current branch

-          git push- pushes local commits to a remote repository

-          remove directory- rm –rf .(“directory”)

 

SSH connect to GitHub

1)      make a directory = mkdir .ssh
![ssh 1.PNG](..%2F..%2F..%2F..%2F..%2F..%2FDownloads%2Fssh%201.PNG)

2)      1s  -a = shows directories & hidden directories

3)      cd .ssh

4)      create public and private key= ssh-keygen –t rsa –b 4096 –C “ADD EMAIL”

5)      Enter file in which to save the key= “github_ssh”

6)      cat “public key”
![ssh2.PNG](..%2F..%2F..%2F..%2F..%2F..%2FDownloads%2Fssh2.PNG)


7)      copy ssh and print in ssh github "cat public key content 
![github1.PNG](..%2F..%2F..%2F..%2F..%2F..%2FDownloads%2Fgithub1.PNG)




8) eval `ssh-agent`
![eval.PNG](..%2F..%2F..%2F..%2F..%2F..%2FDownloads%2Feval.PNG)


9) ssh -T git@github.com
9) ssh-add ~/.ssh/ (add private key)



10) git remote set-url origin (add respository URL)

![22.PNG](..%2F..%2F..%2F..%2F..%2F..%2FDownloads%2F22.PNG)

11)
 

