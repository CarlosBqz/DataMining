<div align="center">

**Instituto Tecnológico de Tijuana**

Departamento de Ciencias y Computación

Ingeniería en Sistemas Computacionales
 
 [![](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)

**Title:**
Evaluation 2

**Subject:**
BDD-1703 SC9A Minería de Datos

**Unit:**
 II

**Professor:**
JOSE CHRISTIAN ROMERO HERNANDEZ

**Student:**

Bojórquez Vargas Carlos Francisco
16211977

Garcia Rincon Daniel Gerardo 
16212002

**Group:**
SC9A

**Date:**
Tijuana, Baja California, November 26, 2020. 
</div>



# INTRODUCTION

## Evaluation Practice Unit 2

In this practice we are asked to create the code according to an image of a graph provided with certain data to follow, which contains different information which refers to a csv file where we will create data frames for the proper handling of data, to chart, customize graphics and text among other functions within the code.

# INSTRUCTIONS

Develop the following problem with R and RStudio for the knowledge extraction that the problem requires. 

The film review website managers are very happy with their previous delivery and now have a new requirement for you. 

However, the R-code used to create the graph has been lost and cannot be recovered. 
Your task is to create the code that will recreate the same table making it look as close as possible to the original. 

# DEVELOPMENT

We start our code by loading the csv into our environment, for this we choose to use a different way of loading files: "read.csv (file.choose ())" this method will allow us to manually choose the file using our browser file.
 
    mydata <- read.csv(file.choose())

Then we will load our graphics library which is "ggplot2"

    library(ggplot2)

Since we have loaded our csv file where we have too much data that really only need a few, so we filter the information in this case will be the genres of different films.

    #filtro1
    filtro <- (mydata$Genre == "action") | (mydata$Genre == "adventure") | (mydata$Genre == "animation") | (mydata$Genre == "comedy") | (mydata$Genre == "drama")

 


 









