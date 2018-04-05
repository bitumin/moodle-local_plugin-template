# Moodle local plugin template

The following steps should get you up and running with this local plugin boilerplate code.

### 1. Download repository

Unzip this repo or clone it within the Moodle directory `local/newmodule`

### 2. Rename files and references

Pick a name for the new plugin. The plugin name MUST be lower case and can't contain underscores. You should check https://moodle.org/plugins/ to make sure that your name is not already used by an other local plugin. Registering the plugin at https://moodle.org/plugins/registerplugin.php will secure it for you.

From the command line run the bash script `rename.sh`. For example, if the name you have chosen is "tictactoe" run:

```bash
sh rename.sh --name=tictactoe --copyright="2018 Mitxel Moriana <mitxel+moriana@my-email.com>"
```

If the script is successful it will create a new local plugin folder with the provided name and all the renaming operations done. Then you may delete this repository folder.  

If this script fails or if you prefer to do the renaming operations manually, follow this steps: 

* Rename the newmodule/ folder to the name of your plugin (eg "tictactoe").

* Edit all the files in this directory and its subdirectories and change
  all the instances of the string "newmodule" to your module name
  (eg "tictactoe"). If you are using Linux, you can use the following command
  $ find . -type f -exec sed -i 's/newmodule/tictactoe/g' {} \;
  $ find . -type f -exec sed -i 's/NEWMODULE/TICTACTOE/g' {} \;

  On a mac, use:
  $ find . -type f -exec sed -i '' 's/newmodule/tictactoe/g' {} \;
  $ find . -type f -exec sed -i '' 's/NEWMODULE/TICTACTOE/g' {} \;

* Rename the file lang/en/local_newmodule.php to lang/en/local_tictactoe.php
  where "tictactoe" is the name of your module

* Modify version.php and set the initial version of you plugin.

* Update the copyright information withing all the files.

### 3. Plugin installation

Visit `Settings > Site Administration > Notifications` and run the plugin installation/update.

### Happy coding!

You may now proceed to write and run your own code.

Check `db/access.php` to add capabilities.

Go to `Settings > Site Administration > Development > XMLDB editor` and add or modify the local plugin's DB tables if you need any SQL data persistence. Check `db/install.xml`, `db/install.php`, `db/upgrade.php` and `db/uninstall.php` to setup common DB managing operations.

We encourage you to share your code and experience in http://moodle.org

Good luck!
