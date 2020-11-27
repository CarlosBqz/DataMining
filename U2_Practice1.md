<div align="center">

**Instituto Tecnológico de Tijuana**

Departamento de Ciencias y Computación

Ingeniería en Sistemas Computacionales
 
 [![](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)

**Title:**
Practice 1

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
Tijuana, Baja California, November 13, 2020. 
</div>


### 5 geometry functions of ggplot

**geom_polygon**
```r
ggplot(data=DF1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Region))+
  geom_polygon(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
```

![](https://lh3.googleusercontent.com/pw/ACtC-3ccCfuSXLFNOXt-j5CHUtpGybMZ5GBYPd_ZGuQP5dEUlMT2_kWdlUXBPNubG38Ta7dE3O6GuYdlVJDbQLl3NF5HXJ5xDYGSyTT-3R9Cc3apOLt8VPSVpZHjwklpC0_QxLNZBPZoRcHzFwhGE9lNzcS4=w758-h495-no?authuser=0)
 

**geom_rug**
```r
ggplot(data=DF1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Region))+
  geom_rug(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
```

![](https://lh3.googleusercontent.com/pw/ACtC-3d2CcrMvE3q8nYORrPUEQvJY4uqBBO4o894c8i8Env_GZzTBtpLEmKcu0y_bZr5Y4gUY0tFBJmRGt5YFxcfGsWe1eC1xOFgcaS9y0m32gNjLZ2qXKmzsdr4uGcOTbU4LjSMcrXXZoCLwuulOEy1KIMg=w751-h496-no?authuser=0)


**geom_smooth**
```r
ggplot(data=DF1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Region))+
  geom_smooth(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
```

![](https://lh3.googleusercontent.com/pw/ACtC-3cJPP50RiusP-W6iQeaYr-y3rkOvVbXGKyrQcb3VtD8llOlGX0PCsRe22cvwCWU_NPnbo625qKzr_SL6sYL_pytv0nAfvhawhoURcZMX9sEkvBahD15XFLGF8w1lQBTLPX3B97qyT0CVn73bqj48uzu=w750-h490-no?authuser=0)


**geom_tile**


![](https://lh3.googleusercontent.com/pw/ACtC-3f5n1KCyLqNlMOCBe7-tnFtJ8Bi3uwiv-pPYsy8twgWEbltiqiWkhP7ShVvbbD0544JM-RXRUau7bu4d7aCS8aSiqHUd96zAxRo6K7Fl080Xc6xxk2BulFumoyC3isUaR4HKfbNg4duOWY4tCE-5vVP=w784-h508-no?authuser=0)

**geom_boxplot**


![](https://lh3.googleusercontent.com/pw/ACtC-3d_aBq3ofq1ml8nOszBHXrAqF50wdm44U5l1z2d4h5cpXNKFEHsNdNDulqMj3FxuJBAOq6iC_oQsLC_-Lm0dRdQBTxQt-JT_LMtojsM1aMYhAiKRTHaRbcHdDGfjPnSFkiPxEh8SGhebMxf7gEfSpQO=w801-h517-no?authuser=0)
