# Craft-3-Automated-Update-Script
This is a short bash script written by *Andrej Szalma* for updating **Craft 3** projects autonomously.

This also takes care about GIT (fetch, merge, commit, push), therefore a local & remote repository needs to be set up already. There also needs to be a branch different than the master, as you usually don't want to change the files directly on the master branch.

Could be used in a cronjob to update **Craft 3** websites on regular basis as the Craft & Plugin updates are coming out pretty often.

## Instructions:

### 1. Make sure to have Craft3 setup correctly
  * For the Craft-CLI to work you need to have your `.env` and `db.php` files setup correctly. If you are using **MAMP** on **mac**, you will have to add a line to both of these files -> You have to add your DB Unix Socket.
  * ### 1. Environment file
    * add this to the end of your `.env` file
    * `DB_SOCKET="/Applications/MAMP/tmp/mysql/mysql.sock"`
  * ### 2. Database config file
    * add this to the end of the return statement in your `db.php` file
    * `'unixSocket' => getenv('DB_SOCKET')` - *Dont forget tu put a comma after the penultimate line*

### 2. Place script
  * Place this script in your `/usr/local/bin/` folder

### 3. Make it an executable
  * For this script to run, it needs permisions to be executed, therefore we need to give those by this command:
    * `chmod u+x /usr/local/bin/craft3updater`

### 4. Add to the PATH
  * For your script to be executable from anywhere whithout the need to write the whole path, you need to export it to your PATH:
  * #### 1. Edit the `.bash_profile` file: 
    * `sudo nano /Users/*username*/.bash_profile`
  * #### 2. Add your script there:
    * `export PATH="/usr/local/bin/craft3updater:$PATH"`

### 5. Run it
  * Finaly navigate to the folder, where all your websites live and run the script by typing `craft3updater`

### 6. Success
  * If everything worked and the updates were successful, you should have an **"Updated Craft CMS & Plugins"** commit on your local & remote repository. Make sure to have `composer update` ran on your staging/develop server to ensure all the updates are installed there as well.

## Thank you for using my script, feel free to make any tweaks to it so it suits your own needs.
