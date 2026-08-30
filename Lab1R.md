# Welcome to GitHub Desktop!

This is your README. READMEs are where you can communicate what your project is and how to use it.

Write your name on line 6, save it, and then head back to GitHub Desktop.
Danielle Marichal

> ## what is the remainder of 12 divided by 5?
> 12 %% 5

## Generate two vectors of length 10. Have one be the numbers one through ten. Have the second one be the numbers 1, ½, ⅓, etc. Do not use the c()
> x <- 1:10
> x
 [1]  1  2  3  4  5  6  7  8  9 10
 y <- 1/x
> y
 [1] 1.0000000 0.5000000 0.3333333 0.2500000 0.2000000 0.1666667 0.1428571 0.1250000 0.1111111
[10] 0.1000000
> plot(x,y)
##For each of the lines of code in the previous box, explain the difference in the inputs and outputs. Why do the different lines of code produce the different outputs?
#Each value in the vector is repeated 3 times
#Each value in the vector is repeated by its own value
#Each value in the vector is repeated a specific amount of times that is set by the input
#Two vectors, the first vector is the value to be repeated, and the second indicates how many times each value is to be repeated

##Write code to generate a vector of all even numbers from 0 to 100. Save the vector as a variable, then give the sum, mean, standard deviation, variance, median, maximum, minimum, first quartile, and third quartile of that vector.
> x<-1:100
> x
  [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19  20  21  22  23  24  25
 [26]  26  27  28  29  30  31  32  33  34  35  36  37  38  39  40  41  42  43  44  45  46  47  48  49  50
 [51]  51  52  53  54  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72  73  74  75
 [76]  76  77  78  79  80  81  82  83  84  85  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100
> x[x%%2==0]
 [1]   2   4   6   8  10  12  14  16  18  20  22  24  26  28  30  32  34  36  38  40  42  44  46  48  50  52
[27]  54  56  58  60  62  64  66  68  70  72  74  76  78  80  82  84  86  88  90  92  94  96  98 100
> evens<-x[x%%2==0]
> evens
 [1]   2   4   6   8  10  12  14  16  18  20  22  24  26  28  30  32  34  36  38  40  42  44  46  48  50  52
[27]  54  56  58  60  62  64  66  68  70  72  74  76  78  80  82  84  86  88  90  92  94  96  98 100
> summary(evens)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    2.0    26.5    51.0    51.0    75.5   100.0 
> sum(evens)
[1] 2550
>sd(evens)
[1] 29.15476
> var(evens)
[1] 850
##Given vector y, generate a vector that determines if the number is even or odd using the modulo %% function. What are the addresses of those values?
> y<-c(8,3,5,7,6,6,8,9,2,3,9,4,10,4,11)
> y
 [1]  8  3  5  7  6  6  8  9  2  3  9  4 10  4 11
 > even<-(y%%2==0)
> even
 [1]  TRUE FALSE FALSE FALSE  TRUE  TRUE  TRUE FALSE  TRUE FALSE FALSE  TRUE  TRUE  TRUE FALSE
 > 400/17
[1] 23.52941
> 12*((6*15)/(40/21))
[1] 567
> 250^(1/3)
[1] 6.299605
> log10(1000)
[1] 3
##Generate the following sequences in R
> seqa<-seq(0,16,by=4)
> seqa
[1]  0  4  8 12 16
> seq(0.3,1.5,0.3)
[1] 0.3 0.6 0.9 1.2 1.5
> seq(0,-40,-10)
[1]   0 -10 -20 -30 -40
> rep(c("tropics","temperate","boreal"),c(3,3,3)) 
[1] "tropics"   "tropics"   "tropics"   "temperate" "temperate" "temperate" "boreal"    "boreal"   
[9] "boreal"  
> seqb<-c(5,3,8,2,9,3,6,9,1,0,2,7)
> seqb
 [1] 5 3 8 2 9 3 6 9 1 0 2 7
 > sum(seqb)
[1] 55
> mean(seqb)
[1] 4.583333
> length(seqb)
[1] 12
> ##Using the following sequence of numbers, sort the numbers in ascending and descending fashion.
> seqc<-c(3,9,6,1,9,4,7,8,2,6,3,8,0,2,5)
> seqc
 [1] 3 9 6 1 9 4 7 8 2 6 3 8 0 2 5
 > sort(seqc)
 [1] 0 1 2 2 3 3 4 5 6 6 7 8 8 9 9
 > rev(sort(seqc))
 [1] 9 9 8 8 7 6 6 5 4 3 3 2 2 1 0
 > ##For this problem you will learn how to use some new functions you have never seen before. For each of the following, explain what the function does and what arguments it takes 
 >##setwd(x) or set working dictionary, is a way to change your working directory in order to access files within the rstudio according to the textbook, used in tandem usually with getwd(x)
 ##read.table(x) creates R data frames from plain text files
 ##names() is used to set the names for your data columns
 > ##attach() is a function that the textbook advises against, it adds a data frame at the second position of the path, behind the global environment
 ##range() is how to find the minimum and maximum values
 ##Download “orangutan.csv” to your computer. Make sure you know where you saved it to. Then do the following.
> ##Using the functions you learned previously, read the “orangutan.csv” into R as a data.frame. Name the object apes.
> df<-read.csv("orangutanCSV.csv")
> View(df)
> apes<-df
> apes
individual.location.weight.kg.sex.Tool.use
1                     A\tBorneo\t105\tmale\tT
2                      B\tBorneo\t72\tmale\tF
3                      C\tBorneo\t60\tmale\tF
4                    D\tBorneo\t43\tfemale\tT
5                    E\tBorneo\t41\tfemale\tT
6                    F\tBorneo\t38\tfemale\tT
7                    G\tBorneo\t33\tfemale\tF
8                    H\tSumatra\t110\tmale\tF
9                    I \tSumatra\t81\tmale\tF
10                    J\tSumatra\t77\tmale\tT
11                  K\tSumatra\t42\tfemale\tT
12                  L\tSumatra\t38\tfemale\tT
13                  M\tSumatra\t37\tfemale\tF
14                  N\tSumatra\t32\tfemale\tT
15                  O\tSumatra\t30\tfemale\tF
> View(orangutanCSV)
> View(df)
> View(apes)
> View(df)
> View(orangutanCSV)
> apes<-orangutanCSV
> apes
# A tibble: 15 × 5
   individual location weight.kg sex    Tool.use
   <chr>      <chr>        <dbl> <chr>  <lgl>   
 1 A          Borneo         105 male   TRUE    
 2 B          Borneo          72 male   FALSE   
 3 C          Borneo          60 male   FALSE   
 4 D          Borneo          43 female TRUE    
 5 E          Borneo          41 female TRUE    
 6 F          Borneo          38 female TRUE    
 7 G          Borneo          33 female FALSE   
 8 H          Sumatra        110 male   FALSE   
 9 I          Sumatra         81 male   FALSE   
10 J          Sumatra         77 male   TRUE    
11 K          Sumatra         42 female TRUE    
12 L          Sumatra         38 female TRUE    
13 M          Sumatra         37 female FALSE   
14 N          Sumatra         32 female TRUE    
15 O          Sumatra         30 female FALSE  
##What are the column names of apes? Which ones are continuous and which
are categorical?
##Individual is continuous, location is categorical, weight is continuous, sex is categorical, and tool use is categorical
##Display only orangutans that are found in Borneo.
>apes<-subset(apes,location=="Borneo")
> apes
# A tibble: 7 × 5
  individual location weight.kg sex    Tool.use
  <chr>      <chr>        <dbl> <chr>  <lgl>   
1 A          Borneo         105 male   TRUE    
2 B          Borneo          72 male   FALSE   
3 C          Borneo          60 male   FALSE   
4 D          Borneo          43 female TRUE    
5 E          Borneo          41 female TRUE    
6 F          Borneo          38 female TRUE    
7 G          Borneo          33 female FALSE   
##Extract only male orangutans and save them as males. Then order males by their weights from heaviest to lightest.
> orangutanCSV<-subset(orangutanCSV,sex=="male")
> orangutanCSV
# A tibble: 6 × 5
  individual location weight.kg sex   Tool.use
  <chr>      <chr>        <dbl> <chr> <lgl>   
1 A          Borneo         105 male  TRUE    
2 B          Borneo          72 male  FALSE   
3 C          Borneo          60 male  FALSE   
4 H          Sumatra        110 male  FALSE   
5 I          Sumatra         81 male  FALSE   
6 J          Sumatra         77 male  TRUE
> category=c("A","B","C","H","I","J")
> value=c(105,72,60,110,81,77)
 > sort(value)
[1]  60  72  77  81 105 110
> rev(sort(value))
[1] 110 105  81  77  72  60
##What is the weight of the lightest of all the orangutans?
> range(apes$weight.kg)
[1]  30 110
##Extract only female orangutans and save them as females. Then give the range of weights for female orangutans.
> apes<-subset(apes,sex=="female")
> apes
# A tibble: 9 × 5
  individual location weight.kg sex    Tool.use
  <chr>      <chr>        <dbl> <chr>  <lgl>   
1 D          Borneo          43 female TRUE    
2 E          Borneo          41 female TRUE    
3 F          Borneo          38 female TRUE    
4 G          Borneo          33 female FALSE   
5 K          Sumatra         42 female TRUE    
6 L          Sumatra         38 female TRUE    
7 M          Sumatra         37 female FALSE   
8 N          Sumatra         32 female TRUE    
9 O          Sumatra         30 female FALSE  
females<-apes
> females
# A tibble: 9 × 5
  individual location weight.kg sex    Tool.use
  <chr>      <chr>        <dbl> <chr>  <lgl>   
1 D          Borneo          43 female TRUE    
2 E          Borneo          41 female TRUE    
3 F          Borneo          38 female TRUE    
4 G          Borneo          33 female FALSE   
5 K          Sumatra         42 female TRUE    
6 L          Sumatra         38 female TRUE    
7 M          Sumatra         37 female FALSE   
8 N          Sumatra         32 female TRUE    
9 O          Sumatra         30 female FALSE   
> range(apes$weight.kg)
[1] 30 43
##What is the mean weight of apes in Sumatra?
> orangutanCSV<-subset(orangutanCSV,location=="Sumatra")
> apes<-orangutanCSV
> apes
# A tibble: 8 × 5
  individual location weight.kg sex    Tool.use
  <chr>      <chr>        <dbl> <chr>  <lgl>   
1 H          Sumatra        110 male   FALSE   
2 I          Sumatra         81 male   FALSE   
3 J          Sumatra         77 male   TRUE    
4 K          Sumatra         42 female TRUE    
5 L          Sumatra         38 female TRUE    
6 M          Sumatra         37 female FALSE   
7 N          Sumatra         32 female TRUE    
8 O          Sumatra         30 female FALSE   
> mean(apes$weight.kg)
[1] 55.875
##How many of the orangutans have been seen using tools?
> apes<-subset(apes,Tool.use=="TRUE")
> apes
# A tibble: 8 × 5
  individual location weight.kg sex    Tool.use
  <chr>      <chr>        <dbl> <chr>  <lgl>   
1 A          Borneo         105 male   TRUE    
2 D          Borneo          43 female TRUE    
3 E          Borneo          41 female TRUE    
4 F          Borneo          38 female TRUE    
5 J          Sumatra         77 male   TRUE    
6 K          Sumatra         42 female TRUE    
7 L          Sumatra         38 female TRUE    
8 N          Sumatra         32 female TRUE    
> length(apes$Tool.use)
[1] 8
##What is the combined weight of the three largest female
orangutans?
> category=c("D","E","F","G","K","L","M","N","O")
> value=c(43,41,38,33,42,38,37,32,30)
> sort(value)
[1] 30 32 33 37 38 38 41 42 43
> order(value)
[1] 9 8 4 7 3 6 2 5 1
> sorted<-sort(value)
> sorted
[1] 30 32 33 37 38 38 41 42 43
> heaviestfemales<-tail(sorted,3)
> heaviestfemales
[1] 41 42 43
> sum(heaviestfemales)
[1] 126
##Generate a vector of ten unique organisms (your choice). Sample twice with replacement and twice without replacement. How do the two methods of sampling differ?
> organisms<-c("Crassotrea_virginica","Mya_arenaria","Mytilus_edulis","Mercenaria_mercenaria","Geukensia_demissa","Anomia_simplex","Ensis_leei","Argopecten_irradians","Anadara_transversa","Petricolaria_pholadiformis")
> organisms
 [1] "Crassotrea_virginica"       "Mya_arenaria"               "Mytilus_edulis"            
 [4] "Mercenaria_mercenaria"      "Geukensia_demissa"          "Anomia_simplex"            
 [7] "Ensis_leei"                 "Argopecten_irradians"       "Anadara_transversa"        
[10] "Petricolaria_pholadiformis"
> sample(organisms,size=10,replace=TRUE)
 [1] "Argopecten_irradians"  "Anomia_simplex"        "Mya_arenaria"          "Mercenaria_mercenaria"
 [5] "Argopecten_irradians"  "Anomia_simplex"        "Mya_arenaria"          "Mercenaria_mercenaria"
 [9] "Ensis_leei"            "Anadara_transversa"  
 > sample(organisms,size=10,replace=TRUE)
 [1] "Crassotrea_virginica"       "Geukensia_demissa"          "Ensis_leei"                
 [4] "Crassotrea_virginica"       "Crassotrea_virginica"       "Mercenaria_mercenaria"     
 [7] "Mercenaria_mercenaria"      "Mercenaria_mercenaria"      "Petricolaria_pholadiformis"
[10] "Argopecten_irradians" 
 > sample(organisms,size=10,replace=FALSE)
 [1] "Mercenaria_mercenaria"      "Anadara_transversa"         "Anomia_simplex"            
 [4] "Argopecten_irradians"       "Petricolaria_pholadiformis" "Ensis_leei"                
 [7] "Mya_arenaria"               "Crassotrea_virginica"       "Geukensia_demissa"         
[10] "Mytilus_edulis"     
> sample(organisms,size=10,replace=FALSE)
 [1] "Argopecten_irradians"       "Mya_arenaria"               "Anomia_simplex"            
 [4] "Geukensia_demissa"          "Crassotrea_virginica"       "Petricolaria_pholadiformis"
 [7] "Ensis_leei"                 "Mercenaria_mercenaria"      "Anadara_transversa"        
[10] "Mytilus_edulis" 
#With replacement, the generated output has randomized repeats, the output without replacement is the same 10 organisms, just ordered differently
## Read “baseball.csv” into R and answer the following questions. This is a table of all games played by the Boston Red Sox between 1876 and 2014. It was originally sourced from baseball-reference.com but has since been put behind a paywall.
> View(baseballCSV)
##What are the column names of the data?
> names(baseballCSV)
 [1] "Franchise"        "Games"            "Wins"             "Losses"           "Win.Loss.Percent"
 [6] "Runs.Scored"      "Runs.Allowed"     "Home.Games"       "Away.Games"       "Home.Wins"       
[11] "Home.Losss"       "Away.Wins"        "Away.Losses"     
##How many games were played, won, and lost, respectively?
> sum(baseballCSV$Games)
[1] 17722
> sum(baseballCSV$Wins)
[1] 9111
> sum(baseballCSV$Losses)
[1] 8528
##What are the greatest differences between wins and losses (both the greatest positive value and the greatest negative value)?
> wins<-baseballCSV$Wins
> wins
 [1]    9   30 1170    5  970    9  971    8 1027   20   17  224  332    7  218  962   11  953 1062   31
[21]    5   10    8  227    4  169  335  304   13
> losses<-baseballCSV$Losses
> losses
 [1]    6   28  967    7  930    1 1030    8  962   10    6  223  294    5  188  927   10 1147  876   22
[21]    4    5    4  168    8  125  304  252   11
> baseballCSV$Wins-baseballCSV$Losses
 [1]    3    2  203   -2   40    8  -59    0   65   10   11    1   38    2   30   35    1 -194  186    9
[21]    1    5    4   59   -4   44   31   52    2
> max(baseballCSV$Wins-baseballCSV$Losses)
[1] 203
> min(baseballCSV$Wins-baseballCSV$Losses)
[1] -194
## Which teams had the greatest differences as identified in 13C?
#Baltimore Orioles
##Which three teams do the Red Sox have the highest win percentage against? Which three teams do the Red Sox have the lowest win percentage against?
#cannot see the Boston Red Sox in file
## Calculate the ratio of runs allowed to runs scored. Plot that ratio against the percentage of games won. Optionally, include a trendline and describe the statistics of the trendline.
> runsallowedtoscoredratio<-baseballCSV$Runs.Allowed/baseballCSV$Runs.Scored
> runsallowedtoscoredratio
 [1] 0.7464789 1.0445344 0.9079965 1.0468750 0.9763923 0.4181818 1.0263274 0.9042553 0.9702866 0.6581633
[11] 0.6232877 0.9431925 0.9424435 0.9230769 0.9489383 0.9740016 0.7578947 1.0986129 0.9062967 0.7817590
[21] 0.6521739 0.7096774 0.5277778 0.8839506 1.1538462 0.8157019 0.9458081 0.9305655 0.8384615
> plot(x,baseballCSV$Win.Loss.Percent)
> plot(runsallowedtoscoredratio,baseballCSV$Win.Loss.Percent)
#There is a downwards trend displayed in the plot