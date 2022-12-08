# Exam_2420

##Part 1

```sudo apt update && sudo apt upgrade```


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

![vimbuffer](https://github.com/sandeep-kr2001/Exam_2420/blob/main/Images/part2Vimbuffer.JPG)

## Part 3
- print logs for the current boot

For this I used /boot

- output in a nice pretty json.

For this I used /pretty to find the output

- logs should have a priority of warning or more important

For this I used /priority
