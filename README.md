# python_informations

## Trick 1 : problem y axis order

on mathplotlib, if you have bad order value on the y axis, that mean your data is not number but string.

To resolve this, it was necessary to transform your data in number value.

## Trick 2 : force to see hex value in binary file

when you want to print a binary file, some character was translate to ascii format. 

To force the hex value printing, you indicate hex() transformation.
```
fileName = "binary_file"
file_data = open(fileName, 'rb').read() 

#print file with ascii appear
print(file_data)

#OUTPUT : b'\xf0\xba\x14\n\xb2 \x06...... in my file example

#print file with only hex character
print(file_data.hex())

#OUTPUT : f0ba140ab22006...... in my file example
```

## Trick 3 : load list
code example for loading list
````
list_file= {
'1607700667369',
'1607700667589',
'1607700667880'}

bs=b''
for fileName in list_file:
    #print(fileName)
    bs = bs + get_bytes_from_file(fileName)
````

## Trick 4 : load list file in directory
code example for loading list
````
import os 

path = 'directory_name_path'
files = os.listdir(path)
for fileName in files:
    print(f)
````
