 head(iris)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa

##Make the plot from the above code. Formulate a plot where the y-axis states the Sepal Length, the x-axis is blank, the title indicates that the plot is of genus Iris (ignore italics for now), and the color of the boxplot is blue. Do not copy and paste the code – retype it
> boxplot(iris$Sepal.Length,main="iris",ylab="Sepal Length",xlab="",col="blue")
##Plot Iris Petal Width by species. Make sure the boxplot has a proper title and axes. Color setosa red, versicolor blue, and virginica yellow.
> boxplot(iris$Sepal.Length~iris$Species,main="Iris Species",ylab="Sepal Length",xlab="Iris Species",col=c("springgreen","steelblue1","thistle"))
##Open the help page for the function lm(). What are its first four arguments?
#1. formula --> an object of class "formula" (or one that can be coerced to that class): a symbolic description of the model to be fitted. The details of model specification are given under details
#2. data --> an optional data frame, list or environment (or object coercible by as.data.frame to a data frame) containing the variables in the model. If not found in data, the variables are taken from environments (formula), typically the environment from whcih lm() is called
#3. subset --> an optional vector specifying a subset of observations to be used in the fitting process 
#4. weights --> an optional vector of weights to be used in the fitting process. Should be NULL or a numeric vector. If non-NULL, weighted least squares is used with weights(), that is (minimizing sum(w*e^2)); otherwise ordinary least squares is used.
##How does the order of the variables in the formula correspond to the
order of the variables in the plot?
#The code is written as y~x, which changes the formula structure from y=mx+b to y=bx+a
##Which arguments control which of the line parameters? Generate the plot where the line is grey, the line type is dashed, and the line width is five units.
#col=color, lty=line style, and lwd=line width, these control the line parameters
> mod=lm(iris$Petal.Width~iris$Petal.Length)
> plot(iris$Petal.Length,iris$Petal.Width)
> abline(mod,col="grey",lty=2,lwd=5)
##What is the R^2 and p-value of the line? Is the line significantly different from a slope of 0?
> summary(mod)

Call:
lm(formula = iris$Petal.Width ~ iris$Petal.Length)

Residuals:
     Min       1Q   Median       3Q      Max 
-0.56515 -0.12358 -0.01898  0.13288  0.64272 

Coefficients:
                   Estimate Std. Error t value Pr(>|t|)    
(Intercept)       -0.363076   0.039762  -9.131  4.7e-16 ***
iris$Petal.Length  0.415755   0.009582  43.387  < 2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.2065 on 148 degrees of freedom
Multiple R-squared:  0.9271,	Adjusted R-squared:  0.9266 
F-statistic:  1882 on 1 and 148 DF,  p-value: < 2.2e-16
#The R-squared value of the line = 0.9266, the p-val = < 2.2e-16, the slope is 0.415755 which is a positive trend compared to 0
##Generate an x-y plot with a line of best fit for the relationship between Sepal Length and Sepal Width, with Sepal Width as the response variable. Make each species its own color and shape. Report the intercept, slope, R2, and p value for the line of best fit. Include a legend in the top-left corner of the plot.
> Irisplot<-lm(Sepal.Width~Sepal.Length,data=iris)
> Irisplot

Call:
lm(formula = Sepal.Width ~ Sepal.Length, data = iris)

Coefficients:
 (Intercept)  Sepal.Length  
     3.41895      -0.06188  

> iris.summary<-summary(Irisplot)
> iris.summary

Call:
lm(formula = Sepal.Width ~ Sepal.Length, data = iris)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.1095 -0.2454 -0.0167  0.2763  1.3338 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept)   3.41895    0.25356   13.48   <2e-16 ***
Sepal.Length -0.06188    0.04297   -1.44    0.152    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.4343 on 148 degrees of freedom
Multiple R-squared:  0.01382,	Adjusted R-squared:  0.007159 
F-statistic: 2.074 on 1 and 148 DF,  p-value: 0.1519
#Intercept = 3.41895, slope = -0.06188, R-squared = 0.007159, p-val = 0.1519
> colors.for.species<-c("setosa"="springgreen","versicolor"="steelblue2", "virginica"="thistle")
> shapes.for.species<-c("setosa"=2,"versicolor"=8, "virginica"=9)
> plot(iris$Sepal.Length~iris$Sepal.Width,pch = shapes.for.species,col = colors.for.species,xlab = "Sepal Length",ylab = "Sepal Width",main = "Sepal Width vs Sepal Length")
> mod<-plot(iris$Sepal.Length~iris$Sepal.Width,pch = shapes.for.species,col = colors.for.species,xlab = "Sepal Length",ylab = "Sepal Width",main = "Sepal Width vs Sepal Length")
> mod<-lm(iris$Sepal.Length~iris$Sepal.Width,pch = shapes.for.species,col = colors.for.species,xlab = "Sepal Length",ylab = "Sepal Width",main = "Sepal Width vs Sepal Length")
> abline(mod,lty=2,lwd=2,)
> legend("topleft",legend=levels(iris$Species),col=colors.for.species,pch=shapes.for.species,bty="n")
##Write a simple function that takes in two arguments, x and y, and then adds them together.
#Building a function 
> function.a<-function(x,y){x + y}
> function.a
function(x,y){x + y}
> function.a(1,2)
[1] 3
##Write code that will generate a loop to print out every even number between 20 and 30, inclusive.
> for(i in c(20:30)) {print(i)}
[1] 20
[1] 21
[1] 22
[1] 23
[1] 24
[1] 25
[1] 26
[1] 27
[1] 28
[1] 29
[1] 30
## Write code that will generate a random sample of these ten prime numbers: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29.
> primes<-c(2,3,5,7,11,13,17,19,23,29)
> primes
 [1]  2  3  5  7 11 13 17 19 23 29
> sample(primes)
 [1]  3 17 13 29 11  7 19  5  2 23
##Generate 100 data points from all four distributions mentioned. Explicitly state your arguments used and plot the results with both a histogram and a density function.
#normal distribution: 
> rnorm
function (n, mean = 0, sd = 1) 
.Call(C_rnorm, n, mean, sd)
<bytecode: 0x8887fa200>
<environment: namespace:stats>
> args(rnorm)
function (n, mean = 0, sd = 1) 
NULL
> norm=rnorm(n=100)
> norm
  [1] -0.92669562 -1.11049483 -0.06094980  0.48352885 -1.59519859 -0.46384668  1.15107553 -0.21410661
  [9]  0.92417141  0.81965889  1.09449427 -0.09485504  1.66356515  1.18543626 -1.78391685  0.28437131
 [17]  0.64413749  0.16107909  1.12459027  1.30755542 -0.84446815  1.74716915 -0.56148423 -0.56565842
 [25] -0.94650194  0.42855251 -0.56423971 -0.09916665  1.12998054  0.30267605 -0.75466135 -0.11388453
 [33] -0.62205939  0.47177885 -0.64431113 -1.10045240 -0.83922563 -0.20818481  1.12186345 -1.55615994
 [41]  1.51731157  0.60569688 -0.74721869  0.59809727 -0.74149791  0.08647325 -1.05359121 -1.25231229
 [49] -1.27071553 -0.34308464 -0.59791082  0.01267478  0.09691187 -0.57392749 -0.70923699  0.32924093
 [57]  0.81264209  2.01960235 -0.37085711 -1.08322823  1.15002422  0.46484187  0.26775650  0.49494268
 [65]  0.71324766 -1.28793846  0.56501651  1.80985336 -0.70779858 -1.24337620 -1.01379423 -0.65900000
 [73] -0.34320935  0.63617369 -0.47246457 -1.76875871  0.05123248  0.19769795 -1.70471872  0.01389302
 [81] -0.94973314 -0.19363002 -1.27744157  2.37239941 -0.60975916  0.15941483 -1.31573108  1.41229206
 [89] -0.37472242 -0.77129520 -0.24210670  0.24378121 -0.34787477 -1.04343027  1.05518165 -0.63842668
 [97] -1.72854746  0.23605751  0.41419496 -1.38560824
 > hist(norm)
 > plot(density(norm))
 #uniform distribution 
 > runif
function (n, min = 0, max = 1) 
.Call(C_runif, n, min, max)
<bytecode: 0x892ee4b30>
<environment: namespace:stats>
> args(rnorm)
function (n, mean = 0, sd = 1) 
NULL
> unif=runif(n=100)
> unif
  [1] 0.074007559 0.765578128 0.132597580 0.243103715 0.916905067 0.916193897 0.789064810 0.074976456
  [9] 0.874052321 0.374422747 0.755008505 0.155070734 0.656336974 0.635262763 0.001727013 0.477696435
 [17] 0.680159362 0.012628658 0.220538330 0.888015225 0.642860403 0.250710114 0.670660305 0.274005329
 [25] 0.967079391 0.718051941 0.182848711 0.648849379 0.453741301 0.700370525 0.584004256 0.632467893
 [33] 0.651935347 0.567722904 0.768373755 0.028174242 0.370952523 0.067529385 0.548864058 0.368457740
 [41] 0.736166748 0.386776753 0.298287659 0.503850597 0.030394601 0.042201704 0.728145669 0.748926395
 [49] 0.164305116 0.014202751 0.370834364 0.849225248 0.593424806 0.739539857 0.059309117 0.568185393
 [57] 0.068717031 0.890986192 0.656907650 0.818685298 0.329712536 0.174275223 0.010611429 0.137614514
 [65] 0.673972758 0.111758211 0.933264817 0.163698239 0.988574232 0.571708359 0.011110462 0.454071261
 [73] 0.931604480 0.081837314 0.951094103 0.673952237 0.238362936 0.347772835 0.923743658 0.416407107
 [81] 0.629249168 0.223971069 0.971514938 0.488881229 0.143521084 0.796940579 0.212390228 0.915944061
 [89] 0.533100311 0.991829530 0.651188469 0.513419893 0.766355614 0.262441075 0.437503585 0.892534096
 [97] 0.722499526 0.044050038 0.986221640 0.507900800
> hist(unif)
> plot(density(unif))
#chi-squared
> rchisq
function (n, df, ncp = 0) 
{
    if (missing(ncp)) 
        .Call(C_rchisq, n, df)
    else .Call(C_rnchisq, n, df, ncp)
}
<bytecode: 0x88807e238>
<environment: namespace:stats>
> args(rchisq)
function (n, df, ncp = 0) 
NULL
> chisq=rchisq(n=100,df=1)
> chisq
  [1] 0.3492428337 0.9304116294 0.4410593739 0.2005143262 0.1547886356 0.2900575412 1.2202169708
  [8] 0.4476389920 0.2762452879 0.0141719172 1.4266774135 0.0912123774 2.8026399448 0.1385852382
 [15] 2.9819221176 0.6453985904 0.8148416681 0.4121514375 2.6909774416 0.1687645737 0.5183697573
 [22] 0.2580415137 0.0442225359 0.0012272349 1.7689778837 0.3914430538 2.7047456628 0.6647820870
 [29] 1.5860137397 0.3350564232 1.4531034810 0.3346861411 0.6346420148 0.6218437924 0.1224346801
 [36] 0.3124173093 0.0147072976 0.5207692598 3.2746545004 0.0345625440 0.6401746993 0.1705945282
 [43] 3.1342229363 2.2068106928 3.9557749481 0.1894263164 0.0048547592 0.1618319855 0.1716939661
 [50] 0.0613225470 1.2165618668 0.1728162243 0.2379366028 2.8984662456 3.9104239136 0.1253401455
 [57] 0.0345095470 1.0170554721 0.0073650847 0.2909649589 0.6801788303 4.2029638625 1.6372482658
 [64] 1.9877406503 1.0414354071 1.8473399870 0.9952498727 0.8584442622 0.6843250614 0.3737860539
 [71] 5.1943178542 0.5054593283 1.0216214000 1.8014355313 0.4701573505 0.2372513404 1.5742872500
 [78] 0.0030758634 0.1154654047 0.4244479684 0.4433745029 0.6752069498 0.0005193569 0.5659596779
 [85] 0.3877227557 0.1813313632 0.0119875840 3.0406940738 5.6064520794 0.0165270409 0.0981852857
 [92] 1.8052334423 0.0234673674 2.7249004580 0.4588398860 2.0549853468 1.8019198169 0.5523460896
 [99] 2.7336648311 0.2591914655
 > hist(chisq)
 > plot(density(chisq))
 #binomial distribution 
 > rbinom
function (n, size, prob) 
.Call(C_rbinom, n, size, prob)
<bytecode: 0x8880811f8>
<environment: namespace:stats>
> args(rbinom)
function (n, size, prob) 
NULL
> binom=rbinom(n=100,size=1,prob=1)
> binom
  [1] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [52] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
> binom=rbinom(n=100,size=1,prob=0.5)
> binom
  [1] 1 0 0 0 1 1 0 1 0 1 1 0 0 0 0 0 0 1 0 0 0 0 1 1 1 0 1 1 1 0 0 0 1 0 1 0 0 1 0 0 0 1 0 0 0 0 0 1 0 0 0
 [52] 0 1 1 1 0 0 1 0 0 1 0 0 1 0 1 1 1 1 0 0 0 0 1 1 0 1 0 0 0 0 1 1 1 1 0 0 0 1 1 0 0 0 0 0 1 0 1 1 1
> hist(binom)
> plot(density(binom))