**Scenario**: You are a Data Scientist working for a consulting firm.
One of your colleagues from the Auditing Department has asked you
to help them assess the financial statement of organization X.


You have been supplied with two vector of data: mounthly revenue and
expenses for the financial year in quiestion. Your task is to calculate
the following financial matrics:

-  profit for each mounth
-  profit after tax for each month (the tax rate is 30%)
-  profit margin for each month - equal to profit after tax divided by revenue
-  good months - where the profit after tax was greater than the mean for the year
-  bad months - where the profit after tax was less then the mean for years
-  the best month - where the profit after tax was max for the year
-  the worst month - where the profit after tax was min for the year


**All results need to be presented as vectors.**


Results for dollar values need to be calculate with $0.01 precision, but need to be
presented in Units of $1,000(i.e. 1k) with no decimal point.


Results for the profit margin ratio needed to be presented in units of % with no
decimal points.


**Note**: *Your collegue has warned you that it is okay for tax for any given month to be negative (in accounting terms, negative tax translates into a deferred tax asset).*


**Hint 1**
Use:
- round()
- mean()
- max()
- min()


## Data
    revenue <- c(14574.49, 7606.46, 8611.41, 9175.41, 8058.65, 8105.44, 11496.28, 9766.09, 10305.32, 14379.96, 10713.97, 15433.50)
    expenses <- c(12051.82, 5695.07, 12319.20, 12089.72, 8658.57, 840.20, 3285.73, 5821.12, 6976.93, 16618.61, 10054.37, 3803.96)



## Profit for each mounth
    profit <- revenue - expenses
    profit



## Profit after tax for each month (the tax rate is 30%)
    tax <- round(0.30 * profit, 2)
    tax 



## Calculate Profit Remaining After Tax Is Deducted
    profit.after.tax <- profit - tax
    profit.after.tax



## Profit margin for each month - equal to profit after tax divided by revenue
    profit.margin <- round(profit.after.tax / revenue, 2) * 100
    profit.margin


## Calculate The Mean Profit After Tax For The 12 Months
    mean_pat <- mean(profit.after.tax)
    mean_pat
    
## Find The Months With Above-Mean Profit After Tax
    good.months <- profit.after.tax > mean_pat
    good.months

## Bad Months Are The Opposite Of Good Months !
    bad.months <- !good.months
    bad.months

## The Best Month Is Where Profit After Tax Was Equal To The Maximum
    best.month <- profit.after.tax == max(profit.after.tax)
    best.month

## The Worst Month Is Where Profit After Tax Was Equal To The Minimum
    worst.month <- profit.after.tax == min(profit.after.tax)
    worst.month

## Convert All Calculations To Units Of One Thousand Dollars
    revenue.1000 <- round(revenue / 1000)
    expenses.1000 <- round(expenses / 1000)
    profit.1000 <- round(profit / 1000)
    profit.after.tax.1000 <- round(profit.after.tax / 1000)

## Print Results
    revenue.1000
    expenses.1000
    profit.1000
    profit.after.tax.1000
    profit.margin
    good.months
    bad.months
    best.month
    worst.month

## Results:
    > revenue.1000
    [1] 15  8  9  9  8  8 11 10 10 14 11 15
    > expenses.1000
     [1] 12  6 12 12  9  1  3  6  7 17 10  4
    > profit.1000
    [1]  3  2 -4 -3 -1  7  8  4  3 -2  1 12
    > profit.after.tax.1000
     [1]  2  1 -3 -2  0  5  6  3  2 -2  0  8
    > profit.margin
     [1]  12  18 -30 -22  -5  63  50  28  23 -11   4  53
    > good.months
     [1]  TRUE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE FALSE FALSE  TRUE
    > bad.months
     [1] FALSE  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE  TRUE  TRUE FALSE
    > best.month
     [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE
    > worst.month
     [1] FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
     
 ## BONUS:
## Preview Of What's Coming In The Next Section
    M <- rbind(
      revenue.1000,
      expenses.1000,
      profit.1000,
      profit.after.tax.1000,
      profit.margin,
      good.months,
      bad.months,
      best.month,
      worst.month
    )
    
## Print The Matrix
    > M
                          [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10] [,11] [,12]
    revenue.1000            15    8    9    9    8    8   11   10   10    14    11    15
    expenses.1000           12    6   12   12    9    1    3    6    7    17    10     4
    profit.1000              3    2   -4   -3   -1    7    8    4    3    -2     1    12
    profit.after.tax.1000    2    1   -3   -2    0    5    6    3    2    -2     0     8
    profit.margin           12   18  -30  -22   -5   63   50   28   23   -11     4    53
    good.months              1    0    0    0    0    1    1    1    1     0     0     1
    bad.months               0    1    1    1    1    0    0    0    0     1     1     0
    best.month               0    0    0    0    0    0    0    0    0     0     0     1
    worst.month              0    0    1    0    0    0    0    0    0     0     0     0
