<br />
<div align="center"> 
  <a href="https://www.linux.org/"><img align="center" src="https://www.linux.org/images/logo.png"></a>
  <h1> Linux Essentials (call it Hacks) </h1>
</div>

<br />


Check out [explainshell.com](https://explainshell.com/) for an interactive alternative to Linux man pages that enables you to quick parse queried commands.

<!--- ####################################################################################################################################################################### -->

# Keyboard shortcuts

For QWERTY-based keyboard layout on linux system.

1. `Ctrl+Shift+C`: copy selection. On Windows only `Ctrl+C`.
2. `Ctrl+Shift+V`: paste selection. On Windows only `Ctrl+V`.
3. `Ctrl+Shift+T`: open a new tab.
4. `Ctrl+PgUp`: switch to the previous tab.
5. `Ctrl+PgDn`: switch to the next tab.
6. `Ctrl+Shift+W`: close the current tab.
7. `Ctrl+R`: history search mode to show the last command matching provided characters.
8. `Ctrl+G`: leave the above history search mode.
9. `Ctrl+I or Tab`: trigger command line suggestion.
10. `Ctrl+A` or Home: go to the start of the command line.
11. `Ctrl+E` or End: Go to the end of the command line.
12. `Ctrl+W` or `Alt+Backspace`: to delete an entire word/command backward (before the cursor).
13. `Alt+D`: to delete an entire word/command onward (after the cursor).
14. `Ctrl+U`: delete all commands.
15. `Ctrl+C`: send a SIGINT signal to cancel/terminate the current process.

<!--- ####################################################################################################################################################################### -->


# Ubuntu Prelims 

Beware: the angle brackets punctuation mark denoted by "`<>`" (voiced chevrons) is only used as a placeholder, i.e, it's not a special character.

- Ubuntu version:

```bash
lsb_release -a
```

- Current user:

```bash
who
```

- To display the manual page for a particular command:

```bash
man <command>
```

- To display one-line manual page descriptions:

```bash
whatis <command>
```

- To open Gnome file manager in the current directory:

```bash
nautilus .
```

- Root privileges:

```bash
sudo su
```

- To locate the binary, source, and manual page files for a command:

```bash
whereis <command>
```

- To locate the pathname for a command:

```bash
which <command>
```


<!--- ####################################################################################################################################################################### -->

## Packages

- Adding an external repository:

```bash
sudo add-apt-repository
```

- Package Update:

```bash
sudo apt-get update
```

- Package Installation:

```bash
sudo apt-get install <package-name>
```

- Packakge Uninstallation
```bash
sudo apt-get purge --auto-remove <file>
```
and (to remove the aptitude cache)
```bash
sudo apt-get clean
```
Note: the flag `--purge` remove the configuration files, and the flag `--auto-remove` removes associated packages.

- List installed packages:
```bash
dpkg --list
```
Note: press 'q' to exit mode.
or (to locate a file in dpkg list)
```bash
dpkg --list | grep file
```
or 
```bash
apt list --installed
```
or (to list specifics)
```bash
apt list -a <package_name>
```


## [TAR-based files](https://explainshell.com/explain?cmd=tar+-xvzf#):

- Extracting:

(tar -xvzf to unpack a .gz file)
```bash
tar -xvzf <filename>.tar.gz
```
(tar -xvjf to unpack a .bz2 file)
```bash
tar -xvjf <filename>.tar.bz2
```
or (tar -xf to unpack a .xz file)
```bash
tar -xf <filename>.tar.xz
```
or (gunzip to unpack .gzip file)
```bash
gunzip <filename>.gz
```

- Installing:
```bash
./configure && make && sudo make install
```

## .sh files:

Grant execute permission:
```bash
chmod +x <file>.sh
```

Run/install the file:
```bash
./<file>.sh
```

## Debian packages:

- Install:
```bash
sudo dpkg -i package.deb
```
Or 
```bash
sudo dpkg --install package.deb
```
- Remove:
```bash
sudo dpkg -r package.deb
```
Or 
```bash
sudo dpkg --remove package.deb
```

<!--- ####################################################################################################################################################################### -->

## Directory

- Path of the current working directory:

```bash
pwd
```

- Creating a folder/directory:

```bash
mkdir <dir-name>
```
Tip: the `mkdir` command works in both Unix-like (Linux, macOS) and Windows command-line interpreters.


- Deleting an empty directory:

```bash
rmdir <dir-name>
```

- Deleting a non-empty directory:

```bash
rm -rf <dir-name>
```

- Switch to a specific folder/directory:

```bash
cd <dir-name>
```
or (if the directory name has spaces)
```bash
cd '<dir name with space>'
```

- Switching to Home directory:

```bash
cd ~
```

- Switch to root directory:

```bash
cd /
```

- Switch to one level up dir.:

```bash
cd ..
```

- Switch to the previous dir.:

```bash
cd -
```

<!--- ####################################################################################################################################################################### -->

## Files

- Listing files in the current directory:

```bash
ls
```
or (to list hidden files)
```bash
ll
```
or (to list content information)
```bash
ls -l
```
or (to list the allocated size of each file, in blocks)
```bash
ls -s
```

- To list a specific file in the current directory:

```bash
<filename>
```
or
```bash
find <filename>
```

- To list all files in the current directory with extension .jpg:

find . -name *.jpg

To list an empty file in the current directory:

```bash
find . -type f -empty
```

- Listing file properties:

```bash
stat <filename>
```
or
```bash
file <filename>
```
or
```bash
ls -l <filename>
```

- To read a file (.txt, .md, .yml):

```bash
less <filename>
```
or
```bash
nano <filename>
```
or (to open the file with gedit)

```bash
gedit <filename>
```

- To read a .pdf file:

```bash
evince <filename.pdf>
```

- Creating a `.txt` file:

```bash
cat > <filename>.txt 
```
or (to create and add a text string to the file)
```bash
echo "This is a string" > <filename>.txt
```

- Updating a `.txt` file:

```bash
echo "new text string" >> <filename>.txt
```

- Cloning a file to the current directory:

```bash
cp -iv ~/<path-dir-name>/<filename> .
```

Note1: the `-i` flag stands for `interactive mode` and enables the user to choose to overwrite the file.

Note2: the `-v` flag stands for `verbose`, to enable progress display.

Note3: flags can be concatenated, such as in `-iv`.

- Cloning a file to a different directory:

```bash
cp -iv ~/<path-dir-name> ~/<path-new-dir>/
```
or (for a file in the current directory)
```bash
cp -i filename ~/<path-new-dir>/
```

- Cloning all files from a specific dir. to a new dir.:

```bash
cp -a ~/<path-dir-name> ~/<path-new-dir>/
```

- Moving an entire directory:

```bash
mv -Ri ~/<path-dir-name> ~/<path-new-dir>/
```
Note: the `-R` flag stands for `recursive` mode.

- Renaming a file:

```bash
mv <filename.extension> <new-filename.extension>
```

- Deleting a file:

```bash
rm <filename>
```
or (to delete all files from the current directory)
```bash
rm *
```
or (to delete all files with `.png` extension in interactive mode)
```bah
rm -i *.png
```

<!--- ####################################################################################################################################################################### -->

## System

- Current system info:

```bash
uname -a
```

- Distribution info:
```bash
uname -m && cat /etc/*release
```

- Kernel version:
```bash
uname -srmv
```

- System's memory usage:

```bash
free -h
```
or
```bash
free -m
```
```
'free' = wasted memory (not being used).
'available' = memory for allocation.
'buff/cache' = used memory for cache (Data has been read) and buffer (data is being written).
'free' + 'buff/cache' = 'available'.
```   

- CPU info (clock, cores, L2 and L3 cache memory...):

```bash
lscpu
```
Note: total threads = CPU core * threads per core.

- PCI (Peripheral Component Interconnect) buses (Wireless adapter, GPU...):

```bash
lspci
```
or 
```bash
lspci -v -s <id>
```

For in-depth description:
```bash
lshw 
```
or (for short)  
```bash
lshw -short
```

- On-board and off-board graphics card:

```bash
sudo lshw -C display
```

- Nvidia Graphics Card:

```jupyter
nvidia-smi
```

<!--- ####################################################################################################################################################################### -->

## Processes

- Top Processes:

```bash
top
```

- Running softwares:

```bash
ps -A 
```
or (for a specific software)
```bash
ps aux | grep <software_name>
```

- Display software PID:

```bash
pgrep <software_name>
```

- To kill a process:

```bash
sudo kill -9 <software_PID>
```


<!--- ####################################################################################################################################################################### -->

## Partition

- To list partition table:

```bash
sudo fdisk -l
```

- To list mount points (mounted drives/filesystem):

```bash
df -h
```

- To mount a partition:

```bash
sudo mount /dev/sdbX
```

<!--- ####################################################################################################################################################################### -->


# Contributors 

Created and maintained by [@camponogaraviera][1].

[1]: https://github.com/camponogaraviera
