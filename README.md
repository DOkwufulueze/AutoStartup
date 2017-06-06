# Auto Startup

- Purpose: This script opens new tabs on terminal and excutes custom commands automatically.
- Author: Daniel Okwufulueze
- Date: 12/03/2017


# Dependency: xdotool
        # Install xdotool
          sudo apt-get install xdotool

# Usage:
        auto-startup [-h | --help]
        auto-startup [-c | --command quoted-semicolon-separated-commands]
        auto-startup [-f | --file-name fileName]
        auto-startup [-c | --command quoted-semicolon-separated-commands]
                [[-b | --black-hole] | [-n | --nohup] | [-o | --output file-path]]
        auto-startup [-f | --file-name fileName]
                [[-b | --black-hole] | [-n | --nohup] | [-o | --output file-path]]

# Options:
        # -c | --command:
        This option receives the list of your custom commands in
        quoted string all separated by semicolons [;].
        For example: auto-startup --command "cd daniel; do_something; do_another_thing".

        # -f | --file-name:
        This option receives the name of the file containing
        all the commands you want to run.
        Each command in the file should take a
        line [separate commands with new line characters].

        # -h | --help:
        This option displays this help page.

# Flags:
        # -b | --black-hole:
        If this flag is set, then all output from the
        running processes will be redirected to the /dev/null black-hole.

        # -n | --nohup:
        This flag creates a nohup.out file in the working
        directories of the running processes and redirects all output
        from the running processes to the nohup.out file.

        # -o | --output:
        The --output flag takes the path of the file you
        intend to use for output of running processes.
        If the file does not exist, it will be created.
        All output from the running processes will be redirected
        to the specified file of the --output flag.

# Installation:
        Clone this repo.
        Add auto-startup to your PATH so you can simply execute it from anywhere in your terminal by entering the following in your shell rc file, say bashrc, zshrc, etc:
        
        [[ $PATH =~ "path/to/auto-startup" ]] || export PATH=$PATH:path/to/auto-startup

        On your terminal, source the rc file thus [~/.bashrc for example]:
        source ~/.bashrc

        You can now execute auto-startup by simply typing the command below on your terminal:
        auto-startup [option] [flag]

        Done.
<br><br>
### Please send bug issues you may encounter to [Issues](https://www.github.com/DOkwufulueze/AutoStartup/issues)
<br><br>
## Copyleft
![Copyleft](/images/copyleft.png) 2017 Daniel Okwufulueze
<br><br>
## Licence
This application is distributed under the [GNU GPL-3.0](https://github.com/DOkwufulueze/AutoStartup/blob/master/LICENCE.md) licence
