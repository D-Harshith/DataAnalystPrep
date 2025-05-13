Dataset: This is a fast food chain dataset and it has 9 columns. It has infromation about date, price, product name, payment type, manager and the city.

## Transforming data:
* Conver the data into table(Ctrl + T) or insert->table.
* The manager name has uneven spaces. So, use TRIM() function (=trim(Tom     Jackson)), this removes all the extra and uneven spaces.
* After chnging the values the data would be conncted to the main column so copy the column and use Alt + H + VV to paste only values or  right-click the destination cell and select "Paste Special," choose "Values".
* Ctrl + - to delete the column.
* Round up the quantity =roundup(row, 0/1/2). Then copy the values only and delete the source column.
* To add country based on city, go to data tab, select the Geography under the Data Types then select the column you want to add country.
*  To remove duplicates, in the data tab under the data tools section choose the remove duplicates.

## Descriptive Statistics
* We can use the formula like average, max, min etc. To speed up the process, go to the file tab -> options -> add-ins->choose Analysis ToolPak -> Go -> Analysis ToolPak and select. This will add Data Anlaysis in the Data tab under the Analysis.
* Then choose the Data analysis->Descriptive statistics-> Choose the input range and appropriate output options and OK.
* To get the box plot to check for any outliers, go to the insert tab under the charts select the box and whisker.
* To customize the axis, right click the chart select data, then edit the Y and X axis.

## Dashboard
* To create drop down choose the cell, go to the data tab choose the data validation in the Data Tools then select the list then choose the source column.
* To get the COuntry and City use the XLOOKUP(lookup_value, lookup array, return array). In my case, =XLOOKUP(C2,Table1[Manager],Table1[Country/region])
* To get the revenue, create the product column, then use the SUMIFS function. SUMIFS(sum range, criteria range 1, criteris 1, criteruia range 2, criteruia 2). In my case, =SUMIFS(Table1[Revenue],Table1[Product],B10,Table1[Manager],C2). Sum the revenue, criteris 1 is products which match the product I choose, then criteria 2 is Manager which matches the manager name I choose from the drop down.
* Finally, use the conditional formatting in the Styles in home tab.
