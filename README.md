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
code example for loading list of file in a directory
````
import os 

path = 'directory_name_path'
files = os.listdir(path)
for fileName in files:
    print(f)
````

## Trick 5 :S aving a Text File
Code example for saving TXT file :
````
with open('text_file.txt', 'w') as f:
    f.write('Text1 to write \n')
    f.write('Text1 to write \n')
````

## Trick 6 : Saving Excel file
Code example for saving pandas dataframe on excel file
````
import pandas as pd
	
data1 = ["ligne 1", "ligne 2","ligne 3","ligne 4"]
data2 = [10229,35355,28282,272772,288282]

# Create dataframe in one step
df = pd.DataFrame({"data1":data1,
                  "data2":data2})

# write dataframe to excel file
df.to_excel("data1_data2.xls")

# write dataframe to excel file with no index
df.to_excel("data1_data2.xls", index=False)

# write dataframe to excel file with sheet name
df.to_excel("data1_data2.xls", 
             index=False,
             sheet_name="data")
````
