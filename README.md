Purpose: Open new tabs in terminal and excute custom commands automatically.
Author: Okwufulueze Emeka Daniel
Date: 12/03/2017


# Install xdotool
```
  sudo apt-get install xdotool
```
# After installation of xdotool, create a shell script and make it executable:
```
  touch my-shell-script
  sudo chmod +x my-shell-script
```
Then place the script below in my-shell-script.

```
#!/bin/bash
# The SHELL_COMMANDS variable below is an array of commands you want to execute on new tabs. I have written out some for example. Remember to separate the array values with spaces
SHELL_COMMANDS=('cdyanpals; npm run dev' 'cdwscore; sh serverd.sh' 'cdwscore; php worker.php' 'mysql-workbench');

# Loop through the array of commands and execute each one on a new tab
for ((i = 0; i < ${#SHELL_COMMANDS[@]}; i++)); do
  SHELL_COMMAND=${SHELL_COMMANDS[$i]};
  xdotool key ctrl+shift+t;
  sleep 1;
  xdotool type --delay 1 --clearmodifiers "${SHELL_COMMAND}";
  xdotool key Return;
done
```



On your terminal, in the directory containing my-shell-script, simply execute the script by:
```
  ./my-shell-script
```

You can also add my-shell-script to your PATH so you can just execute it from anywhere in your terminal by simply typing ```my-shell-script``` thus:
```
  export PATH=$PATH:~/directory-name # where directory-name is the name of the directory containing my-shell-script
```
Enjoy...
