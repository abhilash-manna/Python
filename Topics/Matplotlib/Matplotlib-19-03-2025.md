##### Day-1 [19-03-2025]


# Matplotlib:

- Numpy	---> Data Analysis Library
- Pandas	---> Data Analysis Library / Visualization library
- Matplotlib/Seaborn/Plotly	---> Data visualization libraries

Need of Data visualiztion:
-------------------------
- Data can be represented either in text form or in graphical form.
- Data visualization is the representation of data in visual format.

Advantages:
----------
1. We can compare very easily.
2. We can identify relationship very easily.
3. We can analyze very easily etc...

Basic introduction to Matplotlib :
---------------------------------
- Most **popular and oldest** data visualization library. **Python's alternative to MatLab**.
- It is **open source and freeware** where as MatLab is not open source and not freeware.
- By using this library we can plot data in graphical form very easily. That graphical form can be **either 2-D or 3-D**.
- It is a comprehensive library for creating **static, animated and interactive visualizations in python**.
- **John Hunter** developed matplotlib on top of Numpy and sidepy libraries.
- It has very large community support. Every data scientist used this library atleast once in his life.
- Advanced libraries like **seaborn, plotly are developed on top of matplotlib**.

Installing Matlotlib:
-------------------
1). With Anaconda distribution, this library will be available automatically

>**conda install matplotlib**

2). go to cmd prompt: 
> **pip install matplotlib**   #TO INSTALL

```py
>>> import matplotlib
>>> matplotlib.__version__ #'3.5.3'

# Note:
# 	pip list
# 	pip freeze
```
Types of plots:
----------------------
1. Line plots
2. Bar charts
3. Pie charts
4. Histogram
5. Scatter plots

Based on input data and requirement, we can choose the corresponding plot.


>[!Note]
>1. **matplotlib** ===> package / library
>2. **pyplot**	===> module name
>3. pyplot module defines several functions to create plots:
>		- plot()
>		- bar()
>		- pir()
>		- hist()
>		- scatter()
>
> We can create plots in 2-approaches:
>1. **Function oriented** approach (For **small data sets**)
>2. **Object oriented** approach (For **large data sets**)

## Line Plots:

- We can mark data points from the input data and we can connect these data points with lines. Such type of plots are called line plots.
- We can use line plots to determine the relationship between two data sets.
- Data set is a collection of values like ndarray, python's list etc....
	- wickets = [1,2,3,4,5,6,7,8,9,10]
	- overs = [1,2,3,4,5.......20]
- The values from each data set will be plotted along an axis (x-axis,y-axis).
```py
>>> import matplotlib.pyplot as plt
>>> help(plt.plot)
	plot(*args, scalex=True, scaley=True, data=None, **kwargs)
    Plot y versus x as lines and/or markers.
```
Creation of line plot by passing 2 nd-arrays
--------------------------------------------
plt.plot(x,y)  
The data points will be considered from x and y values  
x = [10,20,30]  
y = [1,2,3]  
Data points:(10,1),(20,2),(30,3)

Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
x = np.arange(1,11)
y = x**2
plt.plot(x,y) #(1,1),(2,4),(3,9),.........
plt.show()
```
figure,plot,x-axis,y-axis

What is a figure?
-----------------
- Figure is an individual window on the screen, in which matplotlib displays the graph i.e, it is the container for the graphical output.
- plot() is a function is responsible to create this figure object.

How to add title to the line plot:
----------------------------------
```py
plt.title('Square function line plot')
```
How to add xlabel and ylabel to line plot:
-----------------------------------------
```py
plt.xlabel('N value')
plt.ylabel('Square of N')
```
>[!Note]
> - plt.plot(x,y) ==> To draw line plot
> -	plt.title() ==> To provide title to line plot
> -	plt.xlabel() ==> Describes info aboy x-axis data
> -	plt.ylabel() ==> Describes info aboy y-axis data
> -	plt.show() ==> To show the line plot

Line propertirs:
-----------------
A line drawn on the graph has several properties like **color, style, width of the line, transparency** etc... We can customize these based on our requirement.

1.Marker property:
-----------------
- We can use marker property to highlight data points on the line plot.
- We have to use marker keyword argument.
```py
plt.plot(x,y,marker='o') #==> o means circle

# to check the marker 
>>> import matplotlib.pyplot as plt
>>> help(plt.plot)
```
| Marker | Description | Category |
|--------|-------------|----------|
| `.` | point marker | Basic markers |
| `,` | pixel marker | Basic markers |
| `o` | circle | Basic markers |
| `v` | triangle down | Basic markers |
| `^` | triangle up | Basic markers |
| `<` | triangle left | Basic markers |
| `>` | triangle right | Basic markers |
| `s` | square | Basic markers |
| `p` | pentagon | Basic markers |
| `*` | star | Basic markers |
| `+` | plus sign | Basic markers |
| `x` | x marker | Basic markers |
| `D` | diamond | Basic markers |
| `d` | thin diamond | Basic markers |
| `\|` | vertical line | Basic markers |
| `_` | horizontal line | Basic markers |
| `P` | filled plus | Common filled markers |
| `X` | filled x | Common filled markers |
| `H` | hexagon2 | Common filled markers |
| `h` | hexagon1 | Common filled markers |
| `8` | octagon | Common filled markers |
| `1` | tri_down | Triangle markers with a different orientation |
| `2` | tri_up | Triangle markers with a different orientation |
| `3` | tri_left | Triangle markers with a different orientation |
| `4` | tri_right | Triangle markers with a different orientation |
| `0` | tickleft | Tick and caret markers |
| `1` | tickright | Tick and caret markers |
| `2` | tickup | Tick and caret markers |
| `3` | tickdown | Tick and caret markers |
| `4` | caretleft | Tick and caret markers |
| `5` | caretright | Tick and caret markers |
| `6` | caretup | Tick and caret markers |
| `7` | caretdown | Tick and caret markers |
| `8` | caretleft (centered at base) | Tick and caret markers |
| `9` | caretright (centered at base) | Tick and caret markers |
| `10` | caretup (centered at base) | Tick and caret markers |
| `11` | caretdown (centered at base) | Tick and caret markers |


2).Linestyle property:
--------------------------------
- Specifies the line styles ==> solid,dotted, dashed
- We can use by using linestyle keyword argument
```py
plt.plot(x,y,marker='o',linestyle='--')
```

| **Character** | **Description** |
|--------------|------------------|
| '-' | solid line style |
| '--' | dashed line style |
| '-.' | dash-dot line style |
| ':' | dotted line style |

3).color property:
--------------------------
- By using color keyword argument we can provide colors to our plot.
- We can specify our required color for the line plot
- We can use any color even hexa code also.

| **Character** | **Color** |
|---------------|-----------|
| 'b'           | blue     |
| 'g'           | green     |
| 'r'           | red     |
| 'c'           | cyan     |
| 'm'           | magenta     |
| 'y'           | yellow     |
| 'k'           | black     |
| 'w'           | white     |
