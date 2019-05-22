<div align="center">
  <img src="https://pictshare.net/y3kkqa.png">
</div>

-----------------
# Safety Algorithm

## The project

Safety Algorithm is an AI approach developed by Ambev to have a safer environment and evoid incidents on our plants.
We hope you copy, use and evolve it. Help us to make the world a better place and reach our dream:

#### *Bringing People Together for a Better World*

## Who we are

We’re building a company to last, brewing beer and building brands that will continue to bring people together for the next 100 years and beyond. With centuries of brewing history, we’ve seen countless new friendships, connections and experiences built on a shared love of beer.

[Click to read About Ambev](https://www.ambev.com.br/sobre/)

[Click to read Who we are](https://www.ab-inbev.com/who-we-are.html)
  
## Contribuitors

:beer: Brayan Crispiano Ksenhuck

:beer: Cassio Oliveira Medeiros

:beer: Fabricio Oliveira Bezerra

:beer: Leonardo Gonçalves Rigueto

:beer: Mario Vieira 

:beer: Renata Cristina Gutierres Castanha

:beer: Thiago Lechuga

## Features

- [x] 1) Feature engineering

- [x] 2) Train Test Split

- [x] 3) Removing constant features

- [x] 4) Removing quasi constant features

- [x] 5) Removing correlated features

- [x] 6) Removing features using univariate roc_auc

- [x] 7) Log send to Email

## Next Steps

- [ ] Finish my changes

- [ ] Push my commits to GitHub

- [ ] Open a pull request

## Features Details

### 1) Feature engineering
- Categorical features
- Number of each different categorical category
- Missing values 
  Seekin' for missing values

### 2) Train Test Split

### 3) Removing constant features

### 4) Removing quasi constant features

### 5) Removing correlated features

### 6) Removing features using univariate roc_auc

### 7) Log send to Email

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

## License

[MIT License](LICENSE)
