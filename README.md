# aus_supermarket_proximity

I was wondering how close Australian's lived to their nearest supermarket.

Specifically, how many ived within 5km of their nearest super store.

## 1. Step one - List

Get a list of the stores for use in this comparison

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores.geojson)

## 2. Step two - Buffer

Generate a 5km buffer around each store.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores_buffer.geojson)

## 3. Step three - mega shape

mush this together into one mega shape which will help comparing with population

## 4. Step four - compare

compare this mega shape to a list of SA1s - determine how much each SA1 fits inside the mega shape.

## 5. Step five - calculate

calculate the percentage of population that is within the the mega shape using some recent SA1 population numbers.

# Results

Turns out about 90.3% lives within 5km of a Coles, Woolworths or IGA. (Note - this list does include some branded fuel stations, but were intentially left in)
