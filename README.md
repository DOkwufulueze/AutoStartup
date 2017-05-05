- Purpose: Open new tabs in terminal and excute custom commands automatically.
- Author: Okwufulueze Emeka Daniel
- Date: 12/03/2017


# Install xdotool
```
  sudo apt-get install xdotool
```

# Clone this repo or start from scratch:
You can simply clone this repo and modify as necessary or you can start from scratch and create your own shell script, say auto-startup like I have in this repo.
```
  touch auto-startup
  sudo chmod +x auto-startup
```

# If you started from scratch with your file named 'auto-startup' for instance, place the script below in auto-startup.
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

# If you didn't start from scratch [meaning you cloned this repo], simply proceed to the next step

# Execute the script from its parent directory
On your terminal, in the directory containing auto-startup, simply execute the script by:
```
  ./auto-startup
```

# Execute the script from any directory
You can also add auto-startup to your PATH so you can just execute it from anywhere in your terminal by entering the following:
```
  export PATH=$PATH:~/directory-name
  # where directory-name is the name of the directory containing auto-startup
```
After which you can execute auto-startup by simply typing the command below on your terminal:
```
  auto-startup
```
# Enjoy...
