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
