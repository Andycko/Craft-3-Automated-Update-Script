# Craft-3-Automated-Update-Script
This is a short bash script written by *Andrej Szalma* for updating **Craft 3** projects autonomously.

This also takes care about GIT (fetch, merge, commit, push), therefore a local & remote repository needs to be set up already. There also needs to be a branch different than the master, as you usually don't want to change the files directly on the master branch.

Could be used in a cronjob to update **Craft 3** websites on regular basis as the Craft & Plugin updates are coming out pretty often.

## Instructions:
### 2. Place the **craft3updater** folder
  * Place the **craft3updater** folder to your `/usr/local/` folder

### 3. Make the script an executable
  * For this script to run, it needs permisions to be executed, therefore we need to give those by this command:
    * `chmod u+x /usr/local/craft3updater/bin/craft3updater`

### 4. Add to the PATH
  * For your script to be executable from anywhere whithout the need to write the whole path, you need to export it to your PATH:
  * #### 1. Edit the `.bash_profile` file: 
    * `sudo nano /Users/*[username]*/.bash_profile`
  * #### 2. Add your script there:
    * `export PATH="/usr/local/craft3updater/bin:$PATH"`

### 5. Run it
  * Finaly navigate to the folder, where all your websites live and run the script by typing `craft3updater`

### 6. Success
  * If everything worked and the updates were successful, you should have an **"Updated Craft CMS & Plugins"** commit on your local & remote repository. Make sure to have `composer update` ran on your staging/develop server to ensure all the updates are installed there as well.

### 7. Debugging
  * The updater now creates a `updater.log.out` log file in the folder it is run. It consists a timestamp for every webpage that it updates and the complete output from all commands that are run during the updating process.
### Thank you for checking out this repo, feel free to make any tweaks to the script so it suits your own needs.
