#DataQuest

Link: https://dataquest.io

###Learning Python
####Introduction:
````python
print("hi./nbye")
type(a) 
```
####Find the US City with the lowest crime rate:

Read text file:
```python
# open text file (2/36)
f = open(_filename_, _mode_)  # _mode_: r = "reading"

# read data (3/36)
d = f.read()  #read the contents
```

List:
```python
# list (5/36)
# list can store diff type of variable
l = []  #define an empty list

# list index (6/36)
# list in python start with 0
l = ["a", "b", "c"]
print(l[0])  #a

# split string (7/36)
t = "1,abc\n2,cde"
t.split("\n")
print(t)  #["1,abc", "2,cde"]
# split csv file
f = open("a.csv","r")
rows = f.read().split("\n")
print(rows)
```

Loops:
```python
# for loop (10/36)
for _element_ in the _list_:
	# _lines in loop_
# lists of lists (13/36)
list = [[1,2,3],[4,5,6],[7,8,9]]
print(list[0][1]) #2
```
Append:
```python
l = ["a","b","c"]
l.append("d")  # ["a","b","c","d"]
```

Read in csv file:
```python
f = open('crime_rates.csv', 'r')
data = f.read()
rows = data.split('\n')
full_data = []
for row in rows:
    split_row = row.split(",")
    full_data.append(split_row)
```
Logical comparison:
```python
 a == b 
 a > b
 a < b
 
```
If statement:
```python
if a == 4:
    print("Success!")
```
int()
```python
# change str to int type
c = '1'
c_int = int(c)  # 1
```
search the list
```python
the_list = [5, 6, 7, 10, 50]

# Loop through the_list
for item in the_list:
    # If the list item equals 5, print out "Found"
    if item == 5:
        print("Found")
```
Find the lowest crime rate:
```python
# Let's load the csv file
f = open('crime_rates.csv', 'r')
data = f.read()
rows = data.split('\n')
full_data = []
for row in rows:
    split_row = row.split(",")
    split_row[1] = int(split_row[1])
    full_data.append(split_row)

city = ""

# lowest crime rate
lowest_crime_rate = 10000
for i in full_data:
    if i[1] < lowest_crime_rate:
        lowest_crime_rate = i[1]
        city = i[0]
        
print(city)
```

####Discover weather patterns in LA
Slicing list
```python
a = [4,5,6,7,8]
# New list containing index 2 and 3.
print(a[2:4])
# New list with no elements.
print(a[2:2])
# New list containing only index 2.
print(a[2:3])
```
Dictionary:
```python
# Assignment
dictionary_one = {}
# add keys and values.
dictionary_one["key_one"] = 2
# or
a = {"key1": 10, "key2": "indubitably", "key3": "dataquest", 3: 5.6}

```
`in` : return `true` if item in list, else `false`
```python
_item_ in _list_

_key_ in _dictionary_
```

Frequency of list
```python
list = [...]
counts = {}
for i in list:
    if i in counts:
        counts[i] = counts[i] + 1
    else:
        counts[i] = 1
```
####Building a spell checker
```python
# Tokenizing is the process of splitting the file into individual words.
tokenized_text = text.split(" ")
```
Replace punctuation
```python
no_punctuation_tokens = []
punctuation = ["?", "!", ",", "'", ";", ".", "\n\n"]
for i in tokenized_story:
    for x in punctuation:
        i = i.replace(x, "")
    no_punctuation_tokens.append(i)
    
print(no_punctuation_tokens)
```

Function (7/18)
```python
# A simple function that takes in a number of miles, and turns it into kilometers
# The input at position 0 will be put into the miles variable.
def miles_to_km(miles):
    # return is a special keyword that indicates that the function will output whatever comes after it.
    return miles/0.62137
```
```python
# read and normalize text
def normalize(token):
    token = token.replace(".","")
    token = token.replace(",","")
    token = token.replace("'", "")
    token = token.replace(";", "")
    token = token.replace("\n", "")
    token = token.lower()
    return token

normalized_dictionary_tokens = []

f = open("dictionary.txt","r")
dictionary = f.read()
dictionary_word = dictionary.split(" ")

for i in dictionary_word:
    x = normalize(i)
    normalized_dictionary_tokens.append(x)
```

####Analyze NFL data
Importing and using modules
```python
import math
a = math.sqrt(16)
b = math.ceil(111.3)
c = math.floor(89.9)
```

```python
import csv
f = open("xxx.csv", "r")
c = csv.reader(f)
d = list(c)
```
boolean keyword
```python
a == 3 and b == 4
a == 3 or b == 4 

```
class
```python
class Team():
    name = "Tampa Bay Buccaneers"
bucs = Team()
```

`__init__`: initialize a class
```python
class Team():
    def __init__(self,name):
        self.name = name
        
bucs = Team("Tampa Bay Buccaneers")
```
method:
```python
class Car():
	def __init__(self, miles_per_gallon):
		self.mpg = miles_per_gallon

	def get_gas_cost(self, miles):
		total_gas = self.mpg * miles
		return total_gas * 3.00
```
####What should you name your kid if you want them to be a US Congressperson?

set
```python
# Converting to a set (get unique element)
unique_genders = set(_list_)
unique_genders_list = []
```
enumerate (x, i=0)
```python
for i, x in enumerate(ships):
    print(ships[i])
    print(cars[i])
```
append a new column
```python
for i, row in enumerate(legislators):
    row.append(birth_years[i])
```
list comprehensions: operation in a list using for loop inside list
```python
# Define a list of lists
data = [["tiger", "lion"], ["duck", "goose"], ["cardinal", "bluebird"]]

# Extract the first column from the list
first_column = [row[0] for row in data]
```
try/ except
```python
try: 
    #  if no error, run code here
except Exception:
    # if error, run code here
    # if no lines to run, use:
    pass
```
None
```python
# Set a variable equal to the None type
a = None

# This is True
print(a is None)

# a is of the None type
print(type(a))
```
`.items()`
```python
animal_types = {"robin": "bird", "pug": "dog", "osprey": "bird"}

# The .items method lets us access a dictionary key and value in a loop.
for key,value in animal_types.items():
    print(key)
    print(value)
    # This is equal to the value
    print(animal_types[key])

```
####Which airline is delayed the most?
`while` loop
```python
x = 3
while x < 6:
    print(x)
    x += 1
```
`break`
```python
for i in list:
	if sth:
		break
```
find column index by name:
```python
def column_number_from_name(column_name):
    column_number = None
    for i, column in enumerate(column_names):
        if column == column_name:
            column_number = i
    return column_number
```
negative indexing:
get values from the end of a list
```python
# the third to last item
third_to_last = flight_delays[-3]
# the last 4 items
end_slice = flight_delays[-4:-1]

first_ten_rows = flight_delays[:10]
last_ten_rows = flight_delays[-10:]

remove_first_2 = list[2:]
```
column sum
```python
arr_del15_column = column_number_from_name("arr_del15")
# get the list of the column
arr_del15 = [float(row[arr_del15_column]) for row in flight_delays]
total_arr_del15 = sum(arr_del15)
```
named argument and optional argument
```python
# b & c are now with default values
# if used named argument in function call, cannot use positional argument at the same time
def multiply(a, b=2, c=1):
    return a * b * c
```
###Data
####Finding out about world alcohol consumption

#####Numpy
Read data `numpy.genfromtxt(_data_, delimiter=_delimiter_)
```python
# No need to use .open() since the function will take care of it
g = "world_alcohol.csv"

# Basic from
world_alcohol = numpy.genfromtxt(g, delimiter=",")

# since numpy will try to convert the data to float type, need to define the data type first

#Using `dtype` argument to set the data type

# `dtype="U75"`
# U = Unicode
# 75 = max length of data

world_alcohol = numpy.genfromtxt(g, delimiter=",", dtype="U75", skip_header=1)

```
Getting Data
```python
# A specific cells
cell = data[0,1]  # the first row, second column data

row = data[1,:]  # get the second row

col = data[:,3]  # 4th column
```

Slicing
```python
vector = [1,2,3,4,5,6,7,8,9,10]
vector_1_5 = vector[1:6]
print(vector_1_5)  # [2, 3, 4, 5, 6]
```

Dimension `.shape`
```python
# the dimension of the vector/ matrix
print(world_alcohol.shape)  #(3257, 5)
```

Boolean elements
```python
# when comparing a vector to a value, it will return an array with the result of each element compare to the value

print(vector_1_5 == 3)  # [False, True, False, False, False]
```

Subset vector
```python
# will get only element if beer == true
world_alcohol[:,3][beer] 
```

Subset matrices
```python
# will print all columns for rows which type equal to "Beer"
beer = world_alcohol[:,3] == "Beer"
print (world_alcohol[beer,:])
```

Subset with multiple conditions
```python
yemen_1987_row = (world_alcohol[:,0] == "1987") & (world_alcohol[:,2] == "Yemen")
yemen_1987 = world_alcohol[yemen_1987_row,:]
```

Convert a column to floats
```python
alcohol_numbers = world_alcohol[:,4].astype(float)
```
Replace values in an array
```python
# replace any item in the alcohol consumption column that contains '0'  with '10'.
world_alcohol[[:,4][world_alcohol[:,4]=='0'] = '10'
```

Convert to floats
```python
bad_value = ''
alcohol_consumption_float_column = None

world_alcohol[:,4][world_alcohol[:,4] == bad_value] = '0'
alcohol_consumption_float_column = world_alcohol[:,4].astype(float)
```

`.sum()` sum of column
```python
total_alcohol = 0
total_alcohol = alcohol_consumption.sum()
```
####Finding the most (and least) nutritious foods
#####pandas
Read csv
```python
# Import pandas
import pandas

# Read in the world_alcohol.csv data from earlier.
world_alcohol = pandas.read_csv("world_alcohol.csv")
```

`.iloc[]`
```python
pandas_dataframe.iloc[0,0]  # first element
pandas_dataframe.iloc[:,0]  # first column
pandas_dataframe.iloc[0,:]  # first row
```
index a series (a.k.a. vector/ array)
```python
# This is a series.
first_row = food_info.iloc[0,:]

# Get the first ten items in the first row.  Note how we index the series.
first_ten_items_in_first_row = first_row[0:10]

# Equivalent to the above two statements, just condensed.
first_ten_items_in_first_row = food_info.iloc[0,:][0:10]
```
Get column by name
```python
print(list(food_info.columns.values))
print(food_info["Protein_(g)"][0:10])
```

Getting multiple columns by name
```python
# This will get just the fiber and sugar columns from the data.
column_list = ['Fiber_TD_(g)', 'Sugar_Tot_(g)']
fiber_and_sugar = food_info[column_list]
```

Math with columns
```python
# same length columns with element wise operation

total_fat = food_info["FA_Sat_(g)"] + food_info["FA_Mono_(g)"] + food_info["FA_Poly_(g)"]

# with scalar
food_info["Iron_(mg)"] / 1000
```
Sort columns `.sort()`
```python
# return a new dataframe sorted accd. to specific criteria
descending_fat = food_info.sort(["Lipid_Tot_(g)"], ascending=[False])
# Print the most fatty food in the data.
print(descending_fat.iloc[0,:])

# We can reverse the sort order.
ascending_fat = food_info.sort(["Lipid_Tot_(g)"], ascending=[True])

# The least fatty food has no fat at all
print(ascending_fat.iloc[0,:])
```

Multicolumn sort
```python
ascending_fat_then_ascending_sodium = food_info.sort(["Lipid_Tot_(g)", "Sodium_(mg)"], ascending=[True, True])
```

Normalized
range normalized
```python
# This will loop through column_list, and normalize each of the columns in it.
for column in column_list:
    food_info[column] = food_info[column] / food_info[column].max()
```

optional argument in `pandas`
```python
row_total = food_info[column_list].sum(axis=1)
column_total = food_info[column_list].sum(axis=0)
```

assign new columns
```python
food_info["double_fat"] = food_info["Lipid_Tot_(g)"] * 2

```

summing
```python

column_list = ["vitamin_totals", "Lipid_Tot_(g)", "Protein_(g)", "Sugar_Tot_(g)", "Fiber_TD_(g)", "Cholestrl_(mg)"]
weight_list = [3, -2, 3, -1, 1, -2]

weight_columns = food_info[column_list] * weight_list
nutritional_rating = weight_columns.sum(axis=1)
```

###Data Visualization
####What are some characteristics of forest fires?
Plotting `matplotlib`
scatter plot
```python
import matplotlib.pyplot as plt

# Let's say that we want to graph weight vs height.
weight = [600,150,200,300,200,100,125,180]

# Height is in inches
height = [60,65,73,70,65,58,66,67]

# Now let's make a plot.
# The first input will be the x-axis, and the second will be the y-axis.
plt.scatter(weight, height)
plt.show()

# Don't forget to clear the figure after showing it!
plt.clf()
```

```python
# line chart
sorted = data.sort(data[x],ascending=[True])
plt.plot(sorted[x], sorted[y])
```

```python
# Make a scatter plot of X and Y fire positions
plt.scatter(forest_fires["X"], forest_fires["Y"])

# Set the x axis label
plt.xlabel('X position in grid')
# Set the y axis label
plt.ylabel('Y position in grid')
# Set the title
plt.title("Grid positions of fires in Montesinho national park")
plt.show()
plt.clf()
```
Global style
```python
import matplotlib.pyplot as plt

# Print all available styles
print(plt.style.available)
# ['fivethirtyeight', 'dark_background', 'ggplot', 'bmh', 'grayscale']
# Use the ggplot style for plotting
plt.style.use('ggplot')

plt.scatter(forest_fires["wind"], forest_fires["area"])
# This plot looks a lot better!
plt.show()
plt.clf()

plt.style.use("fivethirtyeight")
plt.scatter(forest_fires["rain"], forest_fires["area"])
plt.show()
plt.clf()
```
bar plot
```python
import matplotlib.pyplot as plt
import numpy
# The pivot_table method will return a new array containing a summary of the data.
# This pivot table will have the Y position of the fire as the index, and the average area of forest burned per fire as the values.
# It will return a vector, or one dimensional array.
area_by_y = forest_fires.pivot_table(index="Y", values="area", aggfunc=numpy.mean)

import matplotlib.pyplot as plt
plt.style.use("ggplot")

# This gets the index values of the vector, in this case, the sorted y positions
y_index = area_by_y.index
plt.bar(y_index, area_by_y)
plt.show()
plt.clf()
```
