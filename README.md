# Data-Mining-on-Student-Performance-Dataset
Calculating Correlation Coefficients of different variables contributing to Students Academic Performance and using matplotlib to provide a visual representation.
We used a dataset for students’ performance in different academic subjects; subjected to their respective demographic and their socioeconomic background for our research, following are the important questions one might wonder when observing this data set with their answers as the most suitable visual data representation according to the type of data.

Research Questions
1.	Does gender, ethnicity and type of lunch make an impact on students’ scores?
2.	Does the parental education of a students have an effect on their scores?
3.	Do girls score higher than boys in math and reading?
4.	Does preparation make a difference in students score?

![1](https://user-images.githubusercontent.com/83841336/140885469-44e70100-2b03-47b7-8fc4-8b94781c38b9.png)
 

It can be easily observed from the above figure that students who were given standard lunch performed better in all the exams as better nutrition aids in healthy cognitive development and the alienation one might feel having low quality lunch when others have a standard one might lead to depression anxiety as an onset to the bullying they might have faced will also negatively affect their scores.
Furthers deductions may show that females on average scored higher than males in writing and reading whereas males scored higher in math and in Average scores females take a slight lead. Race or ethnicity does not show a linear impact on the scores. 
 ![2](https://user-images.githubusercontent.com/83841336/140885458-b68531a3-d3ea-439e-ab39-877d25fe07c0.png)
  
It can be observed in the figure that students whose parents have a higher level of education are more inclined to achieve a better score as they might get more help at home and same as before race does not show a linear increase or decrease in scores.
  
In the above figures it can be observed that in all possible cases preparation(orange) always increased students score by at least 9.4 and at max 18.3 percent which shows that preparation makes a lot of influence on scores and with prep there was no direct correspondence to the level of education the students’ parents had acquired.



![3](https://user-images.githubusercontent.com/83841336/140885464-21b5fb3f-a84b-4113-842b-f78132d5a94a.png)


![4](https://user-images.githubusercontent.com/83841336/140885467-cbe31e93-cad3-4761-b88e-a19ce05e088f.png)


Correlation of the dependent variables

We used python libraries to find the correlation between our target variables; reading writing and math score.
First we have to import required libraries after installing them through pip install in Command Prompt;
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

Then we input the file with the required data and open it for reading;
df=pd.read_csv('../input/students-performance-in-exams/StudentsPerformance.csv')
df.head()

Then we extract the required variables and determine the coefficient of correlation by dividing the covariance by the product of the variables S.D.
plt.figure(dpi=100)
plt.title('Correlation Analysis')
sns.heatmap(df.corr(),annot=True,lw=1,linecolor='white',cmap='viridis')
plt.xticks(rotation=60)
plt.yticks(rotation = 60)
plt.show()
 

OUTPUT;

![11](https://user-images.githubusercontent.com/83841336/140886418-dfe13619-1796-46d7-a63d-cea22ee48d51.png)

We can remove the unnecessary information and create a good representation by ;
corr = df.corr()
mask = np.triu(np.ones_like(corr,dtype = bool))

plt.figure(dpi=100)
plt.title('Correlation Analysis')
sns.heatmap(df.corr(),mask=mask,annot=True,lw=1,linecolor='white',cmap='viridis')
plt.xticks(rotation=60)
plt.yticks(rotation = 60)
plt.show()



OUTPUT;

![22](https://user-images.githubusercontent.com/83841336/140886414-eed0841b-85c7-4c44-b7ff-f28c6a3108eb.png)

