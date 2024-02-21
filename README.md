
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


