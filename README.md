# byte_count
The Main idea to invoke this scripts is, i Like the count the file in byte size NOT for 1 file but for entire File in the HardDisk in Total Byte Size and convert them to readable format like KB,MB,GB
## linux
using linux command i want to extract only the byte size of the file and save only the bytenumber into file,which is used to count the totalbyte size
Using 
ls -laR /mnt/Drive-1

![ls_cmd](https://user-images.githubusercontent.com/30696072/44015254-c295cd40-9eed-11e8-94c4-ea4bed17c716.jpg)

we need only the 5th colume which is the byte size number extract this awk and save to a file

ls -laR /mnt/Drive-1 | awk '{print $5}' > file-1

Note: Now we have extracted the byte size of all the file with empty space and some alphabetical character, So remove the empty space and alpha character and let the file to contain only the numbers (i.e) byte size number by using the following command

sed -i '/^$/d' file-1   #To remove the empty lines

then use grep write a regular expression to get only the number 
cat file-1 | grep -E "^[0-9]+[0-9]$" > final-file

Now this final-file contains all the byte number of the files , 

## python
python script is use to add all of the byte number contain in the final-file, this file is given as input to list

It display in term of Total byte, Kilo byte, Mega byte, Giga byte

![python](https://user-images.githubusercontent.com/30696072/44015857-3002cc82-9ef0-11e8-9fed-a6278c68ccd1.png)

Just an Interest of Doing its




