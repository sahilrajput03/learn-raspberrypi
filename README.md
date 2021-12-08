# learn-raspberrypi


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

noip2 -S 		#Shows status: *Use sudo to run command in root mode
			# coz first time after creating a configuration it 
			# doesn't without sudo prefixed, yikes!

noip2 			# Runs noip2 service.
noip2 -h 		# Shows help from noip2
noip2 -K 702 		# Delete an existing configuration running task.
sudo noip2 -C 		# Use this command to create a new config after terminating a existing running process.

**IMPORTANT After installating noip2** give read permission to the configuration file to all the users by below command,
and the `.profile` file would be able to run use the configuration without any 
silly error, yikes!!

`sudo chmod +rwx /usr/local/etc/no-ip2.conf`
