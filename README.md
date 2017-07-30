##title: "W2_R workshop"  
##author: "Chunhui Zhu"  
##date: "July 31, 2017"  
##output: html_document  
---

**R Bridge Course Week 2 Assignment**  
One of the challenges in working with data is wrangling.  In this assignment we will use R to perform this task. 
Here is a list of data sets:  http://vincentarelbundock.github.io/Rdatasets/ (click on the csv index for a list) 
Please select one, download it and perform the following tasks:   

---

1. Use the summary function to gain an overview of the data set.  Then display the mean and median for at least two attributes.

```{r}
Titanic <- read.csv("Titanic.csv", header = TRUE, stringsAsFactors = FALSE)
ls(Titanic) #check all column names in downloaded csv file
Age<-Titanic$Age #use data in Age column to fine mean and median
mean(Age,na.rm = TRUE) #remove NA value then find mean 
median(Age,na.rm = TRUE) #remove NA value then find median
print(Titanic[1:5, ]) #for Q6
```
---

2. Create a new data frame with a subset of the columns and rows.  Make sure to rename it. 
```{r}
Titanic1<-data.frame(Titanic$Name, Titanic$Age, Titanic$Sex, Titanic$Survived, Titanic$SexCode) #New data.frame dones Not includ column x.
print(Titanic1[1:5,]) #for Q6
```
---

3. Create new column names for the new data frame. 
```{r}
Titanic1$NewCol<- as.numeric(Titanic1$Titanic.Survived)+as.numeric(Titanic1$Titanic.SexCode) #new column named NewCol
ls(Titanic1) #find NewCol
print(Titanic1[1:5, ]) #for Q6
```
---

4. Use the summary function to create an overview of your new data frame.  The print the mean and median for the same two attributes.  Please compare. 
```{r}
summary(Titanic1) #Age.mean and Age.median are same as in Q1.
```
---

5. For at least 3 values in a column please rename so that every value in that column is renamed.  For example, suppose I have 20 values of the letter "e" in one column.  Rename those values so that all 20 would show as "excellent". 

```{r}
levels(Titanic1$Titanic.Sex) [levels(Titanic1$Titanic.Sex)=="female"]  <- "F" #change "female" to "F" for all matched value in a column
print(Titanic1[1:5,]) #for Q6
```
---

6. Display enough rows to see examples of all of steps 1-5 above. 
#Please see from above solution.
```{r}
#check out from above
```
---

7. BONUS - place the original .csv in a github file and have R read from the link.  This will be a very useful skill as you progress in your data science education and career. 
```{r}
#done
```
---

Please submit your .rmd file and the .csv file as well as a link to your RPubs. 
