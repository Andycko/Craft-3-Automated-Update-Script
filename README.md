# Craft-3-Automated-Update-Script
This is a short bash script written by Andrej Szalma for updating Craft 3 projects autonomously.

This also takes care about GIT (fetch, merge, commit, push), therefore a local & remote repository needs to be set up already. There also needs to be a branch different than the master, as you usually don't want to change the files directly on the master branch.

Could be used in a cronjob to udpate Craft 3 websites on regular basis as the Craft & Plugin updates are coming out pretty often.
