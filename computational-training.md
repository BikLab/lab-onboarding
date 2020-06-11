##Computational Training

Georgia Advanced Computing Research Center (GACRC)

**Step 1: Get an account on the GACRC** - New lab members will need Holly to fill out this form to request a new HPCC user account (please bug her in person if she doesn't remember): https://uga.teamdynamix.com/TDClient/2060/Portal/Requests/ServiceDet?ID=25839

**Step 2: Familiarize yourself with the GACRC guides and training resources** - sign up for a course (or two, or three) if you are a new user or could use a refersher on cluster usage and job submission: https://wiki.gacrc.uga.edu/wiki/Georgia_Advanced_Computing_Resource_Center

**Step 3: Set up a secure ssh key on your personal laptop/desktop** - this is **highly recommended** since you will need to login to the GACRC all the time. An ssh key will minimize time and hassle it takes for terminal logins. Follow these steps:

1. Make a ssh-key on your local computer using the command `ssh-keygen -t rsa`. It will ask you where you’d like to save the key. Press enter for the default location. If you open a new terminal window to do this, the default location will most likely be your home directory. Before you generate your ssh key, use `pwd` (print working directory) to find your location and/or use `cd` to move to your home directory before you proceed.
2. It might ask you to make a password. You can create one or press Enter to skip this step
3. Then add a copy of your key to the cluster using `ssh-copy-id USERNAME@sapelo2.gacrc.uga.edu`. Youre USERNAME should be your alphanumeric UGA MyID (e.g. abcd12345). If the copy id command doesn't work, then you’ll first need to download/install it using homebrew with `brew install ssh-copy-id`
4. Create an alias on your local machine by adding `alias gacrc="ssh USERNAME@sapelo2.gacrc.uga.edu"` to your `.bash_profile` ile (this file will be in your home directory, or you can create it fresh using a command line text editor, e.g. `vim ~/.bash_profile` and then paste the alias command into the blank text file and then type `;wq` to write the file and quit vim). In the alias command, you can use "gacrc" or replace this text with whatever phrase/word you prefer.
5. Now, to login to the GACRC you should be able to open a new terminal window, type your short alias phrase (such as `gacrc`) and you will be logged into the GACRC after you enter your UGA MyID password and complete the two-factor DUO authentication. *Note if you are logging into the HPCC from off campus, you will first need to open a UGA VPN connection before carrying out these terminal login steps: https://eits.uga.edu/access_and_security/infosec/tools/vpn/*
6. To delete or change your ssh-key password (it can get annoying), you can use the command `ssh-keygen -p -P OLDPASSWORD -N "" -f ~/.ssh/id_rsa` on your local computer, where you replace OLDPASSWORD with your old password. the `-N ""` will remove the password entirely, if you just want to change your password then replace the quotes with your new password.
