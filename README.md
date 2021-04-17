# GPU Web Scrapper PoC:
By globoglobito.

The aim of this little project is to create a tool to allow me to catch a GPU (specifically a RTX-3090) at MSRP.
(My trusty Radeon Fury X is growing long in the tooth)

For some context, 2021 is proving to be a year affected my semi-conductor shortages thanks to Covid. Moreover with the current Cryptocurrency boom, GPUs are extremely scarce since they are all hoarded by mining farms or bought by scalpers with the help of bots.

Therefore in a way to combat fire with fire (I refuse to pay the prices asked by scalpers), and as a way to brush up my python skills, I created this simple data pipeline.

### Base idea:

![Image of Scrapper](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/webscapper.JPG)

## The plan is:

#### 1) The webscapper runs every 30 mins and extracts the relevant information from 11 webpages.
    - If a GPU is found @ MSRP, it sends me an email with the URL.




#### 2) Once its done, it dumps the information into a PostgresDB table that is running in a docker container.

![Image of Grafana](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/Postgres_screenshot.png)
<font size="2">The aforementioned table</font>

#### 3) Finally, I have a grafana container that uses this information to vizualise the data into a simple dashboard. 

![Image of Grafana](https://github.com/globoglobito/WebScrapperPOC/blob/main/images/Grafana_screenshot.png)
<font size="2">Current version of the dashboard.</font>

## FAQ:

#### Why only 11 links?
Because my current setup is borderline small form factor, and only blower-style GPUs and the EVGA XC3 line fits. Also I did not include Amazon links because I'm not bothering to compete with other tools (CamelCamelCamel) or other bots (a listing went down in 49 secs since i got notified).
(Feel free to add more if you want)

#### Why you scrape every 30 mins?
Multiple reasons: If I try to scrape constantly I could trigger an anti-bot meassure and I would fill my database pretty quickly since its running in a minuscule SSD.


#### Can I use your script?
Sure go nuts.


#### Why did you did 'xyz thing' that way?
Because it's the first time I've done something like this. If you have a suggestion, feel free to share it.

