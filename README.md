# DunnSense-MVP
**DunnSense - Your Mood-Based Financial Coach**

Welcome to DunnSense! A FinTech app that bridges emotional intelligence and financial literacy. The mission of DunnSense is to empower users to understand how their spending behaviors are influenced by their emotional states, using AI-driven insights and personal analytics. 

The app of DunnSense revolves around the idea that users are able to log transactions that have taken place with associated moods and timestamps. These inputs will then be visualised in emotional spending patterns based on machine learning algorithms with increasing financial well-being with real-life nudges based on history of transactions. Within the app, it will also be possible to see potential future spending patterns and mood predictions based in the inputted history, where the app will prepare for a future where mood-based financial recommendations will be prompted. 

Currently, the backend handles the data ingestion and Machine Learning Modelling (ML) while the frontend (build in FlutterFlow) is in place for UI/UX demonstration and app creation. The API connection has not yet been implemented due to software skills limitation (of myself) but the API connection is a plannend enhancement. 

**So what includes the tech stacks & features?**
**- Frontend (Prototype via Flutterflow)**
See the following link to view app within FLutterflow: https://app.flutterflow.io/project/dunn-sense-m-v-p-7zyqgt

The frontend of the app provies a clean UI/UX for user interaction, combined with UX. The input is gathered and is used for logging transactions and moods, while visual placeholders are included for emotion analytics and recommendations. Here, ideally, the app also provides the nudges after the input of a transaction, but will also be futher included in the growth strategy of this business.

**- Backend (Working MVP)**
Python has been used to code the backend side of DunnSense (within Jupiter notebook) where the Machine Learning for emotion-based financial insights was also placed.

Faker was used to create synthetic transaction and mood data generation of a potential user of the previous year. This was required in order to create the ML models and test the potential predictions and nudges the model creates. The syntehic data was generated with the "Faker" library of Python, which included transaction amounts, mood tages (e.g. Happy, Stressed, Neutral), and with timestamps. This information was saved as a CSV file due to convenience, and has been added within this repository for acces. With the models including:
1. ARIMA: mood forecasting
2. Random forest: mood classification
3. Isolation forest: anomaly detection
4. random forest (probalistic): impulse risk scoring
After this visualisations from plotly the outputs include nudges, insights and CSV logs.

REST APIs need to be developed and documented, while also needed to be connected to the frontend side of this MVP. Again due to skills limitations, this was not possible. 

**The big question of course is, how does the app work? And what code currently runs and how?**
**Frontend**
The frontend of DunnSense is built using FlutterFlow, providing an intuitive and emotionally-aware user journey from onboarding to behavior-aware insights. Below is a breakdwon of the user interface per page (here, page represent the individual pages the user go through during their User Experience (UX)) and how the app currenlty works:

Loging and onboarding (page: login)
On first launch, the user lands on the authentication screen. Here options include, create a new account via email + password + confirmation, continue seamlessly with Google sign-in, and existing users can log in directly. This ensures a secure and scalable onboarding process.

Home screen (page: initial)
After logging in, users arrive on the home dashboard, which displays:
1. Current financial snapshot: total expenses this month, remaining balance, total income logged
2. Latest transaction with amount, data and mood associated.
Here users can log a new transaction or navigate to key insigths from this central screen.

Log a new transaction (Page: createExpense)
Here users can add a new expense or invoice. The required fields that need to be field in are:
1. transaction category (e.g., groceries, shopping)
2. transaction amount
3. mood at the time of spending (e.g. happy, stressed)
4. data of transaction (selected todat or input manually)
& submit via "add new" to save entry
Upon saving, an instant nudge is shown, based on the mood-category patterns detected (from rule-based logic or ML models)

Edit logged transaction (Page: editExpensve)
From the home screen, users can selected a previously logged transaction. Fields can be updated and resaved for accuracy. This supports reflective behavior tracking over time.

View mood & spending stats (Page: report)
Presents a summary of moods and realted transactions, including mood identifiers, expense totals, insights at-a-glance. Users can click tpo view more detailed analytics in the dashboard.

Mood-spend dashboard (Page: dashboarding)
This page displays a 30-day mood tracking graph (based on past inputs) with spendings patterns aligned with moods. This includes predictive nudging insights and with a quick add (+) button allowing users to log a new transaction directly from here. 

Account settings (Page: settings)
Here users can update personal preference, modify language selection, and amange account information

Search Your History (Page: search function)
Users can search past transactions by mood, transaction category, amount, date or keyword which enables quick access to historical data and suppors behavior reflection.

Nudging logic is divided into two sections:
1. immediate nudges: appear after each transaciton is logged (via rule-based logic)
2. Predictive nudges appear across the app at contextually relevant moments (e.g. daily summaries, high risk days), informed by backend ML models (e.g., impulse risk score anomaly detection). 

Summary of workflow:
The frontend UI/UX guides the user through a complete emotional-financial loop: logging --> reflection --> insight --> prediction --> adjustment. Where each page supports personal agency and behavior coaching, ensuring a smooth bridge to backend analytics and nudging engine.

**Backend**
The code is developed in the language of Python and was implemented via a notebook in the software Jupiter. The code is devided within clear steps.

Step 1: introduction
Introduces the app's purpose: helping users understand how their mood influences their spending and offering behaviorally intelligent nudges

Step 2: installs and loads essential python packages required to make the MVP run, including ipywidgets, pandas, plotly, statsmodels, sklearn. This ensures interactive inputs and ML capabilities work, all used for itneractive user input, data handling and visualisation.

Step 3: Mood & Transaction logging
Allows users to manually log transactions with values of mood, amount, spending category and timestamps. This is supported via the imported simulated data from _simulated_transactions.csv.

Step 4: Nudge engine
This code provides the foundation of a rule-based system that create real-time behavioral nudges based on users mood and category defined in the inputted transaction. For example: emotional spending; suggesting taking a walk! Or: happy + saving --> reinforces positive behavior. 

Step 5: Dashboarding and visual analytics
Presents dashboarding and generated dyanmic visualisations based on the inputted transactions and transaction history of the users. Still pretty basic but represents: average spend per mood and mood-linked spending trends over time. It saves all logs to _dunnsense_history.csv and prinst a session summary with total entires, total spent, and most common mood.

Step 6: Machine learning modelling & predictive algorithms
Model 1: Mood forecasting with ARIMA
This model represent and applies time-series modeling to forecast mood scores over the upcomg 7 days. It returns both numerical forecast and interpretive nudges to users, allowing them to think about their spending and emotional state.

Model 2: Mood Classification (Random Forest)
This model uses supervised learning to predict mood class (defined as low, neutral and high) based on essential vs. non-essential spending and total spending per day. The output is a classification report and personalized nudges based on the predictions of mood classification. This report also showcases the metrics on how to measure the efficiency, robustness and overall fit of the model.

Model 3: Anomaly detection (Isolation Forest)
This model detect days with unusual spenidng patterns, and it flags anomalies with contextual nudges. This allows users to see an indication on how and when they are likely to overspend due to emotional state.

Model 4: Impulse Risk score (Random Forest)
This model builds a personalized risk profile based on the day of the week, rolling spending patterns and the days since last transaction. Based on these variables, it predict impulse spending risk using another Random Forest model and adds nudges like "high risk today

**How to run the notebook?**
1. Clone or download the repository
2. Install Jupyter notebook (if needed):
pip install notebook

3. install required libraries (once)
pip install ipywidgets pandas plotly statsmodels scikit-learn

4. run the notebook
jypter notebook (within terminal), then open the notebook file (DunnSense_MVP and attached to this repository) and running the cells in order as displayed (Shift+Enter).

**Small notes for users:**
The backend size of the app runs entirely in Jupyter Notebook, which is ideal for the demo and prototyping. No database or API connection is currently required for the MVP since the data is all simulated using faker or manual input. 

**Looking forward (and vision ahead/ current vs planned features)**
While the current MVP esthablises the technical backbone and user experience, there is currently a lack of full integration and this aspect is therefore viewed as a strategic growth opportunity. Hence, the following plan includes the steps and vision DunnSense sees for itself:
1. Hiring software engineers to integrate frontend with working backend APIs
2. Scaling ML engine to incorporate real financial data
3. Building ethical, privacy-first infrastructure to responsible handle emotional and financial data.

#fintech #ai #emotionaware #flutterflow # ml #personalfinance #python
