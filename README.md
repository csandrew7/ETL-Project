# ETL Project Report:
Group members: Andrew Thao, Callum Linnegan, Mehrdad Maleki

# Data Source: (Extraction)
The dataset used for our ETL project is available on Kaggle.com, it is a daily record of the top trending YouTube videos.

https://www.kaggle.com/datasnaek/youtube-new?select=RU_category_id.json

The dataset includes serveral months of data on daily trending YouTube videos. To determine the year's top-trending videos, YouTube uses a combination of factors including measuring users interactions (total number of views, shares, coments and likes). Data is included for the US, GB, DE, CA, FR, RU, MX, KR, JP and IN regions (USA, Great Britian, Germany, Canada, France, Russia, Mexico, South Korea, Japan and India, respectively) with up to 200 listed trending videos per day. 
Each region's data is in a separate CSV file, which includes the video title, channel title, publish time, tags, views, likes and dislikes, description, and comment count.
The dataset also includes a category_id field which varies between regions, the specific category name can be found in the associated JSON file included within the dataset.

# Transformation:
With the dataset provided we decided to analyse three different regions, CA (Canada), US (USA) and GB (Great Britian). From each region we cleaned up the dataset/dataframe by choosing the columns which were relevant to our analysis. Those columns were video id, title, channel title, category id, views, likes, dislikes and comment_count. After grabbing the relevant columns we then used the associated JSON file to help us map the category id with a category name for each region. We then decided to breakdown each regions trending videos into further tables. These were top 10 trending videos, highest likes, highest comment count and how many videos fall into each category. Finally we created a combined dataframe of all three regions called 'final_df', which combined all three CSV files. These dateframe was then used to load onto our preferred database.

# Load:
We decided to load the extracted and transformed data onto postgreSQL (relational database). Since the dataset that we would be loading has been structured and organised into tables and categories by us we thought that postgreSQL would accompy our needs as relational databases works best with data that is easily structured into categories we have made our data consistent in input, meaning, and easy to navigate and lastly there are relationships that can be easily defined between data points.
