# DunnSense-MVP
DunnSense - Your Mood-Based Financial Coach

Welcome to DunnSense! A FinTech app that bridges emotional intelligence and financial literacy. The mission of DunnSense is to empower users to understand how their spending behaviors are influenced by their emotional states, using Ai-driven insights and personal analytics. 

The app of DunnSense revolves around the idea that users are able to log transactions that have taken place with associated moods and timestamps. These inputs will then be visualised in emotional spending patterns based on machine learning algorithms with increasing financial well-being with real-life nudges based on history of transactions. Within the app, it will also be possible to see potential future spending patterns and mood predictions based in the inputted history, where the app will prepare for a future where mood-based financial recommendations will be prompted. 

Currently, the backend handles the data ingestion and Machine Learning Modelling (ML) while the frontend (build in FlutterFlow) is in place for UI/UX demonstration and app creation. The API connection has not yet been implemented due to software skills limitation (of myself) but the API connection is a plannend enhancement. 

**So what includes the tech stacks & features?**
**- Backend (Working MVP)**
Python has been used to code the backend side of DunnSense (within Jupiter notebook) where the Machine Learning for emotion-based financial insights was also placed.

Faker was used to create synthetic transaction and mood data generation of a potential user of the previous year. This was required in order to create the ML models and test the potential predictions and nudges the model creates. The syntehic data was generated with the "Faker" library of Python, which included transaction amounts, mood tages (e.g. Happy, Stressed, Neutral), and with timestamps. This information was saved as a CSV file due to convenience, and has been added within this repository for acces. 

REST APIs need to be developed and documented, while also needed to be connected to the frontend side of this MVP. Again due to skills limitations, this was not possible. 

**- Frontend (Prototype via Flutterflow)**
See the following link to view app within FLutterflow: https://app.flutterflow.io/project/dunn-sense-m-v-p-7zyqgt

The frontend of the app provies a clean UI for user interaction, combined with UX. The input is gathered are used for logging transactions and moods, while visual placeholders are included for emotion analytics and recommendations. Here, ideally, the app also provides the nudges after the input of a transaction, but will also be futher included in the growth strategy of this business. 

**The big question of course is, how does the app work? And what code currently runs and how?
Frontend:**




****Backend: ****
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

How to run the notebook: 
1. Clone or download the repository
2. Install Jupyter notebook (if needed):
pip install notebook

3. install required libraries (once)
pip install ipywidgets pandas plotly statsmodels scikit-learn

4. run the notebook
jypter notebook (within terminal), then open the notebook file (DunnSense_MVP and attached to this repository) and running the cells in order as displayed (Shift+Enter).

**Small notes for users:
**
The backend size of the app runs entirely in Jupyter Notebook, which is ideal for the demo and prototyping. No database or API connection is required for the MVP since the data is all simulated using faker or manual input. 

**Looking forward (and vision ahead/ current vs planned features)
**
While the current MVP esthablises the technical backbone and user experience, there is currently a lack of full integration and this aspect is therefore viewed as a strategic growth opportunity. Hence, the following plan includes the steps and vision DunnSense sees for itself:
1. Hiring software engineers to integrate frontend with working backend APIs
2. Scaling ML engine to incorporate real financial data
3. Building ethical, privacy-first infrastructure to responsible handle emotional and financial data.

#fintech #ai #emotionaware #flutterflow # ml #personalfinance #python
