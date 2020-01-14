# Craft-3-Automated-Update-Script
This is a short bash script written by *Andrej Szalma* for updating **Craft 3** projects autonomously.

This also takes care about GIT (fetch, merge, commit, push), therefore a local & remote repository needs to be set up already. There also needs to be a branch different than the master, as you usually don't want to change the files directly on the master branch.

Could be used in a cronjob to update **Craft 3** websites on regular basis as the Craft & Plugin updates are coming out pretty often.

## Instructions:

### 1. Place script
  * Place this script in your /usr/local/bin/ folder

### 2. Make it an executable
  * For this script to run, it needs permisions to be executed, therefore we need to give those by this command:
    * `chmod u+x /usr/local/bin/craft3updater`

### 3. Add to the PATH
  * For your script to be executable from anywhere whithout the need to write the whole path, you need to export it to your PATH:
  * #### 1. Edit the `.bash_profile` file: 
    * `sudo nano /Users/*username*/.bash_profile`
  * #### 2. Add your script there:
    * `export PATH="/usr/local/bin/craft3updater:$PATH"`

### 4. Run it
  * Finaly navigate to the folder, where all your websites live and run the script by typing `craft3updater`
