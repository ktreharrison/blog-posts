# An Introduction to Web Scraping with Python and BeautifulSoup

There are many instances where you visit a website and think “This is good data, I can use it for xx \[insert your interest\]”. This lightbulb moment is quickly met with the thought “how do get just the data I am interesting without the copying or downloading the whole page?!”

No need to worry, [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) is here for you. [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) comes in handy to scrape the HTML. If we find the data we want to analyze online, we can use [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) and turn it into a structure we can understand. This Python library, which takes its name from [a song in Alice in Wonderland](https://www.youtube.com/watch?v=FWxFsJUlBbw), allows us to easily and quickly take information from a website and put it into a DataFrame.

We will walk through a small example of getting data from a source with no download option. We will use the [English Premier League table](https://www.premierleague.com/tables) and get all 20 team’s *position, name and points.*

**Prerequisite**

*   Python3 installed on your local machine
*   An IDE or Text editor to write the code (I use Atom for this demo)

#### 1. Install BeautifulSoup

Open your terminal and install BeautifulSoup

`pip install beautifulsoup4`

#### 2. Then in your text editor import:

`from bs4 import BeautifulSoup`

#### 3. Get the website data — Request

Python has a `requests` library that makes getting content really easy. All we have to do is import the library, and then feed in the URL we want to `GET`:

```py
import requests

webpage_request = requests.get(‘https://www.premierleague.com/tables')

webpage = webpage_request.content
```
The result is the full HTML output of the `webpage` variable


```sh
b'<!DOCTYPE html>\n<html lang="en">\n<head>\n    <meta name="twitter:title" content="Premier League Table, Form Guide & Season Archives"/>\n<meta name="keywords" content="Premier League, Football, Soccer, Official"/> .............
```
We can parse the output to a more readable HTML format:

```py
soup = BeautifulSoup(webpage, 'html.parser')
```

*The result of soup parsing:*
```sh
<!DOCTYPE html>

<html lang="en">  
<head>  
<meta content="Premier League Table, Form Guide &amp; Season Archives" name="twitter:title"/>  
<meta content="Premier League, Football, Soccer, Official" name="keywords"/>  
<meta content="website" property="og:type"/>
```

While is a step close to getting the data we want, we still have a lot of data we don’t need.

#### 4. Locate the page attributes

Now we need to go back to our webpage and use the developer tab to get the HTML elements we need to get the positions, teams, and points. You can right-click, then select go to inspect to open the browser developer tab.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642597996552/8-W4ngNAI.gif)

**Position:** We want to find the league position first, which is located at the HTML class `‘resultHighlight’`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642597998874/pGELSujcH.png)

**Teams:** is located at the class `‘long’`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642598000432/KKs6LbCeQ.png)

**Points:** is located at the class `‘points’` in the `<td>` element.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642598002494/3fdb3t8B5.png)

Now we know what elements/attributes position, teams and points are, we can use BeautifulSoup’s `.find_all()` method to find all the data we are looking for. The `find_all()` method take a dictionary with the HTML element/attribute as its key and the name of the element as its value:

```py
league_positions = soup.find_all(attrs={‘class’: ‘resultHighlight’})

league_teams = soup.find_all(attrs={‘class’: 'long'})

league_points = soup.find_all(attrs={‘class’: 'points'})
```
#### **5. Cleaning the data**

Great! We got the elements we need, but it is still in an HTML format. We will turn this HTML data into a list (Note: You can use any data structure you like).

The positions print as:

```sh
[<span class="resultHighlight">  
                                1  
                            </span>, <span class="resultHighlight">  
                                2  
                            </span>, <span class="resultHighlight">  
                                4  
                            </span>
]
```

This is similar for teams and points. A `[list comprehension](https://www.w3schools.com/python/python_lists_comprehension.asp)` will nicely clean this up. We will sort the and get only the unique numbers with `sorted()` and `set()` then we `[zip](https://www.w3schools.com/python/ref_func_zip.asp)`the teams and points into 1 list :
```py
# We remove duplicate with a set, then turn it back into a list
position = sorted(
 set(list(
 [int(position.get_text().strip())
 for position in league_positions][:21])))

teams = [team.get_text().strip() for team in league_teams][:21]

points = [point.get_text().strip() for point in league_points][1:21]

# Combine the teams with their points
premier_league_table = list(zip(teams, points))

```

#### **6. Put into a DataFrame**

Now we have a two list to work with. 1 of integers for the league position and 1 that is a zipped list of the teams and points.

***Note:*** *I could have used* `*range()*` *for the positions, but I wanted to show how you can accomplish with*`*BeautifulSoup*`

```py
# Data into a DataFrame
import pandas as pd

print(“Final Premier League standing:”, end=(‘\n’))

df = pd.DataFrame(premier_league_table, index=position,
columns=[‘team’, ‘points’])

# Rename the index column to position
df.index.rename(“position”, inplace=True)

```

#### **7. Export your Data**

Lastly, use the command below to export your DataFrame to a .csv file. You will find the file in your current working directory (same as your .py file).

```py
# Export the data to csv
df.to_csv(“preimer_league_season_20–21.csv”)
```
![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642598004068/2Ub9pdHG0.png)

I run the code below and added the file to a git repo [here](https://github.com/ktreharrison/beautifulSoup-premier-league-scrape):

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1642598006626/ajgvG4Hf5.gif)

That took less than 4 seconds!

### Conclusion

Amazing! Now you know the basics of how to use BeautifulSoup to turn websites into data. You now can see how far the rabbit hole goes by finding some interesting data you want to analyze on the web. But remember to be respectful to site owners.

Thanks for reading

Ken

*More content at* [***plainenglish.io***](http://plainenglish.io)