# aus_supermarket_proximity

I was wondering how close Australian's lived to their nearest supermarket.

Specifically, how many lived within 5km of their nearest super store.

## 1. Step one - List

Get a list of the stores for use in this comparison.

I initally went with just Coles and Woolworths, but decided to chuck in IGA too given their large number of stores.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores.geojson)

## 2. Step two - Buffer

Generate a 5km buffer around each store.

## 3. Step three - mega shape

Mush this together into one mega shape which will help comparing with population

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores_buffer.geojson)

## 4. Step four - compare

compare this mega shape to a list of SA1s - determine how much each SA1 fits inside the mega shape.

## 5. Step five - calculate

calculate the percentage of population that is within the the mega shape using some recent SA1 population numbers.

# Results

90.3% of Australian's live within 5km of a Coles, Woolworths or IGA. (Note - this list does include some branded fuel stations, but were intentially left in)

# Bonus Side Quest!!

What about the Golden Arches - McDonalds

Following the same process as above, turns out there is a McD's within 5km of 80.6% of Aussies.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/maccas_buffer.geojson)

# ToDo

- Expand on all of the above steps to provide actual details and code snippets of how each were done.
- Chuck in a couple screenshots to make it pretty.

# Data

Store locations were taken from each website.

Population figures taken from recent AEC data showing number of voters per SA1 (not exactly population, but good enough when working out percentages)