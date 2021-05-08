# ETL-Project
Group members: Andrew Thao, Callum Linnegan, Mehrdad Maleki

# Data Source: (Extraction)
The dataset used for our ETL project is available on Kaggle.com, it is a daily record of the top trending YouTube videos.

https://www.kaggle.com/datasnaek/youtube-new?select=RU_category_id.json

The dataset includes serveral months of data on daily trending YouTube videos. To determine the year's top-trending videos, YouTube uses a combination of factors including measuring users interactions (total number of views, shares, coments and likes). Data is included for the US, GB, DE, CA, FR, RU, MX, KR, JP and IN regions (USA, Great Britian, Germany, Canada, France, Russia, Mexico, South Korea, Japan and India, respectively) with up to 200 listed trending videos per day. 
Each region's data is in a separate file, which includes the video title, channel title, publish time, tags, views, likes and dislikes, description, and comment count.
The data also includes a category_id fieldm which varies between regions. To retreive the categories for a specific video, it can be found in the associated JSON. Each country has a specific json file within the dataset.

# Transformation:
With the dataset provided we decided to analyse three different regions, CA (Canada), US (USA) and GB (Great Britian). From each region we cleaned up the dataset/dataframe by choosing the columns which were relevant. After grabbing the relevant columns we then used the associated JSON file to help us map the category id with a category name for each region. We then created a combined dataframe of all three regions called 'final_df', which combined all three CSV files.

# Load:
We decided to load the extracted and transformed data onto MongoDB (non-relational database). Since the dataset would be combining data from different regions and being a large dataset it will allow us to accommdate for the difference in types/structure of data if there is any. Also it will allow us to add data in the future if it was ever needed. 
