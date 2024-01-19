# learn-raspberrypi

Last update all notes on: 8-Dec-2021.

# Playing mp3 file

Date: 19 Jan, 2024

**NOTE: For some reason the mp3 jack isn't working with ubuntu, but the connection with bluetooth works which is actually awesome though because I can keep it near me all the time. Yikes.**

```bash
# Download sample mp3 file
wget https://download.samplelib.com/mp3/sample-3s.mp3

# Play mp3 file with ffmplay utility:
# Install ffmpeg
sudo apt install ffmpeg
# Play mp3 file:
ffplay -nodisp ./sample-3s.mp3

# With sax:
# Installation: ```
sudo apt-get install sox libsox-fmt-all

# Play mp3 file:
play sample-3s.mp3
```

***

Active host: pi-sahil1.ddns.net

Know about system: `hostnamectl` command.

##### Current port forwards

80 and 3001-> 3010

**Can't fix port mapping ? Possible reasons:**

- You have defined multiple port forwards for the same port number. (		:LOL: This was the issue for me		)

# Files

File: `~/.bashrc-extended`. I have `source ~/.bashrc-extended` command in my `~/.bashrc` file.

```
alias temperature='/opt/vc/bin/vcgencmd measure_temp'
alias c='clear'
alias ...='. ~/.bashrc'
alias vi.bashrc-extended='vi ~/.bashrc-extended'
alias ..='cd ..'
```


## Note

```bash
top
stress -c 8
```

## noip2

Dynamic update client [docs here](https://my.noip.com/dynamic-dns/duc).

```
noip2 			# Runs noip2 service.
noip2 -h 		# Shows help from noip2

noip2 -S 		#Shows status: *Use sudo to run command in root mode
			# coz first time after creating a configuration it 
			# doesn't without sudo prefixed, yikes!
			
			# If above command says configuratio file is in use by process <ID>. FIX: Simply kill the process by `kill <ID>` and then it would work.
			# In the process of creating a config file it'll ask for update inteval time you can choose default(30mins) by simply pressing Enter but 			 # its' good to use 10mins.
			
noip2 -K 702 		# Delete an existing configuration running task.
sudo noip2 -C 		# Use this command to create a new config after terminating a existing running process.
```

**IMPORTANT After installating noip2** give read permission to the configuration file to all the users by below command,
and the `.profile` file would be able to run use the configuration without any 
silly error, yikes!!

`sudo chmod +rwx /usr/local/etc/no-ip2.conf`


## Install nvm on pi-os

```
sudo apt install curl 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash 
source ~/.profile

# Install node v14
nvm install 14
```

[Source](https://tecadmin.net/how-to-install-nvm-on-ubuntu-20-04/)
