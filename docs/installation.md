# Linux

## Option 1: install from `.deb` package:
To install from `.deb` package, open file from file explorer of your choice or run in command line:
```
sudo dpkg --install ./cardano-hw-cli_<VERSION>.deb
```
This will create necessary files under `/user/share/cardano-hw-cli/` and create soft link under `/usr/bin/`, so `cardano-hw-cli` command is callable in command line from everywhere.

If you wish to uninstall `cardano-hw-cli`, run:
```
sudo dpkg --remove cardano-hw-cli
```

## Option 2: uncompress `.tar.gz` archive:
if `.deb` package is not working for some reason you can uncompress the `.tar.gz` archive and create soft link to `cardano-hw-cli` manually:

Uncompress:
```
tar -zxvf cardano-hw-cli-<VERSION>.tar.gz
```

Create soft link:
```
sudo ln -s /<PATH_TO_DIRECTORY> /usr/bin
```

or add to PATH. Edit `~/.bashrc`:
```
vim ~/.bashrc
```
add path to the end of file on new line:
```
export PATH=<PATH_TO_DIRECTORY>
```

# Mac
Uncompress the `.tar.gz` archive by double clicking archive in finder or uncompress in command line:
```
tar -zxvf cardano-hw-cli-<VERSION>.tar.gz
```

Add to PATH:
```
sudo vim /etc/paths
```
add to the end of file on new line: `<PATH_TO_DIRECTORY>`

# Windows
Unzip `cardano-hw-cli-<VERSION>.zip` and add directory location to your PATH.

How to add to PATH: https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/

# Setup arguments auto-completion
This step is optional.

## Linux and windows
Append contents of https://github.com/vacuumlabs/cardano-hw-cli/blob/develop/scripts/autocomplete.sh to the `~/.bashrc`.

On windows this works with Git Bash.

## Mac
Check https://github.com/vacuumlabs/cardano-hw-cli/blob/develop/docs/installation-macos-autocomplete.md