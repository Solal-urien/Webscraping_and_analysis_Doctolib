# Analysis of medical desertification

## Research question
The last few years have highlighted an acute shortage of doctors throughout France,
especially in certain (often rural) areas that can truly be described as "medical deserts". The
problem affects both general and specialist medicine (ophthalmologists...).
This project is an opportunity to collect online data to reveal the presence of these medical
deserts on multiple socio-economic levels , and observe socio-economical tendencies
such as heliotropism or coastalization.

## Methodology
To answer the question, we first collected data from the Doctolib medical platform using the webscraping tool "BeautifulSoup", and
subsequently analysed the data. During this second part, we used some INSEE datasets in
order to obtain relevant socio-economic information. We then brought together the
information to analyse the link between the aforementioned data and the distribution of
doctors throughout France, by computing a linear regression model between the number of
doctors per inhabitant and the socio-economic covariates.

## Data collection
We used an online database providing the name of french towns and population, and
selected the commune having more than 30,000 inhabitants. Indeed, the Doctolib website
has the advantage of proposing results in an area around the selected city. Therefore, a
significant number of municipalities uniformly distributed over France was enough to span
the entire territory and allow collecting all the needed information. The data were collected on January 4 th , 2023. They were subsequently stored in
.csv documents.
The collection of our data was particularly complex. Indeed, repeated requests to the
Doctolib website provoked a ban of the IP address from accessing the website via a bot (403
and 429 HTTP errors). To solve this issue, we used a VPN. However, this solution
particularly slowed down the data collection. Another problem we faced during the data
collection was the format of the HTML code: we had to build our own data processing
algorithm, as none of the implemented libraries was able to correctly collect the information
we needed.
Subsequently to the difficult data collection, we found ourselves in possession of around 27k
entries that we had to clean, leaving about 16k entries after deleting the duplicates and
irrelevant data. We were fully satisfied with this number, as the Doctolib platform was
especially hard to scrape, and even implemented an anti-scraping mechanism recently,
which made the collection even harder.
