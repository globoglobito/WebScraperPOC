# GPU Web Scrapper PoC:

> By globoglobito

The aim of this fun little project is to create a tool to allow me to catch a GPU (specifically a Nvidia RTX 3090) at MSRP.

(My trusty AMD Radeon Fury X is growing long in the tooth)

To provide some context it is 2021, and there is a widespread semi-conductor shortage. This shortage is partly caused by the COVID-19 pandemic; partly by the cryptocurrency mining boom. As such, GPUs are extremely scarce; either hoarded by mining farms, or bought by scalpers with the help of bots.

Therefore, I built this data pipeline as a way to combat fire with fire (given that I refuse to pay the current prices), and to brush up my python skills.

### Base idea:

![Image of Scrapper](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/webscapper.JPG)

## The plan is:

#### 1) The web scrapper runs every 30 mins; extracting the relevant information from 11 webpages.
    - If a GPU is found @ MSRP, it sends me an email with the URL.


#### 2) Once its done, it dumps the information into a PostgresDB table that is running in a docker container.

![Image of Grafana](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/Postgres_screenshot.png)
<font size="1">The aforementioned table</font>

#### 3) Finally, I have a Grafana container that uses this information to visualise the data in a simple dashboard. 

![Image of Grafana](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/Grafana_screenshot.png)
<font size="1">Current version of the dashboard.</font>

## FAQ:

#### Why are you only scrapping 11 links?
Because my current setup is borderline small form factor. Meaning only blower-style GPUs, and the EVGA XC3 line fits. Furthermore, I did not include Amazon links because I am not bothering to compete with other tools (like CamelCamelCamel), and frankly the competition against other scalpers is downright silly (a listing went down in 49 secs after I got notified of an available GPU).
(Feel free to add more if you want)

#### Why are you only scrapping data every 30 mins?
Multiple reasons: By scrapping in a smaller timeframe I could pottentially trigger an anti-bot measures, such as getting my IP temporarily blocked. Moreover, I would fill my database pretty quickly, given it is running inside a minuscule SSD.


#### Can I use your script?
Sure, go nuts.


#### Why did you do 'xyz thing' that way?
Because this is the first time I've done something like this. If you have a suggestion, feel free to share it.

