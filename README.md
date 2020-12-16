# python_informations
____________________________________________________________________________________________________________

## Trick 1 : Problem for Y axis order with mathplotlib

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

## Trick 3 : Load a list
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

## Trick 4 : Load list file in directory
code example for loading list of file in a directory
````
import os 

path = 'directory_name_path'
files = os.listdir(path)
for fileName in files:
    print(f)
````

## Trick 5 : Saving a Text File
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

## Trick 7 : Comments in python

In python for comment expression, you can adapt these examples
```
# Comment one line in python

"""
Command a block expression
on multi line
"""
```

## Trick 8 : timestamp in ms for plot with date
```
import matplotlib.pyplot as plt
import matplotlib.dates as md
import matplotlib.ticker as ticker
import numpy as np
import datetime as dt
import time

#timestamp ms conversion
print("Timestamps now (ms)")
timestamp_now=int(round(time.time() * 1000))
print(timestamp_now)

#Extraction timestamp ms to date time
dt_object = datetime.fromtimestamp(timestamp_now/1000)
print("dt_object =", dt_object)
print("type(dt_object) =", type(dt_object))

#Conversion pandas dataframe with Time=Timestamps in ms for marking in plot
dates=[dt.datetime.fromtimestamp(ts/1000) for ts in data_matrix_pandas["Time"]]
print(dates)

#plotting datas
plt.plot(dates[1:],data_matrix_pandas["Data"][1:], 'bo-')
plt.title('Title plot')
plt.xlabel('Label X axis')
plt.ylabel('Label Y axis')
axes.set_ylim([0, 1.5])
plt.show()
```
