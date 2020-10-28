<div align="center">

**Instituto Tecnológico de Tijuana**

Departamento de Ciencias y Computación

Ingeniería en Sistemas Computacionales
 
 [![](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)

**Title:**
Evaluation 1

**Subject:**
BDD-1703 SC9A Minería de Datos

**Unit:**
 I

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
Tijuana, Baja California, October 28, 2020. 
</div>



# INTRODUCTION

## Evaluation Practice Unit 1

In this evaluation we were specified the points that should be made in R to generate the code and to be able to represent the graphs according to the same data provided, in this practice we used vectors, data frames, filters, among other functions in order to interpret the data.

A scatter-plot should be generated showing the statistics of life expectancy (y-axis) and fertility rate (x-axis) by country. The scatterplot should also be sorted by country regions. You have been provided with data for 2 years: 1960 and 2013 and are required to produce a visualization for each of these years.

# DEVELOPMENT
DECLARING THE VECTORS ASSIGNED IN THE DOCUMENT

    #Declaring the vectors
     Country_Code <-c("ABW","AFG","AGO","ALB","ARE","ARG","ARM","ATG","AUS","AUT","AZE","BDI","BEL","BEN","BFA","BGD","BGR","BHR","BHS","BIH","BLR","BLZ","BOL","BRA","BRB","BRN","BTN","BWA","CAF","CA N","CHE","CHL","CHN","CIV","CMR","COG","COL","COM","CPV","CRI","CUB","CYP","CZE","DEU","DJI","DNK","DOM","DZA","ECU","EGY","ERI","ESP","EST","ETH","FIN","FJI","FRA","FSM","GAB","GBR","GEO","GHA","GIN","GMB","GNB","GNQ","GRC","GRD","GTM","GUM","GUY","HKG","HND","HRV","HTI","HUN","IDN","IND","IRL","IRN","IRQ","ISL","ITA","JAM","JOR","JPN","KAZ","KEN","KGZ","KHM","KIR","KOR","KWT","LAO","LBN","LBR","LBY","LCA","LKA","LSO","LTU","LUX","LVA","MAC","MAR","MDA","MDG","MDV","MEX","MKD","MLI","MLT","MMR","MNE","MNG","MOZ","MRT","MUS","MWI","MYS","NAM","NCL","NER","NGA","NIC","NLD","NOR","NPL","NZL","OMN","PAK","PAN","PER","PHL","PNG","POL","PRI","PRT","PRY","PYF","QAT","ROU","RUS","RWA","SAU","SDN","SEN","SGP","SLB","SLE","SLV","SOM","SSD","STP","SUR","SVK","SVN","SWE","SWZ","SYR","TCD","TGO","THA","TJK","TKM","TLS","TON","TTO","TUN","TUR","TZA","UGA","UKR","URY","USA","UZB","VCT","VEN","VIR","VNM","VUT","WSM","YEM","ZAF","COD","ZMB","ZWE")


    Life_Expectancy_At_Birth_1960 <- c(65.5693658536586,32.328512195122,32.9848292682927,62.2543658536585,52.2432195121951,65.2155365853659,65.8634634146342,61.7827317073171,70.8170731707317,68.5856097560976,60.836243902439,41.2360487804878,69.7019512195122,37.2782682926829,34.4779024390244,45.8293170731707,69.2475609756098,52.0893658536585,62.7290487804878,60.2762195121951,67.7080975609756,59.9613658536585,42.1183170731707,54.2054634146342,60.7380487804878,62.5003658536585,32.3593658536585,50.5477317073171,36.4826341463415,71.1331707317073,71.3134146341463,57.4582926829268,43.4658048780488,36.8724146341463,41.523756097561,48.5816341463415,56.716756097561,41.4424390243903,48.8564146341463,60.5761951219512,63.9046585365854,69.5939268292683,70.3487804878049,69.3129512195122,44.0212682926829,72.1765853658537,51.8452682926829,46.1351219512195,53.215,48.0137073170732,37.3629024390244,69.1092682926829,67.9059756097561,38.4057073170732,68.819756097561,55.9584878048781,69.8682926829268,57.5865853658537,39.5701219512195,71.1268292682927,63.4318536585366,45.8314634146342,34.8863902439024,32.0422195121951,37.8404390243902,36.7330487804878,68.1639024390244,59.8159268292683,45.5316341463415,61.2263414634146,60.2787317073171,66.9997073170732,46.2883170731707,64.6086585365854,42.1000975609756,68.0031707317073,48.6403170731707,41.1719512195122,69.691756097561,44.945512195122,48.0306829268293,73.4286585365854,69.1239024390244,64.1918292682927,52.6852682926829,67.6660975609756,58.3675853658537,46.3624146341463,56.1280731707317,41.2320243902439,49.2159756097561,53.0013170731707,60.3479512195122,43.2044634146342,63.2801219512195,34.7831707317073,42.6411951219512,57.303756097561,59.7471463414634,46.5107073170732,69.8473170731707,68.4463902439024,69.7868292682927,64.6609268292683,48.4466341463415,61.8127804878049,39.9746829268293,37.2686341463415,57.0656341463415,60.6228048780488,28.2116097560976,67.6017804878049,42.7363902439024,63.7056097560976,48.3688048780488,35.0037073170732,43.4830975609756,58.7452195121951,37.7736341463415,59.4753414634146,46.8803902439024,58.6390243902439,35.5150487804878,37.1829512195122,46.9988292682927,73.3926829268293,73.549756097561,35.1708292682927,71.2365853658537,42.6670731707317,45.2904634146342,60.8817073170732,47.6915853658537,57.8119268292683,38.462243902439,67.6804878048781,68.7196097560976,62.8089268292683,63.7937073170732,56.3570487804878,61.2060731707317,65.6424390243903,66.0552926829268,42.2492926829268,45.6662682926829,48.1876341463415,38.206,65.6598292682927,49.3817073170732,30.3315365853659,49.9479268292683,36.9658780487805,31.6767073170732,50.4513658536585,59.6801219512195,69.9759268292683,68.9780487804878,73.0056097560976,44.2337804878049,52.768243902439,38.0161219512195,40.2728292682927,54.6993170731707,56.1535365853659,54.4586829268293,33.7271219512195,61.3645365853659,62.6575853658537,42.009756097561,45.3844146341463,43.6538780487805,43.9835609756098,68.2995365853659,67.8963902439025,69.7707317073171,58.8855365853659,57.7238780487805,59.2851219512195,63.7302195121951,59.0670243902439,46.4874878048781,49.969512195122,34.3638048780488,49.0362926829268,41.0180487804878,45.1098048780488,51.5424634146342)
    Life_Expectancy_At_Birth_2013 <- c(75.3286585365854,60.0282682926829,51.8661707317073,77.537243902439,77.1956341463415,75.9860975609756,74.5613658536585,75.7786585365854,82.1975609756098,80.890243902439,70.6931463414634,56.2516097560976,80.3853658536585,59.3120243902439,58.2406341463415,71.245243902439,74.4658536585366,76.5459512195122,75.0735365853659,76.2769268292683,72.4707317073171,69.9820487804878,67.9134390243903,74.1224390243903,75.3339512195122,78.5466585365854,69.1029268292683,64.3608048780488,49.8798780487805,81.4011219512195,82.7487804878049,81.1979268292683,75.3530243902439,51.2084634146342,55.0418048780488,61.6663902439024,73.8097317073171,62.9321707317073,72.9723658536585,79.2252195121951,79.2563902439025,79.9497804878049,78.2780487804878,81.0439024390244,61.6864634146342,80.3024390243903,73.3199024390244,74.5689512195122,75.648512195122,70.9257804878049,63.1778780487805,82.4268292682927,76.4243902439025,63.4421951219512,80.8317073170732,69.9179268292683,81.9682926829268,68.9733902439024,63.8435853658537,80.9560975609756,74.079512195122,61.1420731707317,58.216487804878,59.9992682926829,54.8384146341464,57.2908292682927,80.6341463414634,73.1935609756098,71.4863902439024,78.872512195122,66.3100243902439,83.8317073170732,72.9428536585366,77.1268292682927,62.4011463414634,75.2682926829268,68.7046097560976,67.6604146341463,81.0439024390244,75.1259756097561,69.4716829268293,83.1170731707317,82.290243902439,73.4689268292683,73.9014146341463,83.3319512195122,70.45,60.9537804878049,70.2024390243902,67.7720487804878,65.7665853658537,81.459756097561,74.462756097561,65.687243902439,80.1288780487805,60.5203902439024,71.6576829268293,74.9127073170732,74.2402926829268,49.3314634146342,74.1634146341464,81.7975609756098,73.9804878048781,80.3391463414634,73.7090487804878,68.811512195122,64.6739024390244,76.6026097560976,76.5326585365854,75.1870487804878,57.5351951219512,80.7463414634146,65.6540975609756,74.7583658536585,69.0618048780488,54.641512195122,62.8027073170732,74.46,61.466,74.567512195122,64.3438780487805,77.1219512195122,60.8281463414634,52.4421463414634,74.514756097561,81.1048780487805,81.4512195121951,69.222,81.4073170731707,76.8410487804878,65.9636829268293,77.4192195121951,74.2838536585366,68.1315609756097,62.4491707317073,76.8487804878049,78.7111951219512,80.3731707317073,72.7991707317073,76.3340731707317,78.4184878048781,74.4634146341463,71.0731707317073,63.3948292682927,74.1776341463415,63.1670487804878,65.878756097561,82.3463414634146,67.7189268292683,50.3631219512195,72.4981463414634,55.0230243902439,55.2209024390244,66.259512195122,70.99,76.2609756097561,80.2780487804878,81.7048780487805,48.9379268292683,74.7157804878049,51.1914878048781,59.1323658536585,74.2469268292683,69.4001707317073,65.4565609756098,67.5223658536585,72.6403414634147,70.3052926829268,73.6463414634147,75.1759512195122,64.2918292682927,57.7676829268293,71.159512195122,76.8361951219512,78.8414634146341,68.2275853658537,72.8108780487805,74.0744146341464,79.6243902439024,75.756487804878,71.669243902439,73.2503902439024,63.583512195122,56.7365853658537,58.2719268292683,59.2373658536585,55.633)

Following the declaration of the vectors, we separate the data from 1960 and 2013 in two different data frames. This will allow us to work in a more efficient way.
```r
#Creating data frames from the vectors of Life Expectancy separating the records of the years 1960 and 2013
dfLifeExp1960 <- data.frame(Country_Code, Life_Expectancy_At_Birth_1960)
dfLifeExp2013 <- data.frame(Country_Code, Life_Expectancy_At_Birth_2013)
```

After creating the data frames, we can remove the vector that we have declared at the beginning of the practice, this will free up space in the environment.

```r
#Removing vectors, we don't need them anymore
rm(Country_Code)
rm(Life_Expectancy_At_Birth_1960)
rm(Life_Expectancy_At_Birth_2013)
```

Now, we will load the csv to our environment, to do that we choose to use a different way of load files: "read.csv(file.choose())" this method will allow us to choose manually the file using our file explorer.

```r
#Choosing the csv that we are going to work with
mydata <- read.csv(file.choose())
```

After loading the csv, we will apply a filter to get only the records from 1960 and 2013 respectively. To do so, we are using the filter method and writing the data frame that we are working with followed by the condition.

```r
#Filtering the csv in years
mydata2013 <- filter(mydata, Year == 2013) 

mydata1960 <- filter(mydata, Year == 1960)
```

Now we have separated the data in four data frames, two from 1960 and two from 2013. That means we can merge the data frames with their respective years. To do so, we are using the merge function where we have to specify the two data frames that we want to combine and the values that will help us to identify how the information will be stored.
```r
#Merge the data of the csv with the data from the vectors using Country.Code as a guide
DF1960 <- merge(mydata1960, dfLifeExp1960, by.x = "Country.Code", by.y = "Country_Code")

DF2013 <- merge(mydata2013, dfLifeExp2013, by.x = "Country.Code", by.y = "Country_Code")
```

In this block of code we will create a data frame for every country using the variables DF1960 and DF2013, this is to analyze every region separately in those two years. To do so we are filtering the data frames that we have created before this block and specifying the region that we want to analyze in the condition of the filter.

```r
#By Countries
#1960
Africa1960 <- filter(DF1960, Region== "Africa")
Asia1960 <- filter(DF1960, Region== "Asia")
Europe1960 <- filter(DF1960, Region== "Europe")
MiddleEast1960 <- filter(DF1960, Region== "Middle East")
Oceania1960 <- filter(DF1960, Region== "Oceania")
TheAmericas1960 <- filter(DF1960, Region== "The Americas")
#2013
Africa2013 <- filter(DF2013, Region== "Africa")
Asia2013 <- filter(DF2013, Region== "Asia")
Europe2013 <- filter(DF2013, Region== "Europe")
MiddleEast2013 <- filter(DF2013, Region== "Middle East")
Oceania2013 <- filter(DF2013, Region== "Oceania")
TheAmericas2013 <- filter(DF2013, Region== "The Americas")
```

Now we create the plots of every region, to do so we are using the library ggplot2, to create a plot while using this function we need to write the following:
- data: the data frame that we will be using.
- x: the data that will represent x.
- y: the data that will represent y.
- color: this will separate by colors every country in the data frame.
- geom_point: this specify that we will be using a scatter plot.
- labs: this allow us to specify a title, subtitle, names of the x and y axis.
- theme: this function allow us to center the title and subtitle.

```r
#Graf por regiones
#Africa1960
Af1960 <- ggplot(data=Africa1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Africa by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Asia1960
As1960 <- ggplot(data=Asia1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Asia by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Theamericas1960
TheA1960 <- ggplot(data=TheAmericas1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in The Americas by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Europe1960
Eu1960 <- ggplot(data=Europe1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in The Europe by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Middle East1960
Midd1960 <- ggplot(data=MiddleEast1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in MiddleEast by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Oceania1960
Oce1960 <- ggplot(data=Oceania1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Oceania by Country", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Asia2013
As2013 <- ggplot(data=Asia2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Asia by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Africa2013
Af2013 <- ggplot(data=Africa2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Africa by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#TheAmericas2013
TheA2013 <- ggplot(data=TheAmericas2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in TheAmericas by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Europe2013
Eu2013 <- ggplot(data=Europe2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Europe by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Middle East 2013
Midd2013 <- ggplot(data=MiddleEast2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in MiddleEast by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
#Ocenia2013
Oce2013 <- ggplot(data=Oceania2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Country.Name))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy in Oceania by Country", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
```

Now we just print the variable where the plot is stored:

- Af1960

![](https://lh3.googleusercontent.com/wgcUrkCo2hX9rkkxciWj-h8_ZpE8slCDQNeZsbslXugl_FdSkneSznOKlh9sPbClu0Ow4jQRJ6MezvvJsvEQ7RmYx22Lmz6hCkuc9kPsbt5w16DCWP3lBrOdIlF9CK5gtI55plHKmWeIHqZx5L0cwgG554FAAN5VIefb-u7qfg9-z5MysbOiHQ4M1gAA7GHx0OKkl8Ldp1jgoyruJIeqVm8cNAItVM5CCFtuT0le_Jz3Ki6JGmsMaZzmoTqphug4R6tBwqQVh0oBtgnNctOWjiO7A1RyyVVMzy6bwJ648ZcA51JJh2ty607B3EMXaXqtrPTaZzDyoJetzVcBIiGuZzRBZBn2QHRB-_EbqDMcxWESp-VdaKRyrlJ04n8PKLxxFjy739Ldmg8VU0hEnvPGuMyHeTuugpRzQ3DZwJtrGraXwfMZXlRNIiyCkSv36kCjzn6kMqdvCPE3rKt2RZpoY50FQns3hieuwqjTuLMFH0tT6X8Yu4Fx9kGHL_CbSwLHO30nERRbWxdoeOqUO_iriRL2uS5tIKjjDv-1LrllSgEcINtKIoWoIo8dTCLa5KPU7E-6_uZOmb_dZtPIeDLaHijBRH9Kj5EpQ3Mp6cGyZLydRLygCzj7kPTvZUGMGnqCUpNqAPVolkc6kbCZHsSmT7rpjtEKRabejJfP6r5laFPKbXIel11n5I3JFHB4=w814-h540-no?authuser=0)

- As1960

![](https://lh3.googleusercontent.com/xCsRwKrf7CpWw3YPhRmPh8LAM32n0IHfk0GV2qF1IBts97E-rrch5LJJk8tx2-E-M1lk55PScLziyIYbqgLpzEF1u0TCKHrZS5VsXRKTtqq7ZLNCIZkisGR7xtZuBy7fpkereyGrRsxqOqJI94C4PcI3LcdwqGrk1fPlxGw-2A0ZlYrEdyiQYYOHZhEvw_jAxV2_9KuS0IcnaRNrfXOoCUdZ09Vju_DJj48N_mM66fV12O93hM34nN1lpFlZ8iB0gzpGibl6hj0_bLZUtO5LyRZOePis5_y9nzTpF0MHUsnNPrcbPMe4GTSqGreizaPnPkDolEs4-V0aL9Ot4qzzcv7ynyS-3vck6JKbgb5NorQgb5vP2nblJzOvXBdx_40dxqucBXI9pquCy0XBEsFCxl_vvi5TRM8J5ZPnVPqkaXEISASJcBZXoXTEtgaehLFktLGOaAt_6E5_E692mcAB1WOgWLAlGlETMqZv-rC84YqOFGGSml5iD0IKVjZKWoOuwxKjh-qV6dTwx_wodiefRFRnfeKmecz04Et8748pKb6peTJ-h_-_ZPKiqg172CPB5WMDDqr0AJB9cZsGzMqPHF-1iy_RvYBQWNT8If14y0_w6JWMZW0RBRDAjuMQ4TtFqLWgY--Kl9G8ZTV_MGvuzRBdIZ8dbBjckEgyT99fI9QpN6XM7t65Fyej1wQj=w814-h540-no?authuser=0)

- TheA1960

![](https://lh3.googleusercontent.com/Kipb1-uYlClf0T5sC0xr9GvmfC7LJOLOxPMzd2Li1AIlqIegwvZFy_EK1_F53e_tPHpkfAOvEJnLBLiBwPH0sXoO4bPMGnPK3vXV6_w9Hp88TrLVEU-A-5n24RR3hXApSqOnFBw0Mo1DzGOlesMFXdLlVRfWZ8K_VUWGckcvdj_uDT8M1B_TeHHoPc5UuZ-IYVE0w-wE_xIA9iOmcP6rKTMc3cYfNqhoPK1GquUt7nscrlXwz1kbBk9zqjowY9d0mwCq2lWgtQbv1qZbtMq5vo_36hJ4t43-RDxOcL61vvMi5EQedunrs4zaPTFPVjZxLkWtmymzvAJLWIfoKmezmY0dop-80W89meLXpG3BLMBYHiXeVgU5DuCdWuytz6PhVW7eNe9xaaG7rR4hT_aPbQS2yC-WeBBRngO0nUKphTy_s0inmapaxE_wdmSe4j3-j71U_jcCALpcvlojzqtufhrOmRctRsr-P8rwk8UOlpxicniLa2HgzyCVW3Cbr5sH8j-gIxgH5gxkLXltaKY8fV5ExLqcQDFvMFAamFZ_gHrwvoXIbzvJrVZBOPS9EgBSM4ci1EvcY9ZWlTYS1z6Mr78dCuoH64f2P7K7o9QDuD8ZjUJaYQzFGuyLXYvKTppCZqXSMKsy6ucL3Od_Hom6mKM6EmeCL0EK5cKJo3HjpvAk8G6oW_QtHV6Eayi9=w814-h540-no?authuser=0)

- Eu1960

![](https://lh3.googleusercontent.com/VrrsELHvjiMmx9kUS6SIA99-j_JpaYR-JaEQSsonJJbSCear6WYFutjKhSEFYKOaHRC3iwhVU5zQAwgcE0jRUkTZVTrH4D6uMYl2H5t2wH_LCxZRThiZrUYALawc0w4Fvwtw4m70VzfhGO-iKEo-vlsnGzTGMC-FxXxfLknQwknwx4JFu63GormjVRnNO47oMElDfmYI_LEjSB2g54YP8TK6PRfNdIjqjwga0t0ut2-t1jRtpuo-rbcZZrG37-WbWX4vyTWFOBzHjjwtme4kdU2VPVo8FdGKcBAYYhQpeaYm29ziqoPtp8HVaA2jKfNQL0nFyir7BggUtPTaUPA1dbwX6HaXAuY1QiaRjGMqutsmgkA_OmmozdsbBUt1v9iD-7edP1mvqx2ArDPCNsf4AGjOYIGSj1IbQ09KcWkyeA5Uqf8UesAiu3texcB_ThBswQDqrWq4EKodGJgSLKc6rCYtAL-T1fHV8zOfyHKG3-sU_FnYvxR7s5kc_tZPw1MHN1IiWcsTyj-GsqcnyTArbmb0l3UPwYxy_BRp4ty_LTFE6H10TysMz-vzceQhfhFNOtH-86oL-WEoFhIXTIJSKkNfIig8edXPLHqXQleMiOSv_WqJyqBM3yxyViYFHfVExq_Jc5RIeCGKEaNMiqzgZYrmsdoWSCvGcQLD9fz_RhsnaqZmE6vsEdiCO9cX=w814-h540-no?authuser=0)

- Midd1960

![](https://lh3.googleusercontent.com/FtSLePHNzbPebeIRCum2xbKVEIRWWbwcEUqUlx_R_SkV8iftOE1j2XOacLEyWGyRTecbIp3nUhoFVjth_2cDA59Efd-F5eQXAvQyhtlCY0EBPeay9qUxQr93ebFvXY4ULHjrCV_fgt_q8V55RwbOEJCN_xicvpM5Iqy-ixXIDQStioDLtfhsvDK5lXP-1HL_ECvu3POBnnN65goiPH7WZ-lyEt6MG2SZJew2rup3Qv0emcmNIvsq8kZyNNJmzvaRzkGZkTzXPWw9YHY-x_DlKshUsm2Xl6-M8SshG7qgKI6ZB-iqWBTFZrKCfwfQ4rnRbSiYoqim4hoTRcAzf1ApRWVjT8YGnSzi5YUF5vgP0qiN2QOG7LYUCUpQ0bUr3s473UR-8CnaPiDsAVu7OYczjA2wGL9UrVd-oHHuQpusNGif1RlwUlFqp2anlRdqfJUOAlKDjbPRVhR7_ePYkilFtaXzsMgOkAbbBBVbrABRPfwa2xkExYMk_mJVfibxLOFqb6wbXusHpCG9McOoKdWZf3-WCRz5YtYsHFGcSbRoHOHRZnP7YM7T-BlD1w1vYIuuY8Y5tgec5Gm0v2SQohFkM1TFWzCEpw8Z1gBL1TZl8IZrMFdLC56Ryh0uk3vz5MWWCJH5bhxwL5PTBRlyz9naPOcMRQ7t1m_Laeiu_B3Rf_0pvs5xp1Zd0epodTS1=w814-h540-no?authuser=0)

- Oce1960

![](https://lh3.googleusercontent.com/KHFGMyNqALztR1prAFlc11m8LI_2eAcsz0VhxzZR8LXAIs3j9GSMsY3vYRg1QIlTvSCy4r7P_jedbkTALcT9ifHlIGQckVIeHJYhsT86uX8r-zKl9UrBLZoODTaD-LupJanWItWSDxsaXG4WtVtf_YciSPMO4iwp7TdgAjsRP6f-7Xi2WHcE43t1WufaDRkGAu0S7JK85HqvWYr5wDv6V8Dl9nUGUqOQBNvEcFsEuQEXu_LDiczl7ub4g2EVwGL3vkMEWx5WAUqSHHX4dfK7gTb4OCvAgOIBBfTxlGIyloX38CfzVN8ahkYZf7hs7Y8bq0nyAi92BdZTgtNLnvG5UoHf9QhVfTTfimeFppWaR-vKCcIuE3uLfDq5VwgD0FW387mDBQieeb5WdcwZWoifdB5UZEASQXNh-odQsL8ik2aNpd-WP_KzAD_lr5pSuLvaVzp8-cvwyu8Zq9ez4MUHpNqnIGHjr1QDaSXIiw63KDMaxLlgPmnZhGl7Oc75ayFYsrISjWrszAEC4WmYYjLB8NAdRpMy4u3BdrMIsSoq2o9W7pZOAqCl7Mruq9tHqxk_gYgVOQiGw8TTxMHpKIqZ-TxfBCpPEOCuDVTYVF8cl9_xV8Q69U-KJnSWWq28eYO-GdLrm8_LqUnsCbVh7Sc3m2tl7ZR8tSW-8kBnTbz5MYqFX8_Tq8Xc6h7FVzC2=w814-h540-no?authuser=0)

- As2013

![](https://lh3.googleusercontent.com/K95xvN-MFwy_lthpJcR1ciYgPe6trSOjcIkLnh4FJZkv1VgEpwjOvivCM66uR7HJh-YHRsAHIHs5p_xqu-Aqneuhmzi2aPzH3xg8spYEBSKW4BBVoaGr905nUZtUYSR93wIAKDmisNSiceJcjsY968-xqmZyeVShkcUOlj0Npu1sXlDlqqCcntC2fojXkOV5oE3iU7vjNzUvtrFcJvVwdyUuTEkbHlhW-aPqo4XRwiASmAes9O--r_PcJ000PcMtErNVgDU-s3Zj9-sHpKWJwKUQUNXrJlOq9LiVcxQFLym80e9Hxm_4u-3ZL6tKv9B4acV6UZDHXJKfXfO1q7xG9J_rNpcRfJ64G5f2f0Wi_J_JWD_viGIL5LaoJhmtNGxkdHcCwgr577Fd_XaUhbUKLCUkOhWJXMpSPepinsozPDSCpMhIEIYoINOdZ0lPSJWYqsTd96cieHM3qFdngj_ogN3weBaDsIIPSf5Lg-kXGCh8dq_sklszJb01vjYxVZIBcS8dtVNbz1vGul2GyYg7LTu1DMURjw8t_3hZzvySmh3ryeVx77ax-NWJ6ki-A_piJnb_9SVC5uPMSxRLblu_9RL4_lVcUUHjpoBw4xHjx6cPCUnZDJEdv6f9fAzvEiH0m0dlUBR3w2RahBzT7UmKqj4BCNIxdL8l3cUfnO3LVlW6Cjoku1U_VdPeyb3E=w814-h540-no?authuser=0)

- Af2013

![](https://lh3.googleusercontent.com/Xqa6TOMnpD3U6PByhVq7ImHNUcFoKuCq9jATdA8LmsMzq_2jOuoH79RvSfNkYGQqflkbEcWuGLvPLrM9TlUjlEQKDW8ycqw2FoyRf1c_KH01Z0mef5ePHy54jNiaC7l4kRdhQnTq_808_5gpCvhFu-uzH92GtDd1WMhobAiGqzELXl0q8N73YmzuWbpLMnTw5vLdARxexZenV5FZvpacSOwCFYcrONOLOGVxP6P1vGaQ5Em1azr0E7L0QxfnG-zoimfjY56aZWjaz-BtBcaptUmZNJdYHsy3ELirgiBrCfKzVMxWjQ6KZzwkH0CGl5Ko9uZmuwx-LTIjmVGNS7TSm3OycjufEJavOB9mhJnmxDEgzcVPMNJ8vPH59Sb0Xqs8q121Hpdbwn9__Jn1_ofAwMXjU4Tll3iZr7FrqGJcQmLKrmB9hUMkcg5ofarworjgbRgwVLRmc-mRi8-tQd9nUNJNs7u9Jr8-iVe_iZYXFMWgzetigmx9cTupnn2kpVRxXNnDYBUX_9w6CWB2o7Gp5S4Vvcx6yTvi_6okUbMPvE1O75NUe5GhfZY7yzsTzd_y-7HmaCqmqoMNRcXpjzVGkwIotg-9cX1CKCUvvkT8alWVQAho6kcS2tDubNo-SsTs9bfiORC5GCjtrBIDQtPA31RboY62ecQNZb4OXUGZ-k6SLTmYChRe-4Xt8z1R=w814-h540-no?authuser=0)

- TheA2013

![](https://lh3.googleusercontent.com/l3s7ALPaGhbgpfs9MGHi5ycHZhRg0oydbOnaG_pogNtxfvxHez8zdHOnpuZ_nWAWnEqG3gsDlOWdV1uopzEG4ZpXcfbsF0i2XN-FV009snJSGsnpQR1uIxYmH9CUNqPrDifj9qtcfApgfVLVISB80fV-PViPLEL_tTPU73A3MxyRD27CxES1LTL-iRPNdzkDmd6IOTj2l9lBGNix5Q6JQ3EFvl8bDJbVc-QCXVJlE-LpC7sEEZwIJfecx3VtxE9Pnh8-H4CcP8Ro1YFeGwK6a1bDhEG8k1PDxoyFe1A89SbYxI2mVli_7etoemhqvp4OGbTa6-6v6qLGKmxut5TD6mERjU1G0mkqaT_tBdtqwnVwsjdi94UGP3vkqwKxMcJ-R9iqRgdz8tGEwscVfrUEdIbmpAnaLAO-DN3lFPyDhlyCWTShDFVqJMu4y_Pl0nTw0zSA_qzwarlupHKALj06mmjbpOGqjjFmxQSknz2zTjFApCGsSjs2-b_z7ejUZIF7VSXg4QiyXeHnuwLPKmYSjB6VCQ6FtWNZ1dgZKUp7Ub4lGl0M91OjMaJygKqx6zw8wfxS54wKD42Bhco_2r90tkREhK6sRRV9vJCJBHX5tyFE0J0rfIweJpNwkgjp4aUKnUrnzUEZ2SMxBBbHO_7Usf8XOzxafGkKFDVFql2uAO9Qx5oujOvvteR84t-3=w814-h540-no?authuser=0)

- Eu2013

![](https://lh3.googleusercontent.com/3GhvuSwRa-yRqdnL9Eao-2Imfb_MfDPkG-qiyPrfkwFGYrjGect27oy16jBfy2Pj3iRRYqUgKZ714-9PXMp4bfpKC6c9FrIabBoFanrsffDNTVyZPmgQm5PMbeKzMeWdplMnTPtRmSgsHTULKDBEj2neD6doIANbwQBvvedX6mk66f673zgF4ahp5buBGkA0lTwodff6u3ykVeG6bmFf0DwLVHdlJ_1GIvenGuQJCrh7rO0qFCIxVuLhNFwExabuH_TECnfV--GBT4nXtT_LdCeKK7HLtHsGc6zGpki9fwpigNlzvDXllyQcsiIam46AQdj4rH9d02zZSx4Xxf3M3zgo1tf0qY2mbPfdPoV0m7yVl8V7EGPcsui8BnUomjv2NRkdNMJ-9W_zzjK_vIr62EXRA2o3T4t9w6BVqRmQCUBl3NsYYhfuWh6GnS87thODQoym98BZQG3epCmW8_AB4GndefmVJtNIv30QcfO9RRN8naxlLTuk5iTHSvP_TLm4FNNxltuoMUyyXw3sgxbvHXtHj1GUMBA5qgrLLCdI-aZG1THb1JZOZlBlu7u9Y-uLBRNgkmMEmoqKw2pPcLZsArtSIdir1AB1y9MxZbZmRMR-6LQcycUR2JWfkGj7drotH8BuOM8ojqBxRggEh1RC3db0oSagTZ4WEvhte1g8o3HRUJbVv1-Anb-J6Oy9=w814-h540-no?authuser=0)

- Midd2013

![](https://lh3.googleusercontent.com/oB6YIz6Rsz-IMH6JPUpz6d0aG7c-y4IqOL2zJlDR3FpCLK6YNeY5qsPcfh7nEI-O8nOXYmWW5hZ57e84JjbFtU2O84yl1x_Gh4_d8vov2jmbFdB5WNBm4GvIJoLaiN3tttxJJmHMge3UR6DWYLkntddloKcylBrir8dRuPTWSlRAvD4jDansBAGO1IOIifiyncURxhfjVs2VG2S-h16dCbbpqGzyLJA6r7JrSuKg0oDJMsQavxYGfM9q27dHz0msXa9S9TecF5THVWG9o2B_mUFdWi5ywzttT4YXQSiKY3uyAkzCn_eqLL9TQLvWkSqqaLGRBOeqXGcH6-T8ooQ5nEr-IWXvffYdcWFQMg6htHMfZxB1gGQyrZf6xgpd2GcAZ_6iRP6MUTSVAoQbHZcrKqAUj_d8I8tP3MvTbcS662WQ927O1jAZo83Pk5h7ouaw8jWnyLuyqDy0fZXK-zkAEpfCjAj7esjmK63DuUY02YDk0OI472aAPF8RY1YyzRJrTQhXMLiOEs0ODRS1MwSt92NIeq0VhjL7tZjVAJrVcX4pj5DIsDGFMW_xi9whdKp4aeV02GGaaUCYU0qtEPD9pxa6cFnzQvHvWrDxIki29sXlqBXCGT55CjESc60P4AWnSHPmArXRnxQzH9Ef1ojt8i_raPB4LuPshtBQl4NqB_aClSVgYivQEs0KQFka=w814-h540-no?authuser=0)

- Oce2013

![](https://lh3.googleusercontent.com/aqzecvyM_XzG5mm_fV6Mq1XB6cvOHwXCJ3h8PMjAjQxh3UWnZ7uQrdW1OtQ6tTlPFINB0wHUApb_Bq009gkIzeq0Me-3SeNgMdcO7ShEvOfp88qt65ULLmzz8ypZjsVJhj2rTlw-EfQ-0k3FjI9Piuj9J8jFYUYVPs8jw6Y4iW0i0Ex_baLQEBgRDL1OHh-Icxv9oEt1eBm84XnXff0dVzXiy008e1KNx2P_wKY-Nr5Nv2kYAz65ZBLQ8sfq1tjz8yPKqbHOF0D7FvFqYyssNqa_ZkWGmPN1qjRoWTLhwSfqGPwh_btt-1Btx4ETyyqLAUc0Tf6k2oZCnMf0kl7um-UOpOgmKCbkeVZKXZzjBvhzRnMcnyofRqCdlo-zb_OAu0K6TIYX7-2I8-kClzokfOaBH90FmlJ6y8UGnyFxaJNnskjOF-oEmUJ8pdHxcXHdfI21TLs8UFFI5JOTnOBoqElfq7HogCsdrlNvD9TL63UQFv8fPqBvX8lP9C0sBlv3yFxCSkgF-jFJTSy2dPXs6SkTcKEN3kMKDLIuYGhWz26Rcf3l2kWgMEurmh3iZhrLwVClgrM_6kcJiRMix-bsAIbg5r2KtIgMgT9khqzgGivAS62PUNkkiucNbOSJOFKw0uKj_kjC0tZ6NXZlPrptKsKhhlbqC43B2dkARvdwsDkxXjd2P78ys7yYKvnz=w814-h540-no?authuser=0)


**Plot "Fertility Rate vs Life Expectancy" in Regions.**

To finalize the evaluation practice, we have to plot the Fertility Rate vs Life Expectancy by Regions, to do so we are using the first data frames that we combined using the merge method and the ggplot library to create the plots.

We create a variable that will store the plot named FRvsLE1960, then we fulfill the ggplot method specifying the data frame DF1960, the axis x for Fertility Rate and axis y for Life Expectancy and at the end we declare "color=Region" to separate every country in a region with a color that will identify as part of it. Then, to give a title, subtitle and a renaming of the axis, we are using the labs function aswell as the theme function that allow us to center those titles.

```r
#Here we declare the variable for plotting the data from 1960
FRvsLE1960 <- ggplot(data=DF1960,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_1960, color=Region))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy", subtitle = "1960", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))

#Here we declare the variable for plotting the data from 2013
FRvsLE2013 <- ggplot(data=DF2013,aes(x=Fertility.Rate, y=Life_Expectancy_At_Birth_2013, color=Region))+
  geom_point(alpha=0.8) + 
  labs(title = "Fertility Rate vs Life Expectancy", subtitle = "2013", x= "Fertility Rate", y = "Life Expectancy") +
  theme(plot.title = element_text(hjust = 0.5)) + theme(plot.subtitle = element_text(hjust = 0.5))
```

And finally we print the plots:

```r
FRvsLE1960
```
![](https://lh3.googleusercontent.com/pw/ACtC-3dVHByzP4kyvozJ5uijBBSt_KlyP79YJgqLM5jADKu_ZudioyjCVvzSauuTEi_823VEALnsW4cTNUPwBnojdQvuYSCiYccjJJRiZLPfKU7vl6OGHfCzSQTXEVZabLzQYhIfHvASzdMa3znLxE26icos=w814-h540-no?authuser=0)

```r
FRvsLE2013
```
![](https://lh3.googleusercontent.com/pw/ACtC-3eZJCTCkm06uKxgj9r0YUTuy0D5OXRHl6nlu6CNrm3kI0alx5QNx4-6b8F138kyVh9fXAjC-iCS-FpzHWwMb5kBP0jgz13sBDS9cDCDfFqVq-qcUPcI1yxksfRokT2AhPBYVqe0uQyrF_Ij_nWsRZyT=w814-h540-no?authuser=0)


## Conclusion
At the end of the analysis of the Life Expectancy versus Fertility Rate graphs, we were able to reach different conclusions, where the predominant ones are the following two:
- Europe has the highest average life expectancy as well as the lowest average Fertility Rate, as much as in the years 1960 and 2013, having a life expectancy of 65 to 70 years which increased in 2013 at 75 and 85 on average. Likewise, the Fertility Rate decreased to less than two children per family in 2013, when in 1960 the average was two to three children.
- On the other hand, Africa has the highest average Fertility Rate of all regions, hovering between 6 to 8 children per family, as well as the lowest life expectancy hovering around 40 to 50 years. In 2013, Africa's Fertility Rate dropped to an average of 4 to 6 children per family and its life expectancy increased to an average of 55 to 65 years.

