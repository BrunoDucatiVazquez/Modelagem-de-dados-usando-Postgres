
# Projeto Engenharia de dados

## **Cenário**
Neste projeto, foi aplicado Modelagem de Dados com Postgres e foi construido um pipeline ETL usando Python. Uma startup quer analisar os dados coletados sobre músicas e atividades do usuário em seu novo aplicativo de streaming de música. Atualmente, eles estão coletando dados no formato json e a equipe de análise está particularmente interessada em entender quais músicas os usuários estão ouvindo.


## **Base de dados das musicas**
O conjunto de dados de músicas é um subconjunto de [Million Song Dataset](http://millionsongdataset.com/).

Registro de Amostra :
```
{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}
```

## **registros da base de dados**
O conjunto de dados de registros é gerado por [Event Simulator](https://github.com/Interana/eventsim).

Sample Record :
```
{"artist": null, "auth": "Logged In", "firstName": "Walter", "gender": "M", "itemInSession": 0, "lastName": "Frye", "length": null, "level": "free", "location": "San Francisco-Oakland-Hayward, CA", "method": "GET","page": "Home", "registration": 1540919166796.0, "sessionId": 38, "song": null, "status": 200, "ts": 1541105830796, "userAgent": "\"Mozilla\/5.0 (Macintosh; Intel Mac OS X 10_9_4) AppleWebKit\/537.36 (KHTML, like Gecko) Chrome\/36.0.1985.143 Safari\/537.36\"", "userId": "39"}
```


## Schema

#### Fact Table 
**songplays** - registros em dados de log associados a reproduções de músicas, ou seja, registros com a página `NextSong`

```
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
```

#### tabelas
**users**  - usuarios
```
user_id, first_name, last_name, gender, level
```
**songs**  - musicas 
```
song_id, title, artist_id, year, duration
```
**artists**  - artista 
```
artist_id, name, location, latitude, longitude
```
**time**  - tempo em timestamp
```
start_time, hour, day, week, month, year, weekday
```



