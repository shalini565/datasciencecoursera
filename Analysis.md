# Analysis

## Part 1 Plot the 30-day mortality rates for heart attack

#install.packages("data.table")
library("data.table")
#Reading in data
outcome <- data.table::fread('outcome-of-care-measures.csv')
outcome[, (11) := lapply(.SD, as.numeric), .SDcols = (11)]
outcome[, lapply(.SD
                 , hist
                 , xlab= "Deaths"
                 , main = "Hospital 30-Day Death (Mortality) Rates from Heart Attack"
                 , col="lightblue")
        , .SDcols = (11)]


Plot 1 https://github.com/shalini565/datasciencecoursera/blob/master/1.png
