# Market Basket Analysis <br><br>

<body>A market basket analysis was conducted to identify key prescription drug associations of hospital patients. The results of this analysis could then help hospital executives understand which prescription drug combinations appear most frequently in hospital patient history. This can help executives plan for effective treatments and make more strategic decisions for the hospital system.<br><br>
To prepare for this analysis, the dataset was first transformed by performing the following steps:<br>
1. The data csv file was loaded into a Jupyter notebook as a pandas dataframe (see code file attached).<br>
2. Empty rows were removed from the dataframe.<br>
3. The rows were converted to columns and data were encoded to true/false values.<br>
This process converted a dataframe with 7501 rows and 20 columns to a dataframe with 7501 rows and 119 columns, with each column representing a specific prescription drug.</p><br><br>
The association rules were then determined following the steps below:<br>
1. Needed packages and libraries were imported and the data for the analysis was defined.<br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/d29d4815-4222-422b-a1ca-bd575be66f7b)<br>
2. The Apriori algorithm was set with a min_support of 0.001.<br>
  ![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/2e121fbd-f750-4859-8b12-78fa9aaece40)<br>
3. Association rules were determined using a metric of 'lift' > 1.0 for further pruning. This produced 40,590 rules.<br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/8884c4cd-8cbc-4f20-b1a4-c433b43613e7) <br>
4. A scatterplot of lift vs support values was generated to visualize an appropriate min_support value to significantly reduce the number of rules generated. From the scatterplot, most rules are clustered below 0.05 on the x-axis (support).<br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/bd8fa3fa-3dcf-4f2c-9988-75f697d60f6e)<br>
5. The Apriori algorithm was generated again, with a min_support value of 0.05.<br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/c94e1922-ccf8-4e3f-b464-3b4f22449400) <br>
6. New association rules were generated with lift set at 1.0 for further pruning. This produced 6 rules. <br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/018dc072-9664-4678-8e36-1bddbee8c55b)<br>
7. The 6 rules were sorted, in descending order, by the support, confidence, and lift values.
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/22f5711d-7bcd-4ddb-94da-2d87af6e805b) <br>
<br><br>
The top three rules are summarized in the table below. <br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/191061b4-ca39-4308-a222-b24937ff4f9a)<br>
<br><br>
A summary of the significance of each rule is given below:<br>
1. {carvedilol} --> {abilify}: 5.9725% of transactions include the combination of carvedilol and abilify, representing 448 patients. 34.3032% of transactions that include carvedilol also include abilify as the consequent. The lift value is greater than 1, indicating these two drugs are prescribed together more frequently than by random chance.<br>
2. {abilify} --> {carvedilol}: 5.9725% of transactions include the combination of abilify and carvedilol, representing 448 patients. 25.0559% of transactions that include abilify also include carvedilol as the consequent. The lift value is greater than 1, indicating these two drugs are prescribed together more frequently than by random chance. <br>
3. {diazepam} --> {abilify}: 5.266% of transactions include the combination of diazepam and abilify, representing 395 patients. 32.14% of transactions that include diazepam also include abilify as the consequent. The lift value is greater than 1, indicating these two drugs are prescribed together more frequently than by random chance.<br><br>

This analysis identified carvedilol, abilify, and diazepam as having the highest associations with each other. These three drugs are also listed in the top five most popular prescriptions of hospital patients.<br>
![image](https://github.com/cfuller19/market-basket-analysis/assets/101231073/f6b548c2-4f62-4658-a4fe-f792836fb0b1)<br>
Identifying the main use of each of these prescription drugs can now give insights into the potential comorbidities of hospital patients, assuming each drug is prescribed for its labeled use. This now allows for targeted treatment of patients.
</body>
