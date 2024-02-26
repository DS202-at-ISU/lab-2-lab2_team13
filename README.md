
<!-- README.md is generated from README.Rmd. Please edit the README.Rmd file -->

# Lab report \#1

Follow the instructions posted at
<https://ds202-at-isu.github.io/labs.html> for the lab assignment. The
work is meant to be finished during the lab time, but you have time
until Monday evening to polish things.

Include your answers in this document (Rmd file). Make sure that it
knits properly (into the md file). Upload both the Rmd and the md file
to your repository.

All submissions to the github repo will be automatically uploaded for
grading once the due date is passed. Submit a link to your repository on
Canvas (only one submission per team) to signal to the instructors that
you are done with your submission.

1. As shown by the head() function, we have 16 total variables. These variables ar as follows:
Parcel ID: <chr> (this is an identification number), Address: <chr> (this variable tells us the address of the house)
Style: <fct> (this variable tells the style of the house), Occupancy: <fct> (this gives the type of occupancy)
Sale Date: <date> (this gives the day of the sale), Sale Price: <dbl> (this gives the price of the last sale)
Multi Sale: <chr> (this tells us if the sale was part of a multi sale), YearBuilt: <dbl> (this gives the year built)
Acres: <dbl> (this gives the acres of the property), TotalLivingArea (sf): <dbl> (this is the square footage of liveable area)
Bedrooms: <dbl> (this is number of bedrooms in the house), FinishedBsmtArea (sf): <dbl> (this is square footage of basement area)
LotArea(sf): <dbl> (square footage of the lot), AC: <chr> (tells if the house has AC), FirePlace: <chr> (tells if the house has a fireplace)
Neighborhood: <fct> (the name of the neighborhood).

Sale Price Range: ($0 - $20,500,000)
Acres Range: (0.00 - 12.012)
Year Built Range: (0 - 2022) --> clearly someone entered bad data to get year 0
Bedrooms Range: (0 - 10)
TotalLivingArea (sf) Range: (0 - 6007)
FinishedBsmtArea (sf) Range: (10.0 - 6496.0)
LotArea(sf) Range: (0 - 523228)

2. There are a couple of varibles that have special interest for our objective and special interest when looking into the confines of the data. We think that the price offers special interest because of its relation to other variables, as it is influenced by the other pieces of data. Some of the most influential pieces of data in relation is the date of the sale and the date the house was built. These can explain the price of a house and how it could be higher and lower in certain times.

3.  The range of sale prices is from 0 to 20500000, which is a very large range at first glance. However, if you put it in the histogram, you see that there are only a couple of massive outliers dragging the data up to the millions. Most of the data lies under 1 million. This could cause interesting issues when correlating with different data.

```{r}
library(ggplot2)

# Set the binwidth
binwidth <- 150000

# Plot the histogram
ggplot(ames, aes(x = `Sale Price`)) +
  geom_histogram(binwidth = binwidth, position = "identity", alpha = 0.4, color = "black", fill = "lightblue") +
  labs(title = "Price of Houses",
       x = "Price",
       y = "Count") +
  theme_minimal()
```
![image](https://github.com/DS202-at-ISU/lab-2-lab2_team13/assets/158088728/a1fe92cc-0b3b-4a40-921c-4add323c77c2)

4a.(spenser) I decided to correlate the price with the date that the place was sold. I was expecting to find an upward trend where house prices have slowly crept up as a whole. However, that is not what I found; the scatter plot shows that they have stayed rather consistent. There's a good amount of variation with every year that is recorded.

```{r}

ggplot(ames, aes(x = `Sale Date`, y = `Sale Price`)) + 
  geom_point() +
  ylim(100, 500000)
  labs(title = "Sale price over years",
       x = "Sale Price",
       y = "Sale Date") +
  theme_minimal()
```
![image](https://github.com/DS202-at-ISU/lab-2-lab2_team13/assets/158088728/019d5154-ae6c-462a-aa09-79ffc1345d2b)

4b. (mohamed) The variable that can be closely related to the Sale Price would be the Total Living Area. The range of this variable is 6007 square feet, this would mean that most properties on the datset/list would span within the range of 6007 square feet.
   Based on the scatterplot, we can see that the Sale Price and Total Living Area have a Directly proportional relationship, as the Total Living Area square footage increases, the Sale Price of that property also increases. These two variables share a positive relationship which would help closely describe how dependent they are of each other.
   Some oddities I can see is the amount of outliers which drags the datapoints to a higher range, and the idea that a couple properties were sold for $0.
   
```{r}
library(ggplot2)
library(classdata)
ames
?ames
# Range Plot
ggplot(ames, aes(x = `TotalLivingArea (sf)`)) +
  geom_histogram()
#Range Code
Total_Living_Area_Range <- range(ames$`TotalLivingArea (sf)`, na.rm = TRUE)
print(Total_Living_Area_Range)

#ScatterPlot Code
ggplot(data = ames, aes(x = log(`TotalLivingArea (sf)`), y = log(`Sale Price`))) +
  geom_point()
   
```
![image]("C:\Users\moham\Desktop\DS 202\lab-2-lab2_team13\images\Lab 2  ScatterPlot - Mohamed.png")
// its not working but the image of my graph is in the images tab


4. (Ryan) I decided to show the correlation between sale price and the number of acres the property is on. We have that the price ranges from $0 to $20,500,000 and the number of acres ranges from 0 acres to 12.012 acres.
```{r}
library(ggplot2)
library(tidyverse)

ggplot(ames, aes(x = `Sale Price`)) +
  geom_histogram() +
  facet_wrap(~ `Occupancy`, scales = "free")
```
![image](https://github.com/DS202-at-ISU/lab-2-lab2_team13/blob/main/Screenshot%202024-02-25%20at%207.07.07%20PM.png?raw=true)







