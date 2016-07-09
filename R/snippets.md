#Printing

```R
print(x)
```

#Sequence
```R
x<-1:20
```

#Infinity
```R
Inf
```

#Undefined value 

##Mathematical expression
```R
NaN
```
## Generic Undefined value
```R
NA
```

# Test for missing value

```R
is.na
is.nan
```

#Coercion

## Implicit coercison
```R
x <- c(TRUE,'a') ## Charcter
x <- c(10.0,'a') ## Character
x <- c(TRUE,10)  ## Numeric
```

## Explicit coercion
```R
as.integer
as.complex
as.logical
as.numeric
as.character
```

#Finding type of object

```R
class(objectName)
```

#Finding attributes of an Object
```R
attributes(m)
```

#Naming elements
```R
names(x)<- c("one","two","three")
dimnames(m) <- list(c("a","b"),c("c","d"))
```

#Lists

```R
x <- list(1,"a",TRUE,1+4i)
x <- list(a=1,b="a",c=TRUE,d=4+2i)
```

#Matrix
```R
matrix(nrow = 2, ncol = 3)
matrix(1:6, nrow = 2, ncol = 3)
dim(x) <- c(2,3)
cbind(x,y) x and y are vectors of equal length.
rbing(x,y) ## x and y are vectors of equal length.
```

#Vector

```R
c(1,2,3,4,5)
vector(mode="atomic",length=0)
```

#Factor

```R
x<-factor(c("yes","no","yes"))
table(x) ## Gives the frequency of the levels.
x<-factor(c("yes","no"),levels = c("yes","no"))

```

##Factor attributes
1.  class
2.  levels

#Data Frame
```R
read.table
read.csv
data.frame(foo = 1:4,bar=c(T,T,F,F))
```

#Data Table {Package}
```R
DT = data.table(x=norm(9),y=rep(c("a","b","c")),each=3),z=norm(9))
head(DT)
tables()
DT[2,] #subset rows
DT[c(2,3),] #subset 2 and 3rd row

DT[DT$y =="a"]
DT[,list(mean(x),sum(z))] #perform functions for all values
DT[,table(y)] # Table of y values

DT[,w:=z^2] # add new column
DT[,m:={tmp <-(x+z); log2(tmp+5)}] # Multiple operation
DT[,a:=x>0]
DT[,b:=mean(x+w),by=a] # set by a

DT[,.N,by=x] #Number of occurence of elements in column x

setkey(DT,x)
DT['a']
merge(DT1,DT2)

#Fast Reading
big_df <- data.frame(x=rnorm(1E6),y=rnorm(1E6))
file <- tempfile()
write.table(big_df,file=file,row.names=FALSE,col.names=TRUE,sep="\t",quote=FALSE)
system.time(fread(file))


```

##Converting to matrix
```R
data.matrix
```

#Reading and writing data

##read.table
```R
read.table(file,header,sep,colClasses,nrows,comment.char,skip,stringsAsFactors,na.strings,quote="")
```
##Figuring out classes of each column
```R
initial <- read.table("table.txt",nrows=10)
classes <- sapply(initial,class)
tabAll <- read.table("table.txt", colClasses = classes)
```

##Reading Excel files
XLConnect
```R
library(xlsx)
read.xlsx(filename,sheetIndex=1,header=TRUE,colIndex=2:3,rowIndex=1:20)

write.xlsx()
```

##Reading XML files
```R
library(XML)
doc <- xmlTreeParse(fileUrl,useInternal=TRUE)
rootNode <- xmlRoot(doc)
xmlName(rootNode)
rootNode[[1]]
rootNode[[1]][[1]]
xmlSApply(rootNode,xmlValue)

XPath
xpathSApply(rootNode,"//name",xmlValue)

htmlTreeParse
scores <- xpathSApply(doc,"//li[@class ="scores"],xmlValue)
```

##Reading JSON files

```R
library(jsonlite)
jsonData <- fromJSON(fileURL)
names(jsonData)
jsonData$owner$login
myjson <- toJSON(iris,pretty=TRUE)
cat(myjson)
```
#Textual formats
```R
dput(x,file="x.R")
y <- dget("x.R")
dump(c("x","y") file="xy.R") ## Multiple objects
source("x.R") ## Multiple objects
```

#Connections
```R
file(description,open="",blocking=TRUE,encoding=getOption("encoding"))

con <- file("foo.txt","r")
x <- read.csv(con)
close(con)

con <- gzfile("words.gz")
x <- readLines(con,10)
writeLines(con,c(10,11,12))
close(con)

con <- url("http://www.google.com")
close(con)
```

#Subsetting

```R
x[1]
x[x > "a"]

x[[1]]

x$bar <=> x[["bar"]]
x["bar"] # returns list

x[[1]][[2]]
m[1,2]
m[1,]
m[,2,drop = FALSE] ## Preserves dimensions
```

## Partial Matching

```R
x$a
x[["a",exact=FALSE]]
```

#Removing missing values

```R
#Create logical vector
#Subset using the logical vector

bad <- is.na(x)
x[!bad]

good  <- complete.cases(x,y)
x[good]
``` 

#Vectorised Operations

```R
x*y
m %*% n  # matrix multiplication
```

#For loop

```R
for(i in 1:4) {
}

for(i in seq_along(x)) {
   
}

for(i in nrow(m)) {
}
```

#Matrix

```R
matrix(data,row,column)
```

#While loop

```R
while(count < 10 ) {
}
```

#Assignment
```R

x <- 10

```

#Comment

```R
 ## This is a comment
```

#Infinite Loop

```R
repeat {
   break
}
```

#Next

```R
for(i in 1:10) {
   if(i == 8) {
      next
   }
}
```

#Function

```R
add2 <- function(x,y) {
   x + y
}

above10 <- function(x) {
   use <- x > 10
   x[use]
}

aboveY <- function(x,y=10) {
  use <- x > y
  x[use]
}

columnMean <- function(m,removeNA = TRUE) {
   nc <- ncol(m)
   means <- numeric(nc)
   for(i in 1:nc) {
      means[i] <- mean(m[,i], na.rm = removeNA)
   }
   means
}
```

#Finding structure of an object

```R
str(functionName)
```

##Finding formal arguments of function

```R
formals(add2)
```

## ... Argument
```R
myplot <- function(x,y,type='l',...) {
   plot(x,y,type=type,...)
}

args(paste)

function(...,sep=" ",collapse=NULL)
```

#Date

```R
as.Date("1970-1-1")
library(lubridate)
```

#Time
```R
weekdays(d)
months(d)
quarters(d)
as.POSIXct(t)
as.POSIXlt(t)
Sys.time()
=======
#Looping functions

##lapply
```R
x <- list(a=1:5, b=rnorm(10))
lapply(x,mean)

#Passing arguments to the functions
x<- 1:4
lapply(x,runif,min=0,max=10)

#Anonymous functions

->lapply(x,function(elt) elt[,1])

```
##sapply
```R
x <- list(a=1:5,b=rnorm(10))
sapply(x,mean)
```

##apply
```R
x<-matrix(rnorm(200),20,10)
apply(x,2,mean) #column MARGIN = 2
apply(x,1,sum)  #rows MARGIN=1

#faster shortcuts for sum and Means
rowSums,rowMeans,colSums,colMeans

apply(x,1,quantile,probs=c(0.25,0.75))

a<-array(rnorm(2*2*10),c(2,2,10))

apply(a,c(1,2),mean) # c(1,2) is MARGIN

rowMeans(a,dims = 3)

```

##mapply
```R
mapply(rep,1:4,4:1)

#Vectorising a function.
noise <- function(n,mean,sd) {
   rnorm(n,mean,sd)
}

mapply(noise,1:5,1:5,2)
```

##tapply
```R
x <- c(rnorm(10),runif(10),rnorm(10,1))
f <- gl(3,10) #factors with 3 levels.
tapply(x,f,mean)
tapply(x,f,range)
split(x,f)
```

##Splitting levels
```R
f1 = gl(2,5)
f2 = gl(5,2)
split(x,list(f1,f2))
```

#Stop autoprinting
```R
printMessage <- function(x) {
   if(x>0)
      print("x is greater")
   else
      print("x is less")
   invisible(x)
}
```

#Debugging
```R
traceback()

debug(lm)

options(error = recover)
```

#Simulation

##Distribution

```R
dnorm(x,mean=0,sd=1, log = FALSE)
pnorm(q,mean=0,sd=1, lower.tail = TRUE, log.p = FALSE)
qnorm(p,mean=0,sd=1,lower.tail=TRUE, log.p=FALSE)
rnorm(n,mean=0,sd=1)

set.seed(9)
rbinom(100,1,0.5)
e<-rnorm(100,0,2)
y<-0.5 + 2*x +e
plot(x,y)

sample(letters,5)
sample(1:10,replace=TRUE)
sample(1:10)

```

#Profiling

```R
a <- system.time() # proc_time
#  user  system elapsed 
#  0.035   0.006   0.042
```

##R Profiler
```R
Rprof() #start profiler
summaryRprof()
by.total
by.self
```

#Downloading files

```R
setwd("./data")
if(!file.exists("data")) {
   dir.create("data")
}

download.file(fileUrl,destfile = "./data/camera.csv",method = "curl")
dateDownloaded <- date()
```

#One dimensional summary

```R
summary(pollution$pm25)

boxplot(pollution$pm25,col="blue")
abline(h = 12)

hist(pollution$pm25,col ="green",breaks=100)
rug(pollution$pm25)
abline(v = 12, lwd = 2)
abline(v = median(pollution$pm25),col = "magenta", lwd = 4)

barplot(table(pollution$region),col = "wheat", main = "Num counties in each region")

```

#Multidimensional plots
```R
boxplot(pm25 ~ region,data = pollution,col = "red")


par(mfrow = c(2,1) , mar = c(4,4,2,1))
hist(subset(pollution,region == "east")$pm25,col = "green")
hist(subset(pollution,region == "west")$pm25,col = "green")

with(pollution,plot(lattitude,pm25),col = region)
abline(h = 12,lwd = 2, lty = 2)
```

#Graphics plotting

#Base plot
```R
library(datasets)
data(cars)
with(cars,plot(speed,dist))

?par

library(datasets)
hist(airquality$Ozone)
with(airquality,plot(Wind,Ozone))
airquality <- transform(airquality, Month = factor(Month))
boxplot(Ozone ~ Month,airquality,xlab = "Month" , ylab = "Ozone (ppb)")

par("bg")

par("mar")

# type = "n" just initializing the graphic device and other things without plotting
# actual data

with(airquality,plot(Wind, Ozone, main = "Ozone and Wind in New York city",
     type = "n"))
with(subset(airquality,Month == 5),points(Wind,Ozone,col = "blue"))
with(subset(airquality,Month != 5),points(Wind,Ozone,col = "red"))
legend("topright", pch = 1, col = c("blue","red"), legend = c("May", "Other months"))

par(mfrow = c(1,2))
with(airquality, {
   plot(Wind,Ozone, main = "Ozone and Wind")
   plot(Solar.R, Ozone, main = "Ozone and Solar Radiation")
   mtext("Ozone" , outer = TRUE)
})


```
## some parameters for par() function

* pch  - plotting symbol
* lty  - Line type
* lwd  - Line width
* col  - Plotting color ,use colors()
* xlab - x -axis label
* ylab - y-axis
* las  - label slope
* bg   - background color
* mar  - margin size
* oma  - outer margin area
* mfrow- number of plots per row
* mfcol- number of plots per col

## Base plotting functions

1. plot
2. lines
3. points
4. text
5. title
6. mtext
7. axis
8. legend
9. abline - line

#The lattice system

```R
library(lattice)
state <- data.frame(state.x77,region = state.region)
xyplot(Life.Exp ~ Income | region,data = state , layout = c(4,1))
```

#The ggplot2

```R
library(ggplot2)
data(mpg)
qplot(displ,hwy,data = mpg)
```

# Graphic devices

```R
x11()
pdf(file = "myplot.pdf")
with(faithful, plot(eruptions, waiting))
dev.off()

dev.cur()

dev.set(<integer>)
dev.copy(png,file = "plot.png")
dev.copy2pdf(file ="me.pdf")
dev.off()

```

#Lattice Functions
```R
xyplot
bwplot
histogram
stripplot
dotplot
splom
levelplot
contourplot
```
#MySQL

```R 
install.packages("RMySQL")
library(RMySQL)
library(RMySQL)
ucscDb <- dbConnect(MySQL(),user="genome", host="genome-mysql.cse.ucsc.edu")
result <- dbGetQuery(ucscDb,"show Databases;");dbDisconnect(ucscDb)

hg19 <- dbConnect(MySQL(),user="genome", db="hg19",host="genome-mysql.cse.ucsc.edu")
allTables <- dbListTables(hg19)
length(allTables)
head(allTables)
dbListFields(hg19,"affyU133Plus2")
dbGetQuery(hg19, "select count(*) from affyU133Plus2")

hg19 <- dbConnect(MySQL(),user="genome", db="hg19",host="genome-mysql.cse.ucsc.edu")
query <- dbSendQuery(hg19,"select * from affyU133Plus2 where misMatches between 1 and 3")
affyMis <- fetch(query)
quantile(affyMis$misMatches)
dbClearResult(query)
dbDisconnect(hg19)

```

#HDF5

Hierarchial Data format

```R
source("http://bioconductor.org/biocLite.R")
biocLite("rhdf5")

library(rhdf5)
created <- h5createFile("example.h5")
created

h5createGroup("example.h5","l1e1")
h5createGroup("example.h5","l1e2")
h5createGroup("example.h5","l1e1/l2e1")
h5ls("example.h5")

a = c(1,2,3,5,6)
df = data.frame(1:3,c("ab","bc","ca"))
h5write(df,"example.h5","DataFrame")
h5ls("example.h5")

A = matrix(1:10,nr=5,nc=2)
h5write(A,"example.h5","matrix")
h5write(c(12,13,14),"example.h5","matrix",index=list(1:3,1))
h5read("example.h5","matrix")
```

#Web Scrapping

```R
con <- url("http://scholar.google.com/citations?user=HI-I6C0AAAAJ&hl=en")
htmlCode <- readLines(con)
close(con)
install.packages("XML")
library(XML)
html <- htmlTreeParse(htmlCode,useInternalNodes=T)
xpathSApply(html,"//title",xmlValue)
xpathSApply(html,"//td[@id='col-citedby']",xmlValue)

library(httr)
html2 <- GET(url)
content2 <- content(html2,as="text")
parsedHtml <- htmlParse(content2,asText=TRUE)

pg2 <- GET("http://httpbin.org/basic-auth/user/passwd",authenticate("user","passwd"))
pg2
names(pg2)



```

#Useful Packages

1. file
2. url
3. gzfile
4. bzfile

?connections

##foreign package

1.  read.arff
2.  read.dta
3.  read.mtp
4.  read.octave
5.  read.spss
6.  read.xport

##Database packages
1.  RPostgreSQL
2.  RODBC
3.  RMongo
4.  rmongodb

## Reading Images

1.  jpeg
2.  readbitmap
3.  png
4.  EBImage

##GIS
1. rdgal
2. rgeos
3. raster

##Mp3
1.  tuneR
2.  seewave

# Subsetting
```R

X[,1] #by column
X[,"var1"] #by column
X[1:2,"var2"]

X[(X$var1 <= 3 & X$var3 > 11),] #subsetting rows
X[which(X$var2 >8),] #Subset without NA

```

#Sorting

```R
sort(X$var1)
sort(X$var1,decreasing=TRUE)
sort(X$var1,na.last=TRUE)

X[order(X$var1,X$var2),] #Order by a column

```

#Summary

```R
head(X,n=3)
tail(X,n=3)
summary(restData)
str(restData)
qantile(X,na.rm=TRUE,probs(0.5,0.75,0.9))
table(X,useNA="ifany")
```
#Check missing values
```R
sum(is.na(x$var1))
any(is.na(X$var1))
all(X$var1 > 10)
```

#Sums
```R
colSums(is.na(restData))
all(colSums(is.na(restData)==0)
table(restData$zipCode %in% c("21212")) # any value containing 21212
object.size(fakeData)
```

#CrossTabs
```R
data(UCBAdmissions)
DF = as.data.frame(UCBAdmissions)
summary(DF)
xt <- xtabs(Freq ~ Gender + Admit,data=DF)
xt # display frequency 

ftable(xt)

```

#Sequence
```R
seq(1,10,by=2)
seq(1,10,length=3)
seq(along = x)
```

#Binary Variables

```R
resData$zipWrong = ifelse(restData$zipCode < 0,TRUE,FALSE)
table(resData$zipWrong,resData$zipCode < 0)
```

#Breaking continuous variables into groups

```R

restData$zipGroups = cut(restData$zipCode,breaks=quantile(restData$zipCode))
table(restData$zipGroups)

library(Hmisc)
resData$zipGroups = cut2(restData$zipCode,g=4) #factor
table(resData$zipGroups)
resdata$zcf <- factor(resData$zipCode,levels=c(21010,21011))
relevel(yesnofac,ref="yes")
as.numeric(yesnofac,ref=yes)

```

#Mutate

```R
library(Hmisc); library(plyr)
resData2 = mutate(resData,zipGroups=cut2(zipCode,g=4))
table(resdata$zipGroups)
```

#Reshaping

```R
carMelt <- melt(mtcars,id=c("carname,"gear","cyl"),measure.vars=c("mpg","hp"))
cylData <- dcast(carMelt,cyl ~ variable)
cylData <- dcast(carMelt,cyl ~ variable,mean)

tapply(InsectSpray$count,InsectSpray$spray,sum)

sprCount <- lapply(split(InsectSpray$count,InsectSpray$spray),sum)
unlist(sprCount)

ddply(InsectSpraysm.(spray),summarize,sum=sum(count))

```

#dplyr

```R
select(chicago,city:dptp) #select columns
select(chicago,-(city:dptp))

i <- match("city",names(chicago)) #index of match

chicago[,-(i:j)]

filter(chicago, pm25tmean2 >30 & tmpd > 80)

arrange(chicago,date)
arrange(chicago,desc(date))

rename(chicago,pm25 = pm25tmean2)
chicago <- mutate(chicago,pm25t = pm25 = mean(pm25,na.rm = TRUE))

hotCold <- group_by(chicago,tempcat)
summarize(hotCold,pm25 = mean(pm25),o3=max(o3tmean2))

chicago %>% mutate(month = as.POSIXlt(date)$mon +1) %>% group_by(month) # pipeline operator
```

#Merging

```R
merge(x,y,by.x,by.y,all)
intersect(names(solutions),names(reviews))

join(df1,df2) #plyr joins columns with same name. left join

listD = list(df1,df2,df3)
join_all(listD)
```

#Query

```R
mean(gdp[gdp$V1 %in% intersect(fed[fed$Income.Group == "High income: nonOECD",]$CountryCode,gdp$V1),]$V2,na.rm=TRUE)
```

#Editing Text variables

##Fixing character vectors

```R
tolower()
toupper()
strsplit(names(carData),"\\.")
sub("_","",testNAme)
gsub("_","",testName) #replace all occurences in text

library(stringr)
nchar("King")

substr("Arunkumar Maniam Rajan",1,9)

paste("Arunkumar","Maniam Rajan")
paste0("Arunkumar","King")

str_trim("Arun    ")

```

##Finding Values

```R
grep("Almeda",intersection)
grepl("Almeda",intersection) # returns true or false

cameraData[!grepl("Almeda",intersection),]
grep("Almeda",intersection,value=TRUE)

```

#Kmeans

```R
dataFrame <- data.frame(x,y)
kmeansObj <- kmeans(dataFrame,centers = 3)
names(kmeansobj)
```

```R
svd(dataframe)
library(impute)
impute.knn(dataMatrix2)
svd1 = svd(scale(sub1[,-c(562,563)]))
```

#Working with Colors
```R
pal <- colorRamp(c("red","blue"))
pal(seq(0,1,len=10)) # returns matrix of RGB

pal <- colorRampPalette(c("red","yellow"))
pal(2) #returns n colors as #FF0000

library(RColorBrewer)
cols <- brewer.pal(3,"BuGn")
pal <- colorRampPalette(cols)
image(volcano,col=pal(20)
rgb(0,0,0,0.2)
library(colorspace)
```

#knitr

```R
library(knitr)
knit2html("a.Rmd")
```

#Rmarkdown
```R
```{r name,echo=TRUE,results="hide/asis",fig.height=4,fig.width=4,}
```{r setoptions,echo=FALSE}
opts_chunk$set(echo=FALSE, results="hide")
```

