---
layout: post
title:  "Testing the Li Keqiang Index: Project Introduction and EDA"
author: William Martindale
description: Introducing my Li Keqiang Index project.
image: /assets/images/blog-image.jpg
---

# Introduction

Li Keqiang was the former premier of the People's Republic of China. He was seen by many in the West as a moderate in the Chinese Communist Party; compared to Xi Jinping, Li was more friendly to the West and more open to liberal economics. He was widely expected to be a major candidate to succeed Hu Jintao as paramount leader in 2012.
However, he fell from grace, in large part due to a diplomatic cable stolen and leaked by Wikileaks in 2010. In this document, an ambassador claims to have been told by Li Keqiang that the GDP figures in Li's province of Liaoning were unreliable. Instead, Li said that he used three other indicators: the railway cargo volume, electricity consumption and loans disbursed by banks.
This was widely reported at the time, most famously by [The Economist](https://www.economist.com/asia/2010/12/09/keqiang-ker-ching). Li died in October 2023 after being ousted from power in the 20th National Congress of the Chinese Communist Party and was replaced as premier by the similarly-named Li Qiang.

<p align="center">
  <img src="https://github.com/WiJaMa/wijama.github.io/assets/73615879/48417fb0-10c6-4209-a787-41d48fa397bc">
  <p align="center"><em>Li Keqiang in 2019</em> <a href="https://commons.wikimedia.org/wiki/File:Shinz%C5%8D_Abe_Li_Keqiang_20191225_(1)_(cropped).jpg">Image Source</a></p> 
</p>

# Project

I wanted to see whether this index was actually a good reflection of modern economies. Two of the indicators are strongly connected with industrial development but not the modern service-oriented economy, while the other, volume of bank loans, is difficult to quantify. I was also curious whether the effectiveness of the indicator would vary with level of democracy.
The measurement of democracy is, of course, a widely contested field. The two most famous indices dedicated to measuring democracy are the Economist Democracy Index and the V-Dem Democracy Indices. The latter are plural because V-Dem (or, the Varieties of Democracy Institute) developed multiple indices to measure different types of democracy: electoral, liberal, participatory, deliberative, and egalitarian. For simplicity, I chose to use the Economist Democracy Index.

For control variables, I also included in my analysis the percentage of the economy made of services and the percentage of the population that was urban. I anticipated that these would have some effect on how, accurate the Li Keqiang index would be.

All of the variables included were used in their total, rather than per capita form. This is because Li Keqiang seemed to have been interested in total economic output of his province rather than per capita output. While this means there are likely to be outliers (in the form of the US and China, by far the world's largest economy), it is a more accurate reflection of his index.

Because the Economist Democracy Index only includes the years 2006, 2008, and 2010-2022, those were the only years included in the analysis. This is where the V-Dem indices would likely have been more useful; they evaluate countries as far back as the year 1900. The data on the other indicators only ran as far forward as 2020, so the years used were 2006-2020.

Ultimately, I was not able to find data on the volume of bank loans in China. This was a major weakness of my analysis.

# Gathering Data

## World Bank Data
The World Bank maintains a large database that includes data on a wide variety of economic indicators for every country in the world. Not every indicator is available in every year in every country, but it is extraoridinarily useful. The World Bank Databank can be accessed [here](https://databank.worldbank.org/source/world-development-indicators/). 

The database can be accessed using standard API calls as well. To do this, you will need to know the code for the indicators you want to use. This can be foudn at the end of the URL when you are accessing an indicator in the World Bank Databank:
![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/9a7053a3-6700-4adc-974e-8da94fe73e50)


Accessing the raw JSON is relatively simple. First, import requests:
```python
import requests
```
It's easiest to have an indicator variable that can be changed so that you can run the same code with different indicators. The following code generates a URL for you based on the indicator you want to use. [The indicator used here](https://databank.worldbank.org/source/world-development-indicators/Series/IS.RRS.GOOD.MT.K6) is goods transported by railways, measured in ton-kilometers:
```python
indicator = 'IS.RRS.GOOD.MT.K6'
url = f'https://api.worldbank.org/v2/sources/57/country/all/series/{indicator}/time/all/data?format=json'
```
Next, simply send a get request to that URL:
```python
response = requests.request("GET", url)

status_code = response.status_code
result = response.text
```

However, cleaning up this data is hard work. Tim Herzog, a data scientist at the World Bank, [has created an API wrapper](https://blogs.worldbank.org/opendata/introducing-wbgapi-new-python-package-accessing-world-bank-data) to make it easier to access World Bank data. This API wrapper, called WBGAPI has much larger capabilities than we really need it for. It can be installed into your environment by running `pip install wbgapi`.  

Once it's installed, import it:
```python
import wbgapi as wb
```
Now that it's imported, using it to query data is as easy as copying and pasting this code, replacing the indicator each time:
```python
indicator = wb.data.DataFrame({indicator}, time=range(2006, 2020), skipBlanks=True, columns='series')
```
You'll want to replace the index on each indicator.
```python
indicator.reset_index(inplace=True)
```
The indicators I got from WBGAPI were [rail cargo volume](https://databank.worldbank.org/source/world-development-indicators/Series/IS.RRS.GOOD.MT.K6), [percent urban](https://databank.worldbank.org/source/world-development-indicators/Series/SP.URB.TOTL.IN.ZS), [percent GDP from services](https://databank.worldbank.org/metadataglossary/world-development-indicators/series/NV.SRV.TOTL.ZS), and [total GDP](https://databank.worldbank.org/source/world-development-indicators/Series/NY.GDP.MKTP.CD). 

## The Democracy Index
The Democracy Index data was scraped right off of Wikipedia. This is the easiest way to access this data and is relatively simple to do because it has been put into a table.
In fact, it can be scraped using Pandas alone. First, import Pandas:
```python
import pandas as pd
```
Next, use pd.read_html() to send a get request to the Wikipedia page on the Economist Democracy Index and save all of the tables on the page:
```python
tables=pd.read_html('https://en.wikipedia.org/wiki/The_Economist_Democracy_Index')
```
We require the table that lists the Democracy Index by country and year. It looks like this:
![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/f0197ac2-3ed2-495d-94f5-f04a1e01b81d)

It is the sixth table on the page, so it can be easily acquired. I dropped a couple unneeded columns at this stage as well:
```python
democracy = tables[5]
democracy.drop(['2022 rank', 'Regime type'], axis = 1, inplace=True)
```
To create a tidy data set that could be merged with our other data, I melted it, keeping Region and Country as ID Vars and combining the Year columns into a single column.
```python
democracy = democracy.melt(id_vars = ['Region', 'Country'], value_name='Democracy Index', var_name='Year')
```
Finally, I reordered it to make it easier to keep track of what I would need to merge later:
```python
democracy = democracy[['Country', 'Year', 'Region', 'Democracy Index']]
```

## Electricity Consumption
The final variable, electrictiy consumption, was downloaded as a CSV from the [US Energy Information Administration](https://www.eia.gov/international/data/world/electricity/electricity-consumption)
This data requred significant cleanup to save just the columns I needed. I also renamed the unnamed Country column so that I could use it later, and melted the file into a tidy dataset with one Year column, like the Democracy Index data set. 
```python
energy_consumption = pd.read_csv('Data/INT-Export-11-16-2023_15-35-19.csv')
energy_consumption.rename(columns = {'Unnamed: 1':'Country'}, inplace=True)
energy_consumption.drop('API', axis=1, inplace=True)
energy_consumption = energy_consumption.iloc[1: , :]
energy_consumption = energy_consumption.melt(id_vars=['Country'], var_name= 'Year', value_name='energy_consumption')
```
Finally, I inserted NAs into cells that had "---" in them (the EIA's placeholder symbol) and dropped the NAs. I also stripped the unneccesary spaces on the countries in the Country field:
```python
energy_consumption.replace(to_replace='--',value=np.nan, inplace=True)
energy_consumption.dropna(inplace=True)
energy_consumption['Country'] = [item.strip() for item in energy_consumption['Country']]
```

## Merging the tables
I couldn't find a way to merge multiple Pandas dataframes together at once, so I merged each of the World Bank dataframes one at a time:
```python
merged_df = pd.merge(railcargo, percent_urban, on = ['economy', 'time'])
merged_df = pd.merge(merged_df, service_percent, on = ['economy', 'time'])
merged_df = pd.merge(merged_df, GDP, on = ['economy', 'time'])
```
In this merged dataframe, I removed the non-numeric text that the World Bank API gave with each year:
```python
merged_df['time'] = [item.strip('YR') for item in merged_df['time']]
```

Then, I merged the Democracy and Energy Consumption dataframes together:
```python
merged_dem_en = pd.merge(democracy, energy_consumption, how = 'inner', on = ['Country','Year'])
```
Now, we had a problem. WBGAPI returns its data by country code rather than by the full country name. Fortunately, it also provides a solution to this: an automatic country coder. The method wb.economy.coder() takes a list of countries and returns their country codes. It's simple enough to give it a Pandas series and get back a column:
```python
merged_dem_en['Code'] = wb.economy.coder(merged_dem_en['Country'])
```
However, there is a bug in the current version with Vietnam, which I had to code seperately:
```python
merged_dem_en['Code'][merged_dem_en['Country'] == 'Vietnam'] = 'VNM'
```

WIth everything prepared, I could merge both data frames together and drop the unneeded columns:
```python
keqiang = pd.merge(merged_dem_en, merged_df, left_on=['Code','Year'], right_on=['economy','time'])
keqiang.drop(columns=['time','economy','Code'], inplace = True)
```
I also renamed the World Bank columns into more human-readable names:
```python
keqiang.rename(columns = {'energy_consumption': 'energy_cons',
                'IS.RRS.GOOD.MT.K6': 'rail_cargo',
                'SP.URB.TOTL.IN.ZS': 'urban_per',
                'NV.SRV.TOTL.ZS': 'service_per',
                'NY.GDP.MKTP.CD': 'GDP'}, 
                inplace=True)
```

Finally, every table I had created was saved so that I wouldn't have to query them again later:
```python
railcargo.to_csv('./Data/railcargo.csv', index = False)
GDP.to_csv('./Data/GDP.csv', index = False)
service_percent.to_csv('./Data/service_percent.csv', index = False)
percent_urban.to_csv('./Data/percent_urban.csv', index = False)
democracy.to_csv('./Data/democracy.csv', index = False)
energy_consumption.to_csv('./Data/energy_consumption.csv', index = False)
keqiang.to_csv('keqiang.csv', index = False)
```

# Exploratory Data Analysis
Most of the exploratory data analysis was performed in Seaborn. This blog post assumes that the reader knows the basics of Seaborn and does not need the Seaborn commands used explained to them.

The rail cargo, electricity consumption, and GDP graphs are extremely right-skewed:

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/1750a560-34b1-4236-a717-348650658598) ![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/42035b33-9553-4024-821f-6decddae6fb1) ![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/bca42fe2-b284-49e3-a406-d6f5797e0af4)

However, they match a normal distribution much better when they are logarithmed:

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/54b9deeb-9f5f-4222-92be-848a966280b2) ![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/ea16c106-f32f-481e-ba40-1e50756c7be0) ![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/b7e97728-21be-47bc-90cc-d0734f598273)


A countplot of data points be region reveals some other concerns:

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/ba311bcc-7b61-4b02-985f-90404f9bd9ee)

Most of the data points are from Europe. In our data wrangling, I implicitly decided to throw out any data point that didn't have every one of the variables I was examining. However, in doing so, I filtered out quite a bit of Latin America, Africa, and Asia. The effect was so great that Latin America only had 12 more data points than North America, a region which consists entirely of two countries, the United States and Canada. This could result in an implicit bias in our data set.

In fact, 42 out of the 93 countries in the data set are missing at least one value. Most of these are in the Middle East and Africa:

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/009eb738-b62c-4fc0-82bb-6c27ec9237ae)

Whie there is nothing we can do about this at this point, it is an important thing to note for later.

Finally, I did a pair plot to see how our variables compared with each other:

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/9bd7ec68-9794-494f-a538-2df045e3e837)

It seems like there are some clear outliers, some from Asia and some from North America. As mentioned above, there are likely to be the US and China, the two largest economies in the world, and arise due to the aggregated (rather than per capita) nature of our data. 
There are also clear lines being formed. This is because we included multiple years for each country; there is likely to be autocorrelation across time. THis will have to be dealt with in the final analysis.

Since rail cargo, electricity consumption, and GDP are heavily right-skewed, it seems to have made them interact with other variables rather strangely. Let's produce a version of the data where all of these are logarithmed. 

![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/ac2075bc-1c83-496e-a588-ba3114945fb8)

This looks much better. The data appear much more normal and appear to have resolved any heteroskedasticity issues that may have been present earlier. The US and China are also no longer prominent outliers. This is the data I will use to complete the project.
