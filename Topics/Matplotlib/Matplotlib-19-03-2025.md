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

Line properties:
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


##### Day-2 [20-03-2025]

Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
x = np.arange(1,11)
plt.plot(x,x) #Identity function
plt.plot(x,x**2) #square function
plt.plot(x,x**3) #cubic function
plt.show()
```
default color:
--------------
If we do not specify a color then default color will be selected from the style circle
	blue,orange,green,red.....

Shortcut way to set color, marker and line style:
------------------------------------------------
shortcut notation either **mlc** or **cml**
```py
# c -->color
# l -->linestyle
# m -->marker
plt.plot(x,y,'o-r')
plt.plot(x,y,'ro-')
```
>[!Note]
>- In the shortcut way **we should use short code for color** i.e b,g,y,k,c etc...
>- The values red,yellow not allowed in shortcut way.
>```py
>plt.plot(x,x,'o-r')#valid
>plt.plot(x,x,'o-red')#invalid
>plt.plot(x,x,'o-#1c203d')#invalid
>```
4).alpha property:
---------------
- Denotes **transparency of the color**
- value is between **0.0 to 1.0.**
```py
plt.plot(x,x,'o-r',alpha=1.0)
```
[offical document - matplotlib.lines](https://matplotlib.org/stable/api/lines_api.html)

5).linewidth and marker size:
--------------------------
```py
plt.plot(x,x**3,'o-r',lw=10,ms=15)
plt.plot(x,x**3,'o-r',lw=10,ms=15,mfc='yellow',alpha=1)
```
## Components of line plot:
- figure
- axes/plot
- x-axis and y-axis
- title
- xlabel and ylabel
- xticks and yticks

Sequence of activities of plot function:
----------------------------------------
1. Creation of figure object.
2. Creation of plot/axes object.
3. Draw x and y axis
4. Mark evenly spaced values on x-axis and y-axis(xticks and yticks)
5. Plot the data points
6. connect these data points with line
7. Add title, xlabel, ylabel

How to customize the size of the figure: figure() 
----------------------------------------
- The default size of the figure: **8 inches width and 6 inches height**.
- But we can customize based on our requirement. For this we have to use **figure()** function.
```py
>>> import matplotlib.pyplot as plt
>>> help(plt.figure)
figure(num=None, figsize=None, dpi=None, facecolor=None, edgecolor=None, frameon=True, FigureClass=<class 'matplotlib.figure.Figure'>, clear=False, **kwargs)
```
Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
plt.figure(num=1,figsize=(10,4),facecolor='blue')
x = np.arange(1,6)
plt.plot(x,x,'o-r')
plt.show()

# Ex:
plt.figure(num=1,figsize=(3,3),facecolor='green')
```
How to save line plot to a file : savefig()
--------------------------------
- We can save line plot to a file instead of displaying on the screen.
- We have to use **savefig()** function.
```py
>>> help(plt.savefig)

plt.figure(num=1,figsize=(10,4),facecolor='green')
x = np.arange(1,6)
plt.plot(x,x,'o-r')
plt.savefig('identitylineplot.png')

# Bydefault this figure will be saved in the current working directory.
# But we can provide any location based on our requirement.
plt.savefig('C:\\Users\\mahesh\\Desktop\\identitylineplot.png')
```
Creation of line plot by passing a single ndarray:
--------------------------------------------------
- plt.plot(a,b) ----> **a for x-axis** and **b for y-axis**
- plt.plot(a) ----> **a is y-axis** and **x-axis values will be generated automatically** by matplotlib from 0 to N-1. Where N is size of the datapoints of a [Size of ndarray passed].

Ex:
```py
a = np.array([10,20,30,40,50])
plt.plot(a) #0 to 4 will be considered as x-axis
# a (ndarray) values are considered as y-axis
# Now the data points are:(0,10),(1,20),(2,30),(3,40),(4,50)
```
Ex:
```py
a = np.array([10,20,30,40,50])
plt.plot(a,'o-r')
plt.show()
```
Multiple lines on the same plot
-------------------------------
- We can plot any number of line plots on the same graph.
- This approach is helpful for comparision purpose.

Ex:
```py
x = np.arange(1,11)
i = x
s = x**2
c = x**3
plt.plot(x,i,'o-r')
plt.plot(x,s,'o-b')
plt.plot(x,c,'o-g')
plt.title('One Graph, but multiple plots')
plt.show()

# Shortcut way:
# We can also use single plot() function for all 3-lines
plt.plot(x,i,'o-r',x,s,'o-b',x,c,'o-g')
```
How to customize properties of title of plot :
--------------------------------
```py
>>> help(plt.title)
		title(label, fontdict=None, loc=None, pad=None, *, y=None, **kwargs)
```

Ex:
```py
x = np.arange(1,11)
s = x**2
plt.plot(x,s,'o-r')
plt.title('Square Function Plot',{'color':'b'})
plt.show()

#1.
plt.title('Square Function Plot',color='g')
#2.
plt.title('Square Function Plot',{'color':'r','size':20})
#3.
plt.title('Square Function Plot', {'color':'r','size':20,'backgroundcolor':'yellow','alpha':1})
```
[**Title text Properties**](https://matplotlib.org/stable/users/explain/text/text_props.html)


##### Day-3 [22-03-2025]

- family  [ 'serif' | 'sans-serif' | 'cursive' | 'fantasy' | 'monospace' ]
- style or fontstyle [ 'normal' | 'italic' | 'oblique' ]
- weight or fontweight [ 'normal' | 'bold' | 'heavy' | 'light' | 'ultrabold' | 'ultralight']

Ex:
```py
plt.title('Square Function Plot', {'color':'b','size':20,'backgroundcolor':'yellow','fontstyle':'italic','family':'cursive',
'weight':1000,'rotation':3},loc='right',pad=15,color='r')
```
Customization of xlabel and ylabel:
----------------------------------
```py
>>> help(plt.xlabel)
xlabel(xlabel, fontdict=None, labelpad=None, *, loc=None, **kwargs)
    Set the label for the x-axis.
```
```py
>>> help(plt.ylabel)
xlabel(ylabel, fontdict=None, labelpad=None, *, loc=None, **kwargs)
    Set the label for the y-axis.
```
Ex:
```py
x = np.arange(1,11)
s = x**2
plt.plot(x,s,'o-r')
plt.title('Square Function Plot')
plt.xlabel('Year',{'color':'r','size':20,'backgroundcolor':'yellow','rotation':10,'alpha':1,'fontstyle':'italic','family':'cursive','weight':1000})
plt.ylabel('Data Science Sales',color='r',size=20,backgroundcolor='yellow',rotation=91, alpha=1,fontstyle='italic',family='cursive',weight=1000)
plt.show()
```
>[!Note]
> {'color':'r'} and color='b', In this case of conflict, **keyword args will get more priority**.
> This is because keyword args are provided at last when we calling a function.  
> Generally latest values are to be considered by the PVM.  
> Here keyword args are the latest values, fontdict properties are same for **title, xlabel and ylabel**.  
> These values can be passed as keyword args also. In the case of conflict, **keyword args will get more priority**.

How to add grid lines to the plot:
---------------------------------
```py
>>> help(plt.grid)
grid(visible=None, which='major', axis='both', **kwargs)
    Configure the grid lines.

plt.grid() ===> on ==> grid lines are visible
plt.grid() ===> off ==> grid lines are invisible
plt.grid() ===> on ==> grid lines are visible
plt.grid() ===> off ==> grid lines are invisible
```
>[!Note]
>- when **visible is None** and there are **no kwargs**, this **toggles** the visibility of the lines.
>- **default value for visible is None**.

Case-1: grid lines are visible
----------------------------
```py
a = np.array([10,20,30,40,50])
plt.plot(a,a,'o-r')
plt.grid()
plt.show()
```
Case-2: grid lines are not visible
---------------------------
```py
plt.grid()
plt.grid()
```
Case-3: if keyword args are given then grid lines are visible
------------------------------------------------------
```py
plt.grid()
plt.grid(color='g')
```
Case-4: plt.grid(visible=True) ===> gridlines are visible
-------------------------------------------------------
```py
plt.grid(visible=True)
plt.grid(visible=False)
```
which property of plt.grid():
---------------
- default is major
- There are major grid lines and minor grid lines are present.
- **which property will decides which grid lines are going to be displayed**.
- The allowed values are:  
	 which : {'major', 'minor', 'both'} ==> The default value is **major.**
- Bydefault major grid lines will be displayed

```py
plt.grid(which='both')
plt.show()
```
- It display only major grid lines.
- To show the minor gridlines we have to activate the **minorticks_on**.

```py
>>>help(plt.minorticks_on)
    Displaying minor ticks may reduce performance; you may turn them off
    using minorticks_off() if drawing speed is a problem.
```
Difference between major and minor grid lines:
--------------------------------------------
```py
a = np.array([10,20,30,40,50])
plt.plot(a,a,'o-r',lw=7,markersize=10,mfc='yellow')
plt.grid(color='red',lw=3)
plt.minorticks_on()
plt.grid(which='minor',color='g')
plt.show()
```
axis property of of plt.grid():
---
	Along which axis, grid lines have to display
	 axis : {'both', 'x', 'y'} ==> default value is both

y - axis
```py
plt.grid(axis='y')
plt.show()
```
x - axis
```py
plt.grid(axis='x')
plt.show()
```
Passing other keyword args of plt.grid():
---------------------------
```py
plt.grid(color='g',lw=2,linestyle=':')
```
##### Day-4 [24-03-2025]

## Adding Legend:

- If multiple lines present then it is difficult to identify which line represents which dataset/function.
- To overcome this problem we can add legend

```py
>>>help(plt.legend)
```
Call signatures:
- legend()
- legend(handles, labels)
- legend(labels)

1). legend():
------------
Entries will be added to the legend in the order of plots creation.
```py
a = np.arange(10)
plt.plot(a,a,marker='o',label='identity')
plt.plot(a,a**2,marker='o',label='square')
plt.plot(a,a**3,marker='o',label='cubic')
plt.legend()
plt.show()
```
2). legend(labels):
-------------------
- The argument is list of strings.
- Each string is considered as a label for the plots, in the order they created.
-		plt.legend(['label-1','label-2','label-3'])
- This approach is **best suitable for adding legend for already existing plots**.

```py
a = np.arange(10)
plt.plot(a,a,marker='o')
plt.plot(a,a**2,marker='o')
plt.plot(a,a**3,marker='o')
#plt.legend(['Identity','Square','Cubic'])
plt.legend(['a','a**2','a**3'])
plt.show()
```
>[!Note]
>	This approach is not recommended to use because we should aware the order in which plots were created.

3). legend(handles,labels):
--------------------------
- We can define explicitly lines and labels in the legend() function itself.
- It is recommended approach as we have complete control.
-			plt.legend([line1,lin2],['label-1','label-2'])
Ex:
```py
l = [10]
a = l
print(a)
a, = l #unpack list elements and then assign values to provided variable
print(a)
```
Ex:
```py
a = np.arange(10)
line = plt.plot(a,a,'o-r')
print(f'Type of line:{type(line)}')#list
print(f'Line object: ===>{line}')#2-D Line object
```
Ex:
```py
a = np.arange(10)
line, = plt.plot(a,a,'o-r')
print(line)
```
Ex:
```py
lines = plt.plot(a,a,'o-r',a,a**2,'o-b',a,a**3,'o-g')
print(type(lines))
print(lines)
```
Ex:
```py
a = np.arange(10)
line1, = plt.plot(a,a,'o-r')
line2, = plt.plot(a,a**2,'o-b')
line3, = plt.plot(a,a**3,'o-g')
plt.legend([line1,line2,line3],['identity','square','cubic'])
plt.show()
or
line1,line2,line3 = plt.plot(a,a,'o-r',a,a**2,'o-b',a,a**3,'o-g')
plt.legend([line1,line2,line3],['identity','square','cubic'])
or
lines = plt.plot(a,a,'o-r',a,a**2,'o-b',a,a**3,'o-g')
plt.legend(lines,['identity','square','cubic'])
```
How to adjust legend location:
------------------------------
Based on our requirement we can decide legend location in the plot loc argument.  
loc--->location
```py
plt.legend([line1,line2,line3],['identity','square','cubic'],loc=1)
or
# loc = 'upper right'
# loc = 3
# loc = 10
```
How to specify number of columns in the legend
---------------------------------------------
- Bydefault the number of columns: 1
- But we can customize by using ncol argument.
```py
plt.legend(lines,['identity','square','cubic'],ncol=3)
```

We can do more customization for the legend like

1. We can add title to the legend.
2. We can change look and feel.
3. We can change fontsize and color.
4. We can place legend outside of the plot etc. .

Adding title to legend:
```py
	plt.legend(lines,['identity','square','cubic'],title='3 common function')
```
How to add legend outside of the plot:
---
- For this we have to use loc keyword argument.
>		loc = (x,y)
```py
plt.legend(lines,['identity','square','cubic'],loc=(0,1.1))#(0,0),(1,0),(1,1)
plt.tight_layout()#to fix the legend at fixed position
```
Customization of tick location and labels:
------------------------------------------
```py
a = np.arange(11)
b = a*100
plt.plot(a,b,'o-r')
plt.grid()
plt.title('Sales Report')
plt.xlabel('Year')
plt.ylabel('Number of sales')
plt.show()
```
- Ticks are the markers to represent specific value on the axis.
- Ticks are very helpful to locate data points on the plot very easily.
- Based on our input, matplotlib decides tick value automatically.
- Based on our requirement, we can customize tick location and labels.
- For this we have to use:

 		xticks()
 		yticks()

Ex:
```py
plt.xticks(ticks=[0,1,2,3,4,5,6,7,8,9,10],labels=['2000','2001','2002','2003','2004',
'2005','2006','2007','2008','2009','2010'],color='blue',size=15,rotation=30,
family='fantasy')
plt.yticks([0,100,200,300,400,500,600,700,800,900,1000])
```
>[!Note]
> If we pass empty list to xticks() or yticks() then corresponding ticks will be disabled on the plot.
>
> plt.xticks([]) ==>xticks will be disabled  
> plt.yticks([]) ==>yticks will be disabled

##### Day-5 [25-03-2025]

## How to set limit range of values on x-axis and y-axis

- xlim()
- ylim()

```py
# For x-axis: left and right.
help(plt.xlim)

# For y-axis: bottom and top.
help(plt.ylim)
```
- If we are **not passing any argument** to xlim() function then it **acts as getter** method.
- If we are **passing any argument** then it acts **as setter** method.

To get left and right limits on x-axis and Bottom and Top limit on y-axis:
Ex:
```py
a = np.arange(1,101)
b = a**2
plt.plot(a,b,'o-r')
plt.grid()
left,right = plt.xlim()
bottom,top = plt.ylim()
print('Left limit:',left)
print('Right limit:',right)
print('Bottom limit:',bottom)
print('Top limit:',top)
plt.show()
```
To set left and right limits on x-axis:
```py
plt.xlim(left,right)
plt.xlim((left,right))
plt.xlim(right=3) #left will be generated by matplotlib
plt.xlim(left=3) #right will be generated by matplotlib
plt.xlim(3) #3 is for left and default for right.

#left is 1 and right is 50
plt.xlim(1,50)

plt.xlim(left=1)#left 1 and for right default value
plt.xlim(right=50)#left is default and for right 50
plt.xlim(1) #1 is for left and default for right.
```
To set top and bottom limits on y-axis:
```py
plt.ylim(bottom=100)
plt.ylim(1,1000)
plt.ylim(top=1000)
```
Scaling: How to set scale for x-axis and y-axis
-----------------------------------------------
The difference between any two consecutive points on any axis is called as scaling.

1. Linear scaling
2. Logarithmic scaling

1.Linear scaling:
-----------------
- The difference between any to consecutive points on the given axis **is always fixed**, such type of scaling is called as linear scaling.
- Default scaling in matplotlib is **linear scaling**.
- If the data set values are represented over small range, then linear scaling is the best choice.

2.Logarithmic scaling:
---------------------
- The difference between any two consecutive points on the given axis **is not fixed** and it is multiples of 10, such type of scaling is called as logarithmic scaling.
- If the data set values are spreaded over big range, then logarithmic scaling is the best choice.

```py
>>> help(plt.xscale)
```
linear scaling
```py
a = np.arange(10000)
b = np.arange(10000)
plt.plot(a,b)
plt.grid()
plt.xscale('linear')
plt.show()
```
logarithmic scaling
```py
plt.xscale('log')
```
Ex:
```py
plt.xscale('linear')
plt.yscale('log')
```
Ex:
```py
plt.xscale('log')
plt.yscale('log')
```
How to customize base value in logarithmic scaling

- Bydefault **'10'** is the base parameter value.
- We have to use keyword argument **'base'**.
```py
plt.xscale('log',base=3)
plt.yscale('log',base=9)
```
symlog
```py
plt.xscale('symlog')
```
Plotting styles:
----------------
- We can customize look and feel of the plot by using style library.
- To know the plotting styles available in matplotlib
```py
>>> print(plt.style.available)
# Output
# 1. ggplot:To emulate the most powerful ggplot style of R-Language
# 2. seaborn:To emulate seaborn style
# 3. fivethirtyeight:The most commonly used style in real time
```
ggplot style
```py
a = np.arange(10000)
b = np.arange(10000)
plt.style.use('ggplot')/plt.style.use('seaborn')/plt.style.use('fivethirtyeight')
plt.plot(a,b)
plt.show()
```
## Comparison: Functional/Procedural Oriented vs Object Oriented Approach of Plotting:

Function oriented approach:
```py
def f1():
	print('f1 function')
def f2():
	print('f2 function')
f1()
f2()
```
Object Oriented Approach:
```py
class Test:
	def m1(self):
		print('m1 method')
	def m2(self):
		print('m2 method')
t = Test()
t.m1()
t.m2()
```
1.Functional approach:
---------------------
- We can create plots with the help of multiple functions from pyplot module.
```py
a = np.arange(1,11)
b = a**2
plt.plot(a,b)
plt.xlabel('N')
plt.ylabel('Square value of N')
plt.title('Square Function')
plt.show()

# The functions of matplotlib.pyplot module:
#	plot(),xlabel(),ylabel(),title(),show()
```
2.Object Oriented Approach:
-------------------------------------------
- In object oriented approach, we have to create objects and on those objects we have to call corresponding methods to create a plot.
	- Step-1: Creation of Figure object
	- Step-2: Creation of Axes object
	- Step-3: Plot the graph
	- Step-4: Set the properties of the axes

##### Day-6 [26-03-2025]

Step-1: Creation of Figure object
---------------------------
```py
fig = plt.figure()
plt.show()
```
Step-2: Creation of Axes object:
------------------------------
- Once figure object is ready, then we have to add axes to that object.
- For this we have to use add_axes() method of Figure class.
- This method returns Axes object.

```py
>>> help(plt.Figure.add_axes)

# Parameters
#    rect : sequence of float
#        The dimensions [left, bottom, width, height] of the new Axes. All
#        quantities are in fractions of figure width and height.

# LBWH

fig = plt.figure()
axes = fig.add_axes([0.2,0.3,0.6,0.4])
plt.show()
```
Step-3:Plot the graph:
--------------------
- Once Axes object is ready, then we can use the plot method.
```py
axes.plot(a,b)
```
Step-4:Set the properties of the axes
--------------------------------
```py
axes.set_xlabel('xlabel')
axes.set_ylabel('ylabel')
axes.set_title('title')
```
Ex:
```py
a = np.arange(1,11)
b = a**2
fig = plt.figure()
axes = fig.add_axes([0.2,0.3,0.6,0.4])#[left,bottom,width,height]lbwh
axes.plot(a,b)
axes.set_xlabel('N')
axes.set_ylabel('Square of N')
axes.set_title('Square Function')
axes.grid()
plt.show()

# Note:
# We can use single set() method to set all axes properties like title,xlabel,ylabel,xlim,ylim etc....

axes.set(xlabel='N',
ylabel='Square of N',
title='Square Function',
xlim=(1,5),
ylim=(1,25))
```

## Bar Chart/ Bar Graph/ Bar Plot:
- In a line plot, the data points will be marked and these markers will be connected by line.
- But in bar charts, data will be represented in the form of bars.

4-types of bar charts:
1. Simple bar charts / vertical bar charts
2. Horizontal bar charts
3. Stacked bar charts
4. Clustered bar charts / Grouped bar charts

Simple bar charts/Vertical bar charts:
-----------------------------------
- The data will be represented in the form of vertical bars.
- Each vertical bar represents an individual category.
- The height/length of the bar is **based on value** it represents.
- Most of the times the width of the bar is **fixed**, but we can customize.
- The default width: **0.8**
- By using **bar()** function we can create bar chart.

```py
>>> help(plt.bar)
bar(x, height, width=0.8, bottom=None, *, align='center', data=None, **kwargs)
    Make a bar plot.
```
Ex:
```py
import matplotlib.pyplot as plt
heroes = ['Chiranjeevi','Nag','Venkatesh','Balaiah','Pawan Kalyan']
movies = [1000,300,600,350,750]
c = ['r','b','k','g','orange']
w = [0.8,0.6,0.7,0.9,0.5]
plt.bar(heroes,movies,color=c,width=w)
plt.xlabel('Hero Name',color='b',fontsize=15)
plt.ylabel('Number of movies',color='b',fontsize=15)
plt.title('Hero wise number of movies',color='r',fontsize=15)
plt.show()
```
Ex:Mobile sales of Nokia from 2011 to 2020
```py
import matplotlib.pyplot as plt
years = [2011,2012,2013,2014,2015,2016,2017,2018,2019,2020]
sales = [10000,25000,45000,30000,10000,5000,70000,60000,65000,50000]
c = ['r','k','y','g','orange','m','c','b','lime','violet']
plt.bar(years,sales,color=c)
plt.xlabel('Year',color='b',fontsize=15)
plt.ylabel('Number of sales',color='b',fontsize=15)
plt.title('Nokia Mobile Sales in the last Decade',color='r',fontsize=15)
plt.xticks(years,rotation=30)
plt.tight_layout()
plt.grid(axis='y')
plt.show()
```
How to add labels to the bar:
-----------------------------
We can add labels to any plot by using 2-functions:
1. pyplot.text()
2. pyplot.annotate()
```py
>>>help(plt.text)
text(x, y, s, fontdict=None, **kwargs)
    Add text to the Axes.
    Add the text *s* to the Axes at location *x*, *y* in data coordinates.
```
Adding labels for the data points of lineplots:
-----------------------------------------
```py
import matplotlib.pyplot as plt
import numpy as np
a = np.arange(10)
plt.plot(a,a,'r-o')
#plt.text(2,2,'(2,2)',color='b',size=15)
for i in range(a.size):#0 to 9
	plt.text(a[i]+0.4,a[i]-0.2,f'{a[i],a[i]}',color='b')
plt.show()
```

##### Day-7 [27-03-2025]

pyplot.annotate():
--------------------------
```py
>>> help(plt.annotate)
annotate(text, xy, *args, **kwargs)
```
- Annotate the point **xy** with text **text**.
- In the simplest form, the text is placed at **xy**.

Ex:
```py
a = np.arange(10)
plt.plot(a,a,'o-r')
for i in range(a.size):#0 to 9
	plt.annotate(f'{a[i]},{a[i]}',(a[i]+0.4,a[i]-0.2),color='g')
plt.show()
```
How to add label to the barchart:
-------------------------------
```py
import matplotlib.pyplot as plt
years = [2011,2012,2013,2014,2015,2016,2017,2018,2019,2020]
sales = [10000,25000,45000,30000,10000,5000,70000,60000,65000,50000]
c = ['r','k','y','g','orange','m','c','b','lime','violet']
plt.bar(years,sales,color=c)
plt.xlabel('Year',color='b',fontsize=15)
plt.ylabel('Number of sales',color='b',fontsize=15)
plt.title('Nokia Mobile Sales in the last Decade',color='r',fontsize=15)
plt.xticks(years,rotation=30)
plt.tight_layout()
for i in range(len(years)):#0 to 9
	plt.text(years[i],sales[i]+500,str(sales[i]//1000)+'k',ha='center',color='b')
plt.show()

# Ex:
for i in range(len(years)):#0 to 9
	plt.annotate(str(sales[i]//1000)+'k',(years[i],sales[i]+500),
	ha='center',color='g',backgroundcolor='yellow')
```
Plotting bar chart with data from csv file:
---------------------------------------
- Assume that data is available in student.csv file
- which is present in current working directory, file name 'student.csv'.

|Name of student  | Marks|
|:-----------------|:-------|
|sunny			|	100   |
|bunny			|	200   |

```py
import matplotlib.pyplot as plt
import numpy as np
import csv
names = np.array([],dtype='str')
marks = np.array([],dtype='int')
f = open('student.csv','r')
r = csv.reader(f)#Returns csv reader object
h = next(r)#To read header and ignore
for row in r:
	names = np.append(names,row[0])
	marks = np.append(marks,int(row[1]))
c = ['#ED0A3F','#FFF700', '#FF00CC','#A83731','#0081AB',
		'#8D4E85','#B2F302','#00755E','#E77200']
plt.bar(names,marks,color=c)
plt.show()
```

Note:
If the labels are too long or too many values to represent then we should go for horizontal bar chart instead of vertical bar chart.

Horizontal bar chart:
-------------------
- We will use **barh()** function.
- Here the data will be represented in the form of horizontal bars.
- Each bar represents an individual category.
- The categories will be plotted on y-axis and data values will be plotted on x-axis.
- **width/length of the bar is propotional to the value it represents**.
- The default hight is **0.8**, but we can customize this value

|Vertical | Horizontal|
|:--------|:----------|
|width    | height    |
|bottom   | left      |
|bar()    | barh()    |

Ex:
```py
plt.barh(names,marks,color=c)
plt.xlabel('Marks',fontsize=15,color='b')
plt.ylabel('Name of the student',fontsize=15,color='b')
plt.title('Student Marks Report',fontsize=15,color='r')
plt.tight_layout()
plt.show()
```
Stacked Bar Chart:
----------------
- If each category contains multiple subcatagories then we should go for stacked bar charts.
- Here each sub catagory will be plotted on top of other sub cathagory

Ex-1:
Country wise total population we have to represent. But in that population we have to plot separately men and women

- vertical bar chart ===> bar()
- horizontal bar chart ===> barh()
- **stacked** bar chart ===> bar() or barh()

The stacked bar chart can be **either vertical or horizontal**.

## stacked vertical bar chart

Ex-1:
```py
import matplotlib.pyplot as plt
names = ['Sunny','Bunny','Vinny','Chinny','Pinny']
english_marks = [90,80,85,25,50]
maths_marks = [25,23,45,32,50]
plt.bar(names,english_marks,color='r')
plt.bar(names,maths_marks,color='g')
plt.show()

# Note:
# In the above program overlapping will happens because both bars are started from 0.
# To solve this issue we will use bttom property from which position the second bar should start.

#By using bottom property
plt.bar(names,english_marks,color='r')
plt.bar(names,maths_marks,bottom=english_marks,color='g')
plt.show()
```
with text labels on the bar
```py
import matplotlib.pyplot as plt
import numpy as np
names = ['Sunny','Bunny','Vinny','Chinny','Pinny']
english_marks = np.array([90,80,85,25,50])
maths_marks = np.array([25,23,45,32,50])
total_marks = english_marks + maths_marks
plt.bar(names,english_marks,color='#09695c',label='English')
plt.bar(names,maths_marks,bottom=english_marks,color='#9c0c8b',label='Maths')
for i in range(len(names)):
	plt.text(names[i],english_marks[i]/2,str(english_marks[i]),
	ha='center',color='white',weight=1000)
	plt.text(names[i],(english_marks[i]+maths_marks[i]/2),str(maths_marks[i]),
	ha='center',color='white',weight=1000)
	plt.text(names[i],(total_marks[i]+2),str(total_marks[i]),
	ha='center',color='#008080',weight=1000)
plt.tight_layout()
plt.show()
```
##### Day-8 [28-03-2025]

Ex:  
Country wise medals but sub categories
```py
import matplotlib.pyplot as plt
import numpy as np
country_names = ['India','China','US','UK']
gold_medals = np.array([60,40,50,20])
silver_medals = np.array([50,30,25,43])
bronze_medals = np.array([55,24,45,6])
#
plt.bar(country_names,gold_medals,color='#FFD700',label='gold')
plt.bar(country_names,silver_medals,bottom=gold_medals,
#
color='#C0C0C0',label='silver')
plt.bar(country_names,bronze_medals,bottom=gold_medals+silver_medals,
color='#CD7F32',label='bronze')
plt.xlabel('Country Name',color='b',fontsize=15)
plt.ylabel('Number of Medals',color='b',fontsize=15)
plt.title('Counter Wise Medal Report',color='r',fontsize=15)
plt.legend()
plt.show()
```
## stacked horizontal bar chart

Ex:  
Country wise medals but sub categories
```py
import matplotlib.pyplot as plt
import numpy as np
country_names = ['India','China','US','UK']
gold_medals = np.array([60,40,50,20])
silver_medals = np.array([50,30,25,43])
bronze_medals = np.array([55,24,45,6])
#
plt.barh(country_names,gold_medals,color='#FFD700',label='gold')
plt.barh(country_names,silver_medals,left=gold_medals,
#
color='#C0C0C0',label='silver')
plt.barh(country_names,bronze_medals,left=gold_medals+silver_medals,color='#CD7F32',label='bronze')
plt.ylabel('Country Name',color='b',fontsize=15)
plt.xlabel('Number of Medals',color='b',fontsize=15)
plt.title('Counter Wise Medal Report',color='r',fontsize=15)
plt.legend()
plt.show()
```
>[!Note]
> - To change the vertical bar to horizontal bar
> - bar() ---> barh()
> - bottom ---> left
> - xlabels and ylabels are interchanged.

## Clustered Bar Chart/ Grouped Bar Chart/ Multiple Bar chart:

- If each category contains multiple sub categories and if we want to represent all these sub categories side by side then we should go for clustered bar chart.
- We can create **clustered bar chart by using either bar() or barh()** function.

Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
names = ['Sunny','Bunny','Vinny','Chinny','Pinny']
english_marks = np.array([90,80,85,25,50])
maths_marks = np.array([25,23,45,32,25])
xpos = np.arange(len(names))#[0,1,2,3,4]
w = 0.3
plt.bar(xpos,english_marks,color='r',width=w)
plt.bar(xpos+w,maths_marks,color='g',width=w)
plt.xticks(xpos+w/2,names)
plt.legend(['eng','math'])
plt.show()
```

Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
country_name = ['India','China','US','UK']
gold_medals = np.array([60,40,50,20])
silver_medals = np.array([50,30,25,43])
bronze_medals = np.array([55,24,45,6])
xpos = np.arange(len(country_name)) #[0,1,2,3]
w = 0.2
plt.bar(xpos,gold_medals,color='#FFD700',width=w)
plt.bar(xpos+w,silver_medals,color='#C0C0C0',width=w)
plt.bar(xpos+2*w,bronze_medals,color='#CD7F32',width=w)
plt.xticks(xpos+w,country_name)
plt.ylabel('Country Name',color='b',fontsize=15)
plt.xlabel('Number of Medals',color='b',fontsize=15)
plt.title('Country Wise Medals Report',color='r',fontsize=15)
plt.legend(['gold','silver','bronze'])
for i in range(len(country_name)):
	plt.text(xpos[i],gold_medals[i]+1,gold_medals[i],
	ha='center',color='r',weight=1000)
	plt.text(xpos[i]+w,silver_medals[i]+1,silver_medals[i],
	ha='center',color='r',weight=1000)
	plt.text(xpos[i]+2*w,bronze_medals[i]+1,bronze_medals[i],
	ha='center',color='r',weight=1000)
plt.show()
```
EX:  
India and Australia 20-20 over wise scores required to represent by using clustered bar chart.
```py
import matplotlib.pyplot as plt
import numpy as np
overs = np.arange(1,21)
xpos=np.arange(overs.size)
ind_score = [10,12,8,9,10,22,13,17,3,23,11,10,9,8,23,30,10,9,8,7]
aus_score = [6,8,9,15,23,8,9,6,10,17,13,2,21,15,19,17,4,12,14,10]
w=0.3
plt.figure(num=1,figsize=(16,4),facecolor='g')
plt.bar(xpos,ind_score,width=w)
plt.bar(xpos+w,aus_score,width=w)
plt.xticks(xpos+(w/2),labels=overs)
plt.xlabel('Overs',color='b')
plt.ylabel('Number of Runs',color='b')
plt.title('Overwise Scores Summary')
plt.legend(['IND','AUS'],ncol=2)
plt.grid(axis='y')
plt.show()
```
### horizontal clustered bar chart:
```py
import matplotlib.pyplot as plt
import numpy as np
plt.figure(num=1,figsize=(12,10),facecolor='yellow')
names = ['Bunny','Chinny','Vinny','Pinny']
ypos = np.arange(len(names)) #[0,1,2,3]
h=0.1
english=np.array([45,67,82,95])
telugu=np.array([70,80,54,76])
maths=np.array([65,45,99,78])
science=np.array([88,37,56,87])
social=np.array([78,90,37,42])
hindi=np.array([78,88,65,56])
plt.barh(ypos,english,height=h)
plt.barh(ypos+h,telugu,height=h)
plt.barh(ypos+2*h,maths,height=h)
plt.barh(ypos+3*h,science,height=h)
plt.barh(ypos+4*h,social,height=h)
plt.barh(ypos+5*h,hindi,height=h)
plt.yticks(ypos+2.5*h,names)
plt.xlabel('Marks',color='b')
plt.ylabel('Names',color='b')
plt.title('Students Marks Report',color='b')
plt.legend(['Eng','Tel','Mat','Sci','Soc','Hin'])
plt.show()
```
>[!Note]
> 1. If we want to compare different catagories of values then we should go for bar chart.  
> i.e vertical bar chart and we can create by using bar() function.
>
> 2. If we want to compare different catagories of values and the labels are too long or multiple values to represent then we should go for horizontal bar chart.  
We can create by using barh() function.
>
>3. If we want to compare different catagories of values and each catagory contains multiple sub categories and if we want to represent values on top of the other then we should go for stacked bar chart. It can be either vertical or horizontal.
>
> 4. If we want to compare different categories of values and each category contains multiple sub categories and if we want to represent values side by side then we should go for clustered bar charts.

## Pie Chart:

- Pie chart is a circular chart devided into segments. These segments are called as **wedges**.
- Each wedge represents an individual category. The **area of the wedge is propotional to value of that category**.
- Pie chart is very helpful for comparision of categories.
- The number of categories are less **mostly <=5**.

Ex:
- 20 overs, overwise socres --> bar chart but not pie chart
- The chance of winning match --> pie chart
```py
>>> help(plt.pie)
pie(x, explode=None, labels=None, colors=None, autopct=None, pctdistance=0.6, shadow=False, labeldistance=1.1, startangle=0, radius=1, counterclock=True, wedgeprops=None, textprops=None, center=(0, 0), frame=False, rotatelabels=False, *, normalize=True, data=None)
    Plot a pie chart.
```
Ex:
```py
import matplotlib.pyplot as plt
import numpy as np
marks = np.array([25,30,43,12])
plt.pie(marks)
plt.show()
```
1. Adding labels:
```py
mylabels = ['Python','Java','Devopps','DataScience']
plt.pie(marks,labels=mylabels)
```
2. autopct (auto percentage):  
- To label wedges with their numeric percentage(%) , We can specify its value by using formatted string
```py
plt.pie(marks,labels=mylabels,autopct='%.2f')
```
To add % symbol also
```py
plt.pie(marks,labels=mylabels,autopct='%.2f%%')
```
3. explode:
- If we want to **explode/highlight** a particular category then we should use explode argument.
```py
myexplode = [0.0,0.0,0.0,0.2]
plt.pie(marks,labels=mylabels,autopct='%.2f%%',explode=myexplode)
```
4. shadow:

>		shadow = True

5. colors:

```py
mycolors = ['g','b','r','yellow']
plt.pie(marks,
	labels=mylabels,
	autopct='%.2f%%',
	explode=myexplode,
	shadow=True,
	colors=mycolors)
```

##### Day-9 [1-04-2025]

VIBGYOR colors
---
```py
import matplotlib.pyplot as plt
import numpy as np
marks = np.array([1,1,1,1,1,1,1])
my_labels = ['Violet','Indigo','Blue','Green','Yellow','Orange','Red']
my_colors = ['violet','indigo','blue','green','yellow','orange','red']
plt.pie(marks,
	labels=my_labels,
	colors=my_colors,
	autopct='%.2f%%',
	shadow=True,
	counterclock=False)
plt.show()

# Note:
#	If the number of colors is less than the number of wedges, then the colors will be re-used.
```
startangle:
----
- startangle represents from where first wedge has to start.
- Bydefault it starts from zero from x-axis and move in counter clock wise direction.
```py
marks = np.array([1,1,1,1])
myexplode = [0.0,0.0,0.0,0.2]
my_labels = ['Python','Java','Devops','DS']
my_colors = ['g','b','r','yellow']
plt.pie(marks,
	labels=my_labels,
	colors=my_colors,
	autopct='%.2f%%',
	shadow=True,
	explode=myexplode,
	startangle=90)
plt.show()
```
counterclock:
----
- Bydefault the wedges will be considered in counter clockwise direction.
- If we want clock wise direction we have to use counterclock argument.
- The default value is True.
```py
counterclock = False
```
Adding legend:
-----
```py
plt.legend(title='The 4 Subjects Marks')
plt.tight_layout()
```
wedgeprops:
-----
- The wedges of pie chart can be customized using wedgeprops parameter.
- It is a dictionary of key-value pairs.
- The key can be edgecolor,linestyle,linewidth etc...
```py
wedgeprops={'edgecolor':'k','linestyle':'--','linewidth':3}
```
## Histogram

- Frequency Distribution ===> It is nothing but number of observations in the given interval.
- To represents such type of frequence distributions, we should go for histograms.

Ex-1:

- 300 students (marks: 0 to 100)
	- 23 students got marks in the range:0 to 34
	- 120 students got marks in the range:35 to 49
	- 47 students got marks in the range:50 to 59
	- 80 students got marks in the range:60 to 79
	- 30 students got marks in the range:80 to 100
We distributed 300 values in 5 intervals

Ex-2:
- We are conducting an experiment, where we are trying to roll 3 dicesone 1 lakh time.
	- Every time the sum of outcome of 3 dices will be appended to the list.
	- To analyze these 1 lakh values from the list, it is very difficult.
	- If we convert this into visualization form then it is very easy.

	- For every dice throw, the minimum value :1 and maximum value:6
	- The minimum outcome is 3 and maximum outcode is: 18
	- Total possible outcomes: 3 to 18 means 16 possible outcomes are there.

	- total outcome:15,18,12,16,14,13,4,7,6,12.........
	- 1 lakh values should be distributed into 16 intervals
	- most likely possible values are lies 9 to 12

Ex:
```py
import numpy as np
import time
while True:
	d1 = np.random.randint(1,7)
	d2 = np.random.randint(1,7)
	d3 = np.random.randint(1,7)
	print(f'{d1} + {d2} + {d3} = {d1+d2+d3}')
	time.sleep(3)
```
- Histograms are very helpful to analyze large data sets.
- To plot histograms, we have to divide total input values into equal sized groups or bins.
- A bar is drawn for each bin. The height of each bar is proportional to the number of values related to that bar(bin or interval)
- By using **hist()** function, we can create histograms.
```py
>>> help(plt.hist)
hist(x, bins=None, range=None, density=False, weights=None, cumulative=False, bottom=None, histtype='bar', align='mid', orientation='vertical', rwidth=None, log=False, color=None, label=None, stacked=False, *, data=None, **kwargs)
    Plot a histogram.
```
Ex-1: To create histogram with 10000 samples from uniform distribution in the interval [0,1)

```py
import matplotlib.pyplot as plt
import numpy as np
x = np.random.rand(10000)
xticks_l = [0.1,0.2,0.3,0.4,0.5,0.6,0.7,0.8,0.9,1.0]
plt.hist(x,bins=10,ec='yellow')
plt.xticks(xticks_l)
plt.show()
```
Ex-2: Rolling 3-dice experiment
```py
import matplotlib.pyplot as plt
import numpy as np
l = [ ]
x = np.arange(1,19)#[1,2,3,.....18]
for i in range(100000):
	d1 = np.random.randint(1,7)
	d2 = np.random.randint(1,7)
	d3 = np.random.randint(1,7)
	l.append(d1+d2+d3)
plt.hist(l,bins=x,ec='yellow')
plt.xticks(x)
plt.grid(axis='y')
plt.show()
```
How to change color of bars in histogram:
------------------------------------
```py
# We can specify our own customized color for the bars by using color argument
			plt.hist(l,bins=x,color='r',ec='y')
```
How to change colors of each bars in histograms:
--------------------------------------
- The hist() function returns the **tuple** of the following 3 values

```py
x = plt.hist(l,bins=x,color='r',ec='y')
print(type(x))
print(len(x))
print(x)
```
