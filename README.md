# Analysis-Comedy-channels-in-youtube-

## Part I : Collect data by channel id
If you don't know how to get channel id. This is a solution: `https://www.youtube.com/watch?v=D12v4rTtiYM&t=68s`.

I use youtube api to collect data about 5 famous comedy channels in Viet Nam. These are: 
  1. Dong Tay Promotion
  2. Vie Channel
  3. FapTV
  4. VTV GiaiTri
  5. Dien Quan Comedy

You can see in detail data in Data Folder: 
  1. `category_video.csv`: 
      - I read source from html-parse and extract it to csv file
      - This file has 2 columns: 
          - CategoryId : is similar category id of video when you use youtube api
          - Category : is main aspect of video in life.
  2. `channels.csv`:
      - Some statistical of channels
  3. `video_ids.csv`: 
      - The id of video for each channel
  4. `information_video.csv`:
      - The information of video as well as : duriation, published time, views, likes,....
  5. `artists.txt`:
      - List of Vietnamese artists is provided by Wikipedia.
  6. `tokenize.png`:
      - The runtime is quite long so I paste that image for you to evaluate the result.

Detail on collecting data, I present in detail source code into notebook file. You also see data via `MongoDB Compass`, I made an small demo to import data up to MongoDB Cloud. But I hid my hostname, username and password. Please contact me to get these informations.
  
## Part II: Preprocessing data.

1. Date Time:
    - publishedTime is `ISO 8861` format, I use `dateutil` package to convert to datetime64[ns] format
    - Duration is `ISO 8601 duration`, I use `isodate` package to convert to timedelta64[s] format
2. Tags:
    - Although we see values in Tags columns is similar array, it actually string. So I convert raw string (step by step) to array :((
    - After that, we calculate the number of tags and save in `tagCount` column
3. Catogries of video:
    - Using `category.csv` and merge 2 DataFrame on `CategoryId` 
4. People get involved in video:
    - I using Descriptions and Titles to find artists who take part in this video.
    - It's so difficult to identify all of artists. I use `pyvi` package which is NLP package supporting for `Vietnamese` and the `artists.txt` file.
  
