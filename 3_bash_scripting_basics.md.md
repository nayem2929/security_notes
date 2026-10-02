**Shebang**: First line of any shell script. 
`#!/bin/bash`

**Variables**: 
`name="KrazyFrog"`
`echo $name`

**Parameters**:
`name=$1`
`echo $name`
Running this script with `./script.sh Wimpy` will return `Wimpy`
Parameters can also be inputted pausing the run of the script using `read`.
`echo "Enter your name"`
`read name`
`echo "Your name is $name"`

**Arrays**:
`transport=('car' 'train' 'bike' 'bus')`
`echo "${transport[1]}"`
returns `train`
Arrays can be edited:
`transport[1]='trainride'`
changes the array into: `car trainride bike bus`
Elements can be deleted using `unset`
For example , `unset transport[1]` deletes `trainride` from the array. 

**If-else**:
```shell
# Defining the Interpreter 
#!/bin/bash
echo "Please enter your name first:"
read name
if [ "$name" = "Stewart" ]; then
        echo "Welcome Stewart! Here is the secret: THM_Script"
else
        echo "Sorry! You are not authorized to access the secret."
fi
```
Loops:
```shell
# Defining the Interpreter 
#!/bin/bash
for i in {1..10};
do
echo $i
done
```
