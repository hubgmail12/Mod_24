Acquiring new subscribers is vital for telecom carriers to boost revenue, increase market share, and enhance brand visibility. It compensates for customer churn and fuels investments in network and technological advancements, ensuring competitive strength in a fast-evolving industry.

Understanding subscriber behaviors and their propensity to switch carriers is crucial for telecom companies. It allows them to tailor services to customer needs and reduce churn, ensuring they retain and attract customers effectively by tailoring services and promotions.

To gain a deeper understanding of subscriber behavior,we conducted a comprehensive survey aimed at identifying what is most important to subscribers and what motivates them to switch carriers. This survey helps to pinpoint the key drivers behind customer decisions, providing a foundation to more effectively address their needs and preferences.

In the subsequent analysis, we will employ various predictive models to interpret these behaviors and determine the factors that influence users to change carriers. By leveraging data-driven insights, we aim to predict the likelihood of switching under certain conditions and identify the most influential parameters affecting subscriber satisfaction and loyalty.

Our dataset comprises a range of variables designed to capture subscriber characteristics and behaviors in the telecommunications sector:

Totl entries: 69000

- Wireless Internet: Indicates whether the user has home wireless internet (1 for yes, 0 for no); data type: integer.
- Landline Internet: Indicates whether the user has home landline internet (1 for yes, 0 for no); data type: integer.
- Number of Devices: The number of mobile handsets owned; data type: integer.
- Company: The name of the user's current telecom carrier; data type: string.
- Family Size: The total number of household members; data type: integer.
- Streaming Habit: Indicates whether the user utilizes streaming services (1 for yes, 0 for no); data type: integer.
- Streaming Services: Lists the streaming services currently used by household members, such as Netflix, Hulu, etc.; data type: string; categorical.
- Satisfaction Rating: General satisfaction rating for existing services, scored from 1 to 6; data type: integer.
- Suburb: Describes the suburb's distance from the nearest major city center; data type: string; categorical.
- Likelihood of Switching: User's rating regarding their likelihood to switch carriers, from 1 to 6; data type: integer.
- switched: Indicates if the customer has switched carriers within the last three months (1 for yes, 0 for no); data type: integer.
- Date: Date the response was recorded
- Price rating, Speed rating, Coverage rating, customer service; Rating ( 1 - 5 ) data type: infloatteger


The project is done in Colab since I did not have the desktop power to process the models. So the best expereicne is to use the link in Github to run this in Colab, or you can use the notebook that is also added to the Git repository.


The Goal to use this data, is to better understand what features most impact users sitching networks and provide predictions for identifying possible new customers.


Data Conditon:

Feature			 # of NULLs
Number of Mobile Phones     9748
Company                     3406
price rating               13816
speed rating               13856
coverage rating            13753
customer service           13886
overall Likelihood         13785
suburb                     11445
Streaming Services         28852 

To process the Data, I dropped suburb, Date and Streaming Services, since these do not have any signifcanrt impact.

In order to resolve the remianer of NULL features, I utilized KNNImputer to populate the NULL features.

One of the issues with data is that there was no correlation between the features hence I used few different models to find the best model

Between the 4 models I attempted, Decition Tree seemed to be the best model.

I also used sysntatic data that I generated to use the prediction model to see if the custoemrs using those criteria they would switch their company,

Currently using this model, it can accept the dataset and provide prediction.

The other significant thing about the learning from this data is that top 3 features that customer switch were:
- Wireless Internet capability
- Count of Mobile phones in the household
- the current company is Verizon.

Although this is an observation, during the same period that this survey was gathered, Verizon did have the most lost mobile subscribers and one of the most attractive offer in the market was from t-Mobile offering special discount for 3+ mobile phones.

Future Enhancements:

There are a few things that needs to be done and investigated regarding this dataset and possibly exploring other models.

Given the Data correlation was mostly nuetral, one suggeston is that to change the questionaire or perform additional data engineering to change the answer input or rating mechanisim.

