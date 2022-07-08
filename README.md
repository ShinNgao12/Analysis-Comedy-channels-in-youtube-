# Analysis-Comedy-channels-in-youtube-

## Part I : Collect Data by channel id
If you don't know how to get channel id. This is a solution: https://www.youtube.com/watch?v=D12v4rTtiYM&t=68s.

I use youtube api to collect data about 5 famous comedy channels in Viet Nam. These are: 
  1. Đông tây promotion
  2. Vie Channel
  3. FapTV
  4. VTV GiaiTri
  5. Dien Quan Comedy

You can see in detail data in Data Folder: 
  1. category_video.csv: 
      - I read source from html-parse and extract it to csv file
      - This file has 2 columns: 
          - CategoryId : is similar category id of video when you use youtube api
          - Category : is main aspect of video in life.
  2. channels.csv:
      - Some statistical of channels
  3. video_ids.csv: 
      - The id of video for each channel
  4. information_video.csv:
      - The information of video as well as : duriation, published time, views, likes,....
Detail on source code, I present in detail into notebook. You also see via MongoDB Compass, I made an small demo to import data up to MongoDB Cloud. But I hiden my hostname, username and password. Please contact me to get these informations.
  
  ## Part II: Preprocessing data.
  
  
