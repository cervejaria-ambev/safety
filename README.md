<div align="center">
  <img src="https://pictshare.net/y3kkqa.png">
</div>

-----------------
# Safety Algorithm

## Who we are

We’re building a company to last, brewing beer and building brands that will continue to bring people together for the next 100 years and beyond. With centuries of brewing history, we’ve seen countless new friendships, connections and experiences built on a shared love of beer.

[Click to read About Ambev](https://www.ambev.com.br/sobre/)

[Click to read About AB-Inbev](https://www.ab-inbev.com/who-we-are.html)

## The project

Safety Algorithm is an AI approach developed by Ambev to have a safer environment and avoid incidents on our plants.
We hope you copy, use and evolve it. Help us to make the world a better place and reach our dream:

> **Bringing People Together for a Better World

The main goal for the project is predict unsafe conditions that could lead to an accident, called TRI - Total Recordable Injuriues, and help breweries to have visibility if any accident is going to happen soon.. As much important as the prediction, the next steps are a big part of the ecosystem. What to do with the information and what action need to be taken is crucial to apply to the field. So, below is a basic diagram regarding the strategy delpoyed:

<div align="center">
  <img src="https://pictshare.net/z8is6s.png">
</div>

Where:

#### 1) Databse
- Data from different sources are used, such as:
  - People
  - Brewery Infos
  - Accidents and occurrences
  - Environment Data
#### 2) Artificial Intelligence
- Algorithm to predict accidents
#### 3) Dashboard
- Analytic Dashbaord in order to deliver visibility to business
#### 4) Alerts
- Coefficient analysis
#### 5) Identify
- After alert is received, it is necessary to check safety procedures on site.
#### 6) Classify
- The issue is classified 
#### 7) Action
- Actionis taken after analysis
#### 8) Check
- Evaluate

Ideally after steps above, all info gathered from steps 5 to 8, by procedure, has to be insert to a system. This system is a source for the algorithm, so the system has this feedback in order to evaluate if it was a good / bad prodiction. 

## Importante Notes

:arrow_right: The dataset **DOES NOT** reflect facts. All data was changed with simulated values.

:arrow_right: Algorithm Choice

Through the development process we tried several machine learning algorithms, such as random forest, Support vector clustering (SVC), Artificial neural networks (ANN). The best fit for our model according all data we used was the XPTO.

Please, fell free to use all options according your dataset.

For reference, please read the following:

[Scikit Python Library](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning)

## Contribuitors

:beer: Brayan Crispiano Ksenhuck

:beer: Cassio Oliveira Medeiros

:beer: Fabricio Oliveira Bezerra

:beer: Leonardo Gonçalves Rigueto

:beer: Mario Vieira 

:beer: Renata Cristina Gutierres Castanha

:beer: Thiago Lechuga

## Algorithm Features

- [x] 1) Feature engineering

- [x] 2) Train Test Split

- [x] 3) Removing constant features

- [x] 4) Removing quasi constant features

- [x] 5) Removing correlated features

- [x] 6) Removing features using univariate roc_auc

- [x] 7) Log to Email

## Requirements

## How to install

## Features Details

### Data Cleasing / Feature Engineering

In order to reach a better model further on the algorithm, the data cleasing process is a necessary step to prepare a dataset where only data that is relevant for the ANSWER that we need as output. Focusing time on analysing the data is crucial. We used a few steps in order to prepare the data and execute the feature engineering, such as: 

- #### Seekin' for missing values

- #### Removing constant features
  - Here the idea is to remove all features which variance doesn’t meet some threshold (in this case, zero)

- #### Removing quasi constant features
  - The code below removes all features which variance does not meet some threshold (in this case, almost 99%)

- #### Recursive Feature Elimination
  - Importance of the features according to the algorithm

### Log to Email

We developed a solution in order to give visibility about the algorithm. Mainly focused when it is schueduled in a daily basis. That way it is possible to get feedback from the algorithm sent to an e-mail, for example, if all steps was done as expected or even the accuracy and recall.
  
The code is under Log_Email folder. We used Gmail as domain, but you can use any domain as desired or even use a local SMTP server. In order to do so, Google requests a pre-work, such as allowing SMTP and connections inside config. The steps can be seen here:

For more information about SMTP and Gmail, please read:

[Allowing SMTP connection with GMAIL](https://support.google.com/a/answer/2956491) 

Though keep in mind that will be required a few changes at the code at least this two steps if the SMTP server is local or from other domain:
  
#### Change the port
```
server = smtplib.SMTP('smtp.gmail.com',587)
```

#### Change authentication credentials (might be necessary to remove according chosen authentication method)
```
user = 'youremail@domain.com'
passwd = 'yourpassword'
server.login(user, passwd)
```
For more information about SMTP on python, please read:

[SMTP Python Documentation](https://docs.python.org/3/library/smtplib.html)

#### Log Details

The log is through a dataframe. We have included one example at first step : Reading Database. 

Change the row number and include the code below as desired steps that you want to get feedback from.

#### Change Code

```
try: 
  dataset = pd.read_csv('modelo_unidade_diario_comentado.csv', encoding='ISO-8859-1', sep=';')
  df.iloc[0, df.columns.get_loc('Data')] = datetime.datetime.now().strftime("%d/%m/%y - %H:%M:%S")
  df.iloc[0, df.columns.get_loc('Status')] = 'SUCESSO'
  df.iloc[0, df.columns.get_loc('Comment')] = 'Import dos Dados com SUCESSO'
  validador_log()
  
except:
  df.iloc[0, df.columns.get_loc('Data')] = datetime.datetime.now().strftime("%d/%m/%y - %H:%M")
  df.iloc[0, df.columns.get_loc('Status')] = 'FALHA'
  df.iloc[0, df.columns.get_loc('Comment')] = 'Import dos Dados com FALHA'
  validador_log()
```
Make sure to add the feedback from algorithm as needed as example above.

The actual log send by email is similar as shown below:
  
<div align="center">
  <img src="https://pictshare.net/goynzm.png">
</div>

## Next Steps

- [ ] Finish my changes

- [ ] Push my commits to GitHub

- [ ] Open a pull request

## License

[MIT License](LICENSE)
