# Line Charts with Matplotlib
In this tutorial, we would like to create line charts using Python's Matplotlib



### Prepare the matplotlib library.

This tutorial is using Python version 3.8, as a very stable version. With a ready python on your computer, check the following commands:

> python3 --version

> pip3 --version

> pip3 install matplotlib


Create a .py file, import the library, and you can also check the version of the matplotlib library as follows:
```
import matplotlib                # first step is to import the library
print(matplotlib.__version__)    # let's first check the version used
```

The pyplot is a submodule we will use where most of the Matplotlib utilities exist

```
import matplotlib.pyplot as plt  # let's import such submodule with an alias of plt
```



### Part 1: Let's create a simple line chart

As a simple start, let's draw a line from the start point (10,100) to the end point (20,250).

plot() is a function used first to mark points and draw lines (by default) between them. plot() accepts some inputs:
+ The first input is an array containing the points of the x-axis.
+ The second input is an array containing the points of the y-axis.

```
import matplotlib.pyplot as plt  

horizontal = [10,20]                   # the horizontal axis starts at 10 and ends at 20
vertical   = [100,250]                 # the vertical axis starts at 100 and ends at 250

plt.plot(horizontal, vertical)         # let's design the graph

plt.show()                             # let's display the graph
```




### Part2: let's draw a graph between a set of 4 sequential points:


```
import matplotlib.pyplot as plt

horizontal = [1, 2, 5, 7]
vertical = [3, 7, 2, 8]
  
plt.plot(horizontal, vertical) 
plt.show()                  
```



### Part3: let's add some information (e.g., titles, labels) to the chart

```
import matplotlib.pyplot as plt  

horizontal = [1, 2, 5, 7]
vertical = [3, 7, 2, 8]

plt.plot(horizontal, vertical)   

font1 = {'family':'ariel','color':'blue','size':12}             # let's define one formate
font2 = {'family':'serif','color':'red','size':10}              # let's define another formate

plt.title("Simple Plot", fontdict = font1, loc = 'center')      # let's include a title
plt.ylabel("y-axis", fontdict = font2)                          # let's include a label on the vertical axis
plt.xlabel("x-axis", fontdict = font2)                          # let's include a label on the horizonatal axis
plt.show()                                                      
```


### Part4: passing more inputs to the plot()

The plot() function we have used so far accepts two inputs: The first input is an array containing the points of the x-axis, and the second input is an array containing the points of the y-axis.


However, the plot() function also accepts more formate and style-related inputs:

* You can change the style of the line using linestyle (ls), color, and linewidth (lw) parameters:
```
plt.plot(horizontal, vertical, ls = ':', color = 'r', lw = '8.5')  
```
where ':' is for dotted line, '-' for solid, '--' for dashed
where 'r' is for red color, 'g' for green, 'b' for blue


* You can display the points without the lines:
```
plt.plot(horizontal, vertical, '*')  
```

* You can also display the points on the lines and define the size of them with markersize (ms) parameter:
```
plt.plot(horizontal, vertical, marker = '*', ms = 20)  
```

* You can also display the points on the lines, define the size, and set the color of the markers with markerfacecolor (mfc) parameter:
```        
plt.plot(horizontal, vertical, marker = '*', ms = 20, mfc = 'r')              
```
where 'r' is for red color, 'g' for green, 'b' for blue

   
* You can also change the format/shape of the line, the color, and the point marker using the shortcut string notation parameter. This parameter is called fmt and is written with this syntax: marker|line|color
```
plt.plot(horizontal, vertical, '*:r') 
```


Let's use some of these inputs in an example:

```
import matplotlib.pyplot as plt

horizontal = [1, 2, 5, 7]
vertical = [3, 7, 2, 8]

plt.plot(horizontal, vertical, ls = ':', color = 'r', lw = '8.5', marker = '*', ms = 20)  
plt.title("Simple Plot")    
plt.ylabel("y-axis")        
plt.xlabel("x-axis")        
plt.show()    
```


### Part5: drawing more than one line

You can use the plot() function multiple times to draw many lines on the same diagram

```
import matplotlib.pyplot as plt

horizontal1 = [10,20]      
vertical1   = [100,250]    
plt.plot(horizontal1, vertical1) 

horizontal2 = [10, 20, 50, 70]
vertical2 = [30, 70, 20, 80]
plt.plot(horizontal2, vertical2) 

plt.show()

```


### Part6: displaying more than one plot

The subplot() function enables multiple plots to be displayed in the layout of the output figure; the layout is arranged in a table format with rows and columns.

The subplot() function accepts three parameters to describe the layout.
+ The first argument represents the number of rows
+ The second argument represents the number of columns
+ The third argument represents the position in the layout


```
import matplotlib.pyplot as plt

horizontal1 = [10,20]      
vertical1   = [100,250]    
plt.subplot(1, 2, 1)                #the layout is 1 row, 2 columns, and this plot is in the first position
plt.plot(horizontal1, vertical1)
plt.title("First plot")             #a title for this plot

horizontal2 = [10, 20, 50, 70]
vertical2 = [30, 70, 20, 80]
plt.subplot(1, 2, 2)                #the layout is 1 row, 2 columns, and this plot is in the second position
plt.plot(horizontal2, vertical2) 
plt.title("Second plot")            #a title for this plot


plt.suptitle("All plots")           #add one title on the collection
plt.show()
```
