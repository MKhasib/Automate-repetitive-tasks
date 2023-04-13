# Automate repetitive tasks with custom Git commands

# Installation
1. Create a base folder for all of your commands
```bash
mkdir my-git-custom-commands
```
2. Create file name with git-commandName
. In this tutorial we will be creating the following files:
```bash
touch git-lazyrebase
touch git-remote-diff
touch git-lazypush
touch git-lazyrebase-push-force
touch git-lazyammend-push-force
touch git-lazycheckout
```
3. Make each file executable
```bash
chmod +x  git-lazyrebase
chmod +x  git-remote-diff
chmod +x  git-lazypush
chmod +x  git-lazyrebase-push-force
chmod +x  git-lazyammend-push-force
chmod +x  git-lazycheckout
```
4. Add your commands directory to PATH
```bash
export PATH=$PATH:/your-directory/my-git-custom-commands
```
5. Refresh your terminal
```bash
source ~/.zshrc
```
6. Save configuration on terminal startup
```bash
nano ~/.zshrc
```
and put this command in it
```bash
export PATH=$PATH:/your-directory/my-git-custom-commands
```
7. Make aliases to run them with ease
```bash
git config --global alias.r 'lazyrebase'
git config --global alias.ll 'log --oneline'
git config --global alias.rd 'remote-diff'
git config --global alias.p 'lazypush'
git config --global alias.rpf 'lazyrebase-push-force'
git config --global alias.apf 'lazyammend-push-force'
git config --global alias.c 'lazycheckout'
```

## Running
```bash
# Rebase to latest changes in develop branch
git r develop 
# Shows log with one line
git ll
# Shows diff between remote branch and local
git rd 
# Commit and push changes to remote
git p "commit message" 
# Rebase to provided branch followed by force push current branch
git rpf develop
# Add latest changes to last commit and force push it
git apf
# Save local directory, checks branch and pull changes from remote to local
git c develop