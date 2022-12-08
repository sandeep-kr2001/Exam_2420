# Exam_2420

## Part 1

```sudo apt update && sudo apt upgrade```

![update](https://github.com/sandeep-kr2001/Exam_2420/blob/main/Images/update.JPG)


## Part 2 

List of Keybindings used :

``` 
:%s/\<eco\>/echo/g
:%s/\<V\>/C/g
:s/1/0/g
:s/numbs/:digit:/g 
``` 

1. Used :%s/\<eco\>/echo/g to change the occurrence of eco with echo in the whole system
2. Used :%s/\<V\>/C/g to replace the occurrence of V to C in the whole file 
3. Used :s/1/0/g while keeping the pointer in the first line to replace 1 with 0 in the first file.
4. Used :s/numbs/:digit:/g while keeping the pointer in line numbs present to replace it.
![part2Vimbuffer](https://user-images.githubusercontent.com/97915467/206578718-35406bd1-dc7d-4f82-9c25-b4a9b1bf9985.JPG)



## Part 3
- print logs for the current boot

For this I used /boot
![Logs](https://github.com/sandeep-kr2001/Exam_2420/blob/main/Images/part3logs.JPG)
- output in a nice pretty json.

For this I used /pretty to find the output
![pretty](https://github.com/sandeep-kr2001/Exam_2420/blob/main/Images/pretty%20json.JPG)
- logs should have a priority of warning or more important

For this I used /priority
![pretty](https://github.com/sandeep-kr2001/Exam_2420/blob/f7d0d7f191c32f164e1d9b77d0b77ac01f2b5619/Images/priority.jfif)

complete command

```journalctl -b -o json-pretty -p "emerg".."warning”```
![complete command](https://github.com/sandeep-kr2001/Exam_2420/blob/main/Images/commplete%20command.JPG)

## Part 4

 * script for part 4. Saved this in /opt/
``` 

#!/bin/bash

echo "Currently logged in user: $(whoami)" > /etc/motd

for user in $(awk -F: '$3 >= 1000 && $3 <= 5000 {print $1}' /etc/passwd); do
  uid=$(id -u $user)
  shell=$(grep "^$user:" /etc/passwd | cut -d: -f7)
  echo "User: $user, UID: $uid, Shell: $shell" >> /etc/motd
done

```


## Part 5
* saved this service file in /etc/systemd/system
``` 
[Unit]
Description=Used to run the script

[Service]
Type=oneshot
ExecStart=/opt/part4.sh

[Install]
WantedBy=multi-user.target
```

## Part 6 
saved this timer file in /etc/systemd/system
``` 
[Unit]
Description=part 5 Timer

[Timer]
OnBootSec=1min
OnUnitActiveSec=1day

[Install]
WantedBy=timers.target

``` 



