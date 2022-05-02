# Stock-analysis

## Overview of Project
### Purpose
To improve the efficiency of a code that analyzes stock data by refactoring it to decrease the run time. The refactored code should allow the client to run larger data sets in notably less time than with the original script. I worked on this code in collaboration with Nick Foley and Sruthi Vayuvegula.

### Background 
Steve, the client, requested analysis of environmentally friendly “green” stocks for his parents’ investment. Initially he requested analysis of the Daqo stock, but then expanded his inquiry to cover additional green stocks after the initial analysis showed notable losses over the two years of data. We provided Steve with a macro with a user-friendly button that will run stock analysis over green stocks for the year inputted. After completing his initial project, Steve requested that we modify the code so that he can analyze the entire stock market over the past few years. Because the initial code was designed for a smaller dataset, refactoring the code made it more efficient to later be modified to run over the entire stock market dataset.
## Analysis and Results
### Analysis
To check the efficiency of the refactored code, the original script of YearValueAnalysis (the same output formatting code from the refactored macro) ran ten times for both 2017 and 2018 and the times were noted for each trial. Then the refactored subroutine, AllStocksAnalysisRefactored, ran ten times and times were noted. The time differences between the years using both the original script and refactored were compared across each trial, and then the mean and median times were compared and percentage in time change was calculated.

The main difference of the refactored code was the removal of nested FOR loops. The original code, below, had one array and used a nested FOR loop that would cycle through each index in the tickers array. It would set the initial volume for a ticker to zero before then running through all the data and pulling the total volume, starting price, and ending price for that ticker. It would then output the results to the All Stocks Analysis worksheet before cycling to the next ticker.

![Original Code](https://user-images.githubusercontent.com/101822948/166179531-f7c82057-5022-44d9-a24a-e685f4cc3fdb.png)

The refactored code, below, created additional arrays. In addition to the tickers array, we created arrays for ticker total volumes, ticker starting prices, and ticker ending prices. The multiple arrays allowed us to remove the nested FOR loops and reduced the number of times the code had to run through all the rows in the data set. The first FOR loop set all the ticker volumes to zero without having to go over each row of data. The second FOR loop got the volume, starting price, and ending price for each ticker before outputting the data to the All Stocks Analysis worksheet. 

![Refactored Code](https://user-images.githubusercontent.com/101822948/166179541-6afaaa93-300a-4ae9-b88e-74524be9168e.png)

### Results
To directly compare the run times, the formatting code used in the AllStocksAnalysisRefactored macro was added to the YearValueAnalysis subroutine. After refactoring the script, the run time for both 2017 and 2018 analyses decreased by over 86% from the original script over the same data set. In 2017 there was an 86.96% decrease in time using averages and an 86.73% decrease using the median time. In 2018 there was an 86.40% decrease in time based on average times and a 86.47% decrease in time using the median time. The following image shows the run times for a 2017 analysis using the YearValueAnalysis and then the AllStocksAnalysisRefactored subroutines.

The 2017 time using the original script was .8203125 seconds and for the refactored .109375 seconds.

YearValueAnalysis

![Original 2017 Time](https://user-images.githubusercontent.com/101822948/166179319-b303ad15-7f80-496c-8932-daa8f42ea343.png)

AllStocksAnalysisRefactored 

![Refactored 2017 Time](https://user-images.githubusercontent.com/101822948/166179376-8e2007f6-35db-4bd9-a4c6-fe115f90041f.png)

The following images are examples of the same comparison for 2018 analysis. 

The original script ran in .8671875 seconds and the refactored in .125 seconds respectively. 

YearValueAnalysis

![Original 2018 Time](https://user-images.githubusercontent.com/101822948/166179409-f189a93c-2c1d-41e7-a8b2-2af5039daf24.png)

AllStocksAnalysisRefactored

![Refactored 2018 Time](https://user-images.githubusercontent.com/101822948/166179425-c52e9ea9-4d59-4139-a342-0bd5c1342ff4.png)

The chart below depicts the time trials for the script comparisons.

![Time Trials](https://user-images.githubusercontent.com/101822948/166179464-2c9a991b-85cd-45fa-a643-fc06703ffd10.png)

This chart shows the average and median times for both 2017 and 2018 trials for both scripts. 

![Average and Median Time Differences](https://user-images.githubusercontent.com/101822948/166179482-760823d4-ac25-4836-8f4b-f821eb6621a0.png)

## Conclusion
The refactored code in every trial was notably quicker than the original subroutine. In addition to running faster compared to the original script, the refactored macro analyzed both 2017 and 2018 data with a narrower spread between times. The refactored code, on average, varied by around .0023 seconds between 2017 and 2018 analyses. The original macro run times, on average, were around .01641 seconds different between the 2017 and 2018 analyses.  

The improved run time as well as the narrower spread between analyses of different years reflects the improved efficiency of the refactored code. To further improve the efficiency, the formatting of the row headers for the output sheet could be formatted directly onto the worksheet so that only the data analyzed was being generated each time.  

## Summary
Refactoring code has many advantages. Lengthy code, particularly with multiple contributors, can become messy with redundancies, excessive parameters, code duplication, too many or too functions, and overly general code. Refactoring can improve the efficiency of the program so that it runs more quickly or uses less memory. In addition, it can make it more reader friendly for other programmers, which allows them to better understand the purpose of the code as well as make edits if needed. It is often less costly than redoing the code from scratch. However, there are some disadvantages. Refactoring could introduce new errors and bugs. In addition, as the function is the same a customer may struggle to understand the benefits of the refactored code and consider the time and effort wasteful spending. 

The advantages to refactoring the YearValueAnalysis code specifically was that it reduced the run time of the program notably. The redundancy of looping through all rows of data to reset ticker volume to zero before then pulling the volume, ticker starting price and starting end price was removed by the creation of additional arrays and removing the nested FOR loops. The disadvantage of the refactored code was, for this specific data set and the index count, was that the time saved by running the program was comparably negligible compared to the time it took to actually refactor the code. The code would have to be run nearly 103,000 times before all the time spent refactoring would be recouped! 

