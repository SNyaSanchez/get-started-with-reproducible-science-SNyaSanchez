---

# Get started with open reproducible science!

[Open reproducible science](https://www.earthdatascience.org/courses/intro-to-earth-data-science/open-reproducible-science/get-started-open-reproducible-science/) makes scientific methods, data and outcomes available to everyone. That means that *everyone* who wants should be able to **find**, **read**, **understand**, and **run** your workflows for themselves.

<img alt-text="Components of open science - accessible, reproducible, inclusive" src="https://www.earthdata.nasa.gov/s3fs-public/2021-11/Circle_Diagram_UPDATE_2.jpg?VersionId=pFRniRpjtgc_MEXUJKi9_sXLoMsSX.pB" width=500 />

 > Image from https://www.earthdata.nasa.gov/esds/open-science/oss-for-eso-workshops

Few if any science projects are 100% open and reproducible (yet!). However, members of the open science community have developed open source tools and practices that can help you move toward that goal. You will learn about many of those tools in [the Intro to Earth Data Science textbook](https://www.earthdatascience.org/courses/intro-to-earth-data-science/). Don't worry about learning all the tools at once -- we've picked a few for you to get started with.

1. Open Reproduicble science is supported by collaboration and being able to replicate. It is workflow that is easily shared, publisher, and reviewed by other to communicate ideas.
2. Github allows you to manage and track changes to your files. You can implement version control and then publish your code and workflow on the cloud.
3. Yes because there are no spaces or strange characters. Instead of spaces, you can use dashes or underscores to seperate ords within the name to make them easy to read. 

I can write clean code by:
  * `YOUR ANSWER HERE`


Advantages of clean code include:
  * `YOUR ANSWER HERE`


```python
# Importing Python Libraries
import pandas as pd


```

Once you have run the cell above and imported `pandas`, **run the cell below**. It is a test cell that will tell you if you completed the task successfully. If a test cell isn't working the way you expect, check that you ran your code **immediately before** running the test.


```python
# DO NOT MODIFY THIS TEST CELL
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas


**YOUR DATA DESCRIPTION AND CITATION HERE**


```python
rctemp = ('https://www.ncei.noaa.gov/access/monitoring/'
                       'climate-at-a-glance/city/time-series/USW00024090'
                       '/tmax/ann/2/1949-2023.csv')

rctemp
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00024090/tmax/ann/2/1949-2023.csv'




```python
# DO NOT MODIFY THIS TEST CELL
resp_url = _
points = 0

if type(resp_url)==str:
    points += 3
    print('\u2705 Great work! You correctly called your url variable.')
else:
    print('\u274C Oops - your url variable was not called correctly.')

if len(resp_url)==117:
    points += 3
    print('\u2705 Great work! Your url is the correct length.')
else:
    print('\u274C Oops - your url variable is not the correct length.')

print('You earned {} of 6 points for defining a url variable'.format(points))
```

    ✅ Great work! You correctly called your url variable.
    ✅ Great work! Your url is the correct length.
    You earned 6 of 6 points for defining a url variable



```python
#download
rctemps_df = pd.read_csv(rctemp, header=3, names=['date', 'temp'])
rctemps_df


```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>55.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>54.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>59.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>59.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for downloading data


  > HINT: Check out the `type()` function below - you can use it to check that your data is now in `DataFrame` type object


```python
# Check that the data was imported into a pandas DataFrame
type(rctemps_df)
```




    pandas.core.frame.DataFrame




```python
# ncei has wacky years
rctemps_df.iloc[:,0] = rctemps_df.iloc[:,0] // 100
rctemps_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>58.4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>55.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>54.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>59.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>59.8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp.df = points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 59.04]:
    points += 4
    print('\u2705 Great work! You correctly cleaned up years.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for cleaning up years'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for cleaning up years


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an EXTRA CHALLENGE? Modify the code to be **more expressive**.

Rewrite the code below to select columns by **name** instead of by **index**. You might find the [pandas User Guide section on slicing and dicing](https://pandas.pydata.org/docs/user_guide/indexing.html) to be useful. However - don't worry if you can't figure this out yet! We're going to talk a lot about how to use pandas `DataFrame`s. 

YOUR ANSWER HERE


```python
#convert to celcius
rctemps_df.iloc[:,1] = (rctemps_df.iloc[:,1] - 32) * 5 / 9
rctemps_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>14.666667</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>13.111111</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>12.555556</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>15.222222</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>15.444444</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>14.000000</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>12.611111</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>16.555556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>16.722222</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>16.055556</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
# DO NOT MODIFY THIS TEST CELL
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [1985.5, 59.09, 14.94]:
    points += 4
    print('\u2705 Great work! You correctly converted to Celcius.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for converting to Celcius'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ❌ Oops - your data are not correct.
    You earned 1 of 5 points for converting to Celcius


<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?
  1. As you did above, rewrite the code to be more expressive
  2. Using the code below as a framework, write and apply a **function** that converts to Celcius.
     > **Functions** let you reuse code you have already written
  
  3. You should also rewrite this function name to be more expressive.
  
        ```python
        def convert(temperature):
            """Convert temperature to Celcius"""
            return temperature # Put your equation in here

        dataframe['temp_c'] = dataframe['temp_f'].apply(convert)
        ```


```python
import seaborn as sns

sns.set(font_scale=2)

ax = sns.regplot(tmax_df_resp, x='date', y='temp')
tmax_df_resp.plot(
    x='date', y='temp',
    title='Rapid City, SD Maximum Annual Temperatures',
    xlabel='Year', ylabel='Temperature ($^\circ$C)',
    legend=False, figsize=(12,8),
    color='red', ax=ax)




```




    <Axes: title={'center': 'Rapid City, SD Maximum Annual Temperatures'}, xlabel='Year', ylabel='Temperature ($^\\circ$C)'>




    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_21_1.png)
    


**THIS ISN'T THE END! Don't forget to complete the next task where you will describe your plot**
    
<img src="https://www.nps.gov/pais/learn/nature/images/NPS-KempsRidley-Hatchlings.JPG" height=150 style="padding: 1em; border-style: solid; border-color: grey;" />

> Image source: https://www.nps.gov/pais/learn/nature/hatchlingreleases.htm

<img src="https://static.thenounproject.com/png/3842781-200.png" width=20 style="float: left; padding: 3px" /> Want an **EXTRA CHALLENGE**?

There are many other things you can do to customize your plot. Take a look at the [pandas plotting galleries](https://pandas.pydata.org/docs/user_guide/visualization.html) and the [documentation of plot](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html) to see if there's other changes you want to make to your plot. Some possibilities include:
  * Remove the legend since there's only one data series
  * Increase the figure size
  * Increase the font size
  * Change the colors
  * Use a bar graph instead (usually we use lines for time series, but since this is annual it could go either way)
  * Add a trend line

## YOUR RAPID CITY PLOT HEADLINE HERE
Describe your plot in this cell in 2-3 sentences

**THIS ISN'T THE END EITHER! Don't forget to reproduce your analysis in a new location!**

<img src="https://static.independent.co.uk/s3fs-public/thumbnails/image/2008/12/26/20/107000.jpg" height=150 style="padding: 1em; border-style: solid; border-color: grey;" >

> Image source: https://www.independent.co.uk/climate-change/news/by-the-left-quick-march-the-emperor-penguins-migration-1212420.html

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. See the instructions above fore how to get your URL. You will need to make your own new Markdown and Code cells below this one.
