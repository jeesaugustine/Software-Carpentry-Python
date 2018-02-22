# Software Carpentry Workshop: Session3: Python Programming 
SWC workshop, February 2018 Instructors: [Jees Augustine](https://github.com/jeesaugustine) Adapted from Rohit Rawat November 12, 2017.
Time: 1 Hour 30 Minutes 
**Lesson Overview** We have covered the basic [Python](https://python.org) Usage here in this section

- Reading Data Files 
- Creating and Manipulating  Variables 
- Data Types
- Calling Build-in Functions

**Now we will cover:**

- Writing Functions
- Scope isses in Functions, Missing arguments
- Calling Python scripts from command line


## **Why Functions ?**

Functions are

[ ] Mathematical interpretations of how to make life easy
[ ] How will I get rid of these mundane repeated tasks, for heaves sake ?
[ ] How to go from point A to point B on a map
[ ] How can I get my Instagram tell me how many filters my friend has used in their post (to keep my sanity, helps to start )

It helps you get from picture A to picture B every day;  **If you have one though**.

![courtesy](https://d2mxuefqeaa7sj.cloudfront.net/s_AEFBA043F8D1FF4EEA67EE31D838B916CDF6206837EE90F4A379DCD53212DCAA_1518742277093_13cd3b9b26fbf4d802e5ac9bb0bf92cb--baby-boy-haircuts-baby-haircut.jpg)


**Parents have done extensive research on this and mostly dads came up with multiple ‘Functions’ to fix them many ingenious ones are with popular in internet.**

![Courtesy](https://d2mxuefqeaa7sj.cloudfront.net/s_AEFBA043F8D1FF4EEA67EE31D838B916CDF6206837EE90F4A379DCD53212DCAA_1518746309408_hqdefault.jpg)


**Functions are mere ways of convenience defined under complicated jargons and terminologies**

                                                                                                          - **Jees Augustine** 

**So lets simply it for once and forever, Functions are**

- Collections of steps that accomplish a particular tasks 
- It can be summoned any time for infinite number of times
- They are also Python codes 
- Abstract away complexities of tasks ‘under-the-hood’
- Allows easy access to functionalities through defined interfaces 

**Parts of a Function** 

- Way to negotiate with the Python interpreter that this is valid ‘Function’
- An identifier to a function for us to use
- A well defined functionality section
- A defined way to indicate how well we performed the action and what are the outcomes of our calculations 

We will go through each one of them in ‘Military’ precision here, 


- **Way to negotiate with the Python interpreter that this is valid ‘Function’**
  - We use a keyword ‘def’ to indicate that, yes whatever written here goes as a function
  - Never execute them without someone explicitly summons it
- **An identifier to a function for us to use**
  - We can simply call this as the name of the function, (eg: set_alarm, calculate_area, remind_me)
  - It can be a combination of letters as well as digits
  - This is your go to place for getting expected results 
  - This should be clear, concise and easy to understand both for the programmer and for a reader. [clean is a great identifier, but what are we expected clean ? table, desktop, car, myself, credit card, neighbor, really what ? a better name would be clean_patio(), clean_kitchen_sink()]
- **Arguments** 
  - Arguments helps the functions keep themselves away from embarrassment later.
  - Imagine you call a set_alarm with a  time, its really embracing if you do not give them a time and if you don’t provide  done  Python wont forgive you.
  - remind_me: this one probably requires two fold inputs (“**what should I remind you**”, “**when should I remind you**”)
  - Arguments specify ‘*how many*’ inputs are required for this routine to work on.
  - We can have varying number of input arguments as well (We will save it for another time and day, so for us its a constant number of inputs)
  - **POP UP Quiz:  Can a Function have a Zero-Input-as-Arguments ? Give me a real life function of that sort ?**
- **A well defined functionality section**
  - In this part we clearly set out rules to work with the inputs or in case of no input how to work without one and get desired result
- **A defined way to indicate how well we performed the action and what are the outcomes of our calculations** 
  - Every function is expected to do something (may be nothing, but its just fine, most of them has got to do something) 
  - But there is someone who is waiting for the results, who has kinda stopped the execution in expectations of the results 
  -  Your function call should report back the results to it once execution is complete 
  - We use something called ‘return’ for accomplishing this

**Prototype Function**

![](https://d2mxuefqeaa7sj.cloudfront.net/s_AEFBA043F8D1FF4EEA67EE31D838B916CDF6206837EE90F4A379DCD53212DCAA_1518749462358_Picture1.png)


There are two kinds of functions (1) defined/library/in-build (2) user defined 

**Small Inro - in-build functions** 

- abs(): gives the absolute value of the input 
- bin(): gives the binary equivalent of a number 
- min([]): gives the minimum value in an input list

The whole list can be found [here](https://www2.informatik.hu-berlin.de/Themen/manuals/python/python-texinfo/built-in_functions.html).

**Big Intro - User Defined Functions** 
Lets get warmed up a bit here, 


# Problem 1: 
  - You have read a [NYTimes article on healthy life](http://www.nytimes.com/2007/11/07/health/07fat.html) and you wanted to proactively get your weight under control. But you are unclear of setting goals to achieve your goal for tracking.  Construct a simple function, **dropDown**,  that helps you make a plan get to your weight to a desired weight bound and you would like work on a week by week plan. How will you approach this ?


    def dropDown(desired_weight, current_weight, time_to_achieve_in_weeks):
        """
        Comments goes here 
        current_weight: weight of the individual before starting the plan
        desired_weight: weight of the individual after finishing the plan
        time_to_achieve_in_weeks: in how many weeks indiviual is going to achieve this goal
        This code returns the weight that needs to be lost in a week to keep up with the plan
        """
        
        target_reduction = abs(desired_weight - current_weight)
        weight_to_be_lost_per_week = (target_reduction / time_to_achieve_in_weeks)
    
        # Comments are written here
        return (weight_to_be_lost_per_week)
    } 
    
    weight_per_week = dropDown(170, 150, 5)
    

You an invoke your Function dropDown from anywhere from the function. 
**Under-the-hood**: The Python interpreter scans the entire body of the function and makes some mechanism ‘*to practice*’ whats written inside at the beginning of the code. Once it achieves that practice now you can invoke it any time you make a call to it. 


# Explaining the Python Environments

We have a dataset !!!!!!!!!!


## Pop Quiz: What is a dataset ? Why is it important ?

Our dataset today is the [gapminder](https://www.gapminder.org/data/) dataset,  


    #Balans way of doing it 
    
    # Locate the file in your local computer drive - be ready with your location or navigate to your directory
    
    # type python or python3 in your command line
    
    #Import pandas and pylab
    import pandas as pd
    import matplotlib.pyplot as plt      
    import pylab
    
    #read data into python
    my_file = pd.read_table("gapminder.txt")
    
    #select information about Africa
    Africa = my_file[my_file.continent == "Africa"]
    
    #calculate the mean
    Africa_Mean = Africa.iloc[:,5].mean()
    
    #Do the same for Europe
    Europe = my_file[my_file.continent == "Europe"]
    Europe_Mean = Europe.iloc[:,5].mean()
    
    # Create a List to store the values
    continents = ["Africa","Europe"]
    mean_gdp = [Africa_Mean, Europe_Mean]
    
    # Set figure width to 10 and height to 8
    fig_size = plt.rcParams["figure.figsize"]
    fig_size[0] = 10
    fig_size[1] = 8
    plt.rcParams["figure.figsize"] = fig_size
    
    #Plot the graph with Y axis label and Title
    plt.bar(continents,mean_gdp,align='center')
    plt.ylabel('Mean GDP/Capita')
    plt.title('Mean GDP per Capita in Africa Vs Europe')
    pylab.show()
    



# Problems Here

Image you are little ambitions here; you wanted to try this for all the continents and somehow wanted to decide where to pitch your next project on human development.

Currently you will have to call with all possible combination calls before making a comparisons.


> But lets see what are we really trying to do here,


    continents = ["first","second"]
    # we keep changing this part of the code. 



> **Is that the problem ?** 
> **If this is not the problem whats the problem ?** 
> **Why will you support a function** 


## How did we Miss imaging we decided now we are not interested in ‘mean’ anymore and rather we are interested in ‘sum’ ! how many possible changes you need ?
# Function’s defense

Functions save your time as well as **your space**, and provides nice interfaces where you can get your *plug-n-play* to get your desired results without much of repetitions. 

So Lets do it,

> Rememeber everything that we have said about ideal functions here 

Design and Layout your Function

> **Make a clear goal and write out steps, no matter how small they are, before you code. (Commas matter here)**

**Goal**: Design a method which publishes the mean GDP of a continent and yet plots the bar chart of the GDPs.

    **Input**   gapmider.txt

        **Output**  mean comparison plot GDP of a given continents 
          **Steps**   

                 **1**   Accept the input text file 
         **2**  Read the input file 
         **3**  Get the mean of a specified Continent 
         **4**  Plot the chart for these two Continents


## **Analysis** 

          **Steps**   

                 **1**   Accept the input text file (No need of a function as the deadline itself is simple command)
    
         **2**  Read the input file (This requires some intelligence and its better if you can avoid all the codes for reading input files from clustering our main functionality )
        
         **3**  Get the mean of a specified Continent  (We need a function for this, for sure )
         **4**  Plot the chart for these two Continents (no way i am going to write a eveytime, no not happening, sorry !! )
#  “Talk is cheap. Show me the code” 
                                                                                           — Linus Torvalds 

 

    def fileReader(filename):
      """
      This functions reads a '.txt' file and return its contents to the one who invokes it 
      """
        #read data into python
        my_file = pd.read_table("gapminder.txt")
        return my_file


## File ready to use as a table much better


    def calculateMeanForMyContinent(table, continent_name):
      """
      This function will help you calculate the mean of a given continent given its name from the given name and returns the value
      """
        #select information about desired continent
        continent = my_file[table.continent == continent_name]
        
        #now calculate the mean
        continent_mean = continent.iloc[:,5].mean()
        
        return continent_mean


## Mean Calculator Ready for use 


    def plotIt(ylabel, title, aligner, figure_size):
      """
      """
      # Set figure width to 10 and height to 8
      fig_size = plt.rcParams["figure.figsize"]
      plt.rcParams["figure.figsize"] = fig_size
    
      #Plot the graph with Y axis label and Title
      plt.bar(continents,mean_gdp,align=aligner)
      plt.ylabel('Mean GDP/Capita')
      plt.title('Mean GDP per Capita in Africa Vs Europe')
      pylab.show()
      plt.savefig("foo", format='pdf')
      plt.savefig("foo.pdf", bbox_inches='tight')


## Plotter is also ready lets put it all together now 
## Wait, what !!!

What we are not putting anything together, its all kept in the top of the file that we are writing,  and we are done.


    # ----- -------- ------- ------- GDP_plotter.py ----- -------- ------- ------- #
    
    
    #Import pandas and pylab
    import pandas as pd
    import matplotlib.pyplot as plt      
    import pylab
    
    # add all your fucntions here starting from here  ---------- #
    #                                                            #
    #           addtion of fucntions ends             ---------- #
    
    #read data into python
    my_table = fileReader("gapminder.txt")
    
    # calculate the mean of Africa
    Africa_Mean = calculateMeanForMyContinent(my_table, "Africa")
    # calculate the mean of Europe
    Europe_Mean = calculateMeanForMyContinent(my_table, "Europe")
    
    # Create a List to store the values
    continents = ["Africa","Europe"]
    mean_gdps = [Africa_Mean, Europe_Mean]
    # Set figure width to 10 and height to 8
    plotIt('Mean GDP/Capita', 'Mean/Capita GDP Africa Vs Europe', 'center', [10, 8])

Imagine you want plot the graph for three of the continents now ? What changes are needed ?


> Add this line after line 16
    Asian_Mean = calculateMeanForMyContinent(my_table, "Asia")


> Change line 19 and 20 to the following
    continents = ["Africa","Europe", "Asia"]
    mean_gdps = [Africa_Mean, Europe_Mean, Asian_Mean]


> Change the plotter header 
    plotIt('Mean GDP/Capita', 'Mean/Capita GDP Africa VS Europe Vs Asia', 'center', [10, 8])

Total Changes = 4 lines

## Think how much code change is needed for if we have change the original code

Answer: 5 lines

When we call function names Python will internally try to look up for its definitions and apply it to the inputs(if any).


# Default Values 

Default values helps from defaulters, who fail to produce required inputs that a function is expecting. 

Imagine you are actually working on this code, and you got pretty interested in plotting the per capita GDP of other continents with that of North America. And imagine all of your further comparison are going to be with North America, in that case I am asking even more important question.


## Can I do something that helps me avoid typing North America everything that I am calling the ‘calculateMeanForMyContinent’ Function.

Answer is yes we can,
How hard is it ? its actually quite simple, Let try to explain it here 


    def calculateMeanForMyContinent(table, continent_name="North America"):
      """
      This function will help you calculate the mean of a given continent given its name from the given name and returns the value
      """
        #select information about desired continent
        continent = my_file[table.continent == continent_name]
        
        #now calculate the mean
        continent_mean = continent.iloc[:,5].mean()
        
        return continent_mean

What did i do here, whenever I am calling the function 

    calculateMeanForMyContinent

I can specify an input parameter as a continent and if we miss to provide one instead of Python bugging you, it will automatically assume the continent you are requesting for is North America and will fetch results for it.


## **Key Points**
- Define a function using `function` name(…params…)
- The body of a function should be indented.
- Call a function using name(…values…).
- Numbers are stored as integers or floating-point numbers.
- Each time a function is called, a new stack frame is created on the call stack to hold its parameters and local variables.
- Python looks for variables in the current environment before looking for them at the top level.
- Put docstrings in functions to provide help for that function.
- Annotate your code!
- Specify default values for parameters when defining a function using name=value in the parameter list.
- Parameters can be passed by matching based on name, by position, or by omitting them (in which case the default value is used).


# **Calling Python scripts from the command line**

Just like we can call other scripts and functions from our Python programs, we can call an Python script from the command line. We use the  `Python`  command  program to do this.


    python name_of_the_script.py


    #In our case it will be 
    > python GDP_plotter.py

Imagine you wanted toe plot the values for a single continent and you wanted to supply the name of the country as an input to the code. How do we do it.

Its much more simpler, all we have to do is to modify out script so that we accept an input  from the user while we call the script.

We add the following lines to the code now,


    import sys
    # calculate the mean of Africa
    Africa_Mean = calculateMeanForMyContinent(my_table, sys.argv[1])
    # calculate the mean of Europe
    Europe_Mean = calculateMeanForMyContinent(my_table, sys.argv[2])

You are done,  now you will call our script by the follwing sequence of commands


    #Python call should be 
    # >python file_name.pyt argument_1 argument_2 [.....]
    # In our case it will be 
    > python GDP_plotter.py Africa Europe

We now write a shell script that is going to call this method on a list of countries.
Create a file `makePlots.sh`

    continents="Canada Belgium"
    python GDP_plotter.py $continents

Now its as simple as running a bash script 


    bash makePlots.sh

This may not clearly enable you to see the output graphs (bash does not allow anything to pop out of its terminal unless its something important,) but we have saved the output plots in the directory to take a look later. So problem solved.

