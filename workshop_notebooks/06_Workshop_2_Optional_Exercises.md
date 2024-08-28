---
title: "Workshop 2 Optional Exercises"
date: 2024-08-28
authors:
  - name: JT Thielen
---

## Introduction

These are a set of practice problems that reinforce and extend upon everything we covered in Workshop 2. Most will require you to reference the respective packages' documention. As with the first set of optional excercises, these range from easy to quite challenging, so don't feel discouraged if you're struggling to complete one of these problems.

## Problems

### CartoPy Natural Earth Features

The [Natural Earth feature collection](https://www.naturalearthdata.com/features/) has numerous vector and raster data themes that can display cultural or physical features. For this problem, **create a two panel plot using matplotlib (and Cartopy) that compares two different Natural Earth backgrounds over the state of Colorado** (or other region of comparable size).

Some tips:

- Remeber to use the axes-based interface (e.g., starting with `plt.subplots()` or `plt.subplot_mosaic()`) to handle a single figure with multiple panels.
- Mid-latitude locations like Colorado will look somewhat distorted in a Plate Carree projection. Try setting your plot's projection to a Lambert Conformal Conic or Mercator projection.
- Try using [geojson.io](https://geojson.io/) to get the coordinates of your bounds if you don't want to guess and check or look them up by other means.
- Pay attention to the `scale` argument. Finer scales will look more detailed, but take longer to download.

*Extra Option:* Look up a collection of geographical point data (such as the locations of airports, ASOS stations, mountain peaks, or radar sites). Using Pandas, create or read in this collection of lat-lon point data, and plot them on your feature map as well. Don't forget to account for projections!

### Using Masking/where Options

Sometimes in our field, a formula is only valid for a given range of input values. An example of this is wind chill (see [https://www.weather.gov/media/epz/wxcalc/windChill.pdf](https://www.weather.gov/media/epz/wxcalc/windChill.pdf) or the [MetPy documentation](https://unidata.github.io/MetPy/latest/api/generated/metpy.calc.windchill.html#metpy.calc.windchill) for details), where wind chill is typically only defined when temperature is less than or equal to 50 $\degree F$ and the wind speed is at least 3 miles per hour.

For a set of sample data (you can pull this from a real-world data source, or use random data covering both the valid and invalid ranges), use pandas to implement a wind chill calculation that masks (or utilizes `where`) to properly account for the ranges of values for which it is valid. 

### Accessing Remote Data

Both Pandas and xarray have functionality under-the-hood to not just load data from your local disk, but also remotely over the internet. Below are two open-ended examples to showcase this ability.

#### Pandas

A common tabular data source in our field is station observations. One source that provides these data readily is the [Iowa Environmental Mesonet (IEM)](https://www.mesonet.agron.iastate.edu/). You can load a time series of station data using a remote URL like the following:

```python
pd.read_csv((
    "https://mesonet.agron.iastate.edu/cgi-bin/request/asos.py"
    "?data=tmpf&data=dwpf&station=BDU&hours=48"
))
```

- Using this as an example, make a simple plot of temperature and dewpoint for the Boulder station over the last 48 hours
- *Extra option*: Notice the query arguments present in the URL string above. Based on the documentation from IEM, try to play around with the different options
    - Fields other than temperature and dewpoint?
    - A station (or stations) other than BDU ([this page](https://www.mesonet.agron.iastate.edu/ASOS/current.phtml?sortcol=ts&network=CO_ASOS&metar=no&sorder=desc&format=html) may be helpful)
    - A longer or shorter period of time.

#### xarray

*More detail will be added to this problem soon...for now, try locating an OpenDAP link from the below THREDDS server, and include it in your xarray* `open_dataset` *command.*

```
https://tds.scigw.unidata.ucar.edu/thredds/catalog/idd/forecastModels.html
```