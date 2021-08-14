# Vacation Rental Recommender - TripAdvisor

The project is an original end-to-end project originated by the author. Vacation rentals are popular for weekend vacations in Canada. Most of the booking for these rentals are done on booking sites and the consumers depend on these booking sites for recommendation of vacation rentals that suits their needs. The accuracy of these recommendation engines built into rental sites will determine if a consumer gets a desired vacation rental. In this case study, we use a popular booking site 'TripAdvisor' to build a recommendation engine for vacation rentals in Canada. Dataset of customer reviews serves as the training dataset, and using Natural language Processing algorithms, these reviews are used to build a recommender engine. We applied Deep learning and classification modeling to improve the accuracy of our Recommender system.

To obtain original data to be used for building the recommender system, I scraped the website [www.tripadvisor.ca](http://www.tripadvisor.ca/) with the search keyword as ‘Vacation Rentals’ on the 10th of September 2019. The search yielded about 870 results. The results were then scraped from the website using selenium and python package. The contents scraped from the website for each rental included **Title, Price, Rating, Reviews, Review URL, Location.** The contents obtained from the web search was dependent on the date. However, we believe that this search represents to a higher degree the vacation rentals currently available in Canada. This informs the choice of using TripAdvisor as the booking website of choice for the data, since it has been highly rated as one of the best booking websites. Moreover, the purpose of the whole study is to build a recommender system, which I believe the modelling can be applied to any dataset.

## Project structure
```
.
├── app
│   ├── app.py                                  # streamlit app file
│   ├── deploy                                  # code to deploy the app on google cloud
│   │   ├── app.py
│   │   ├── app.yml
│   │   ├── Dockerfile
│   │   ├── Pipfile
│   │   ├── README.md
│   │   └── requirements.txt
│   └── run.sh
├── code
│   ├── app.py
│   ├── __init__.py
│   └── scraping.py                             # script to scrap the data from tripadvisor.ca site
├── data
│   ├── bronze
│   │   └── reviews.csv                         # scraped data with user reviews and ratings
│   └── silver
│       └── reviews.parquet.gzip                # preprocessed dataset
├── docs
├── LICENSE
├── models
├── notebooks
│   ├── reco-tut-vrr-01-data-ingestion.ipynb    # data ingestion and EDA notebook
│   ├── reco-tut-vrr-02-predictions.ipynb       # keras model to predict ratings from reviews
│   └── reco-tut-vrr-02-recommendations.ipynb   # recommender model based on ratings and/or reviews
├── README.md
├── requirements.txt
└── setup.py
```