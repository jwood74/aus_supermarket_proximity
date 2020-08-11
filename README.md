# aus_supermarket_proximity

I was wondering how close Australian's lived to their nearest supermarket.

Specifically, how many lived within 5km of their nearest super store.

## 1. Step one - List

Get a list of the stores for use in this comparison.

I initally went with just Coles and Woolworths, but decided to chuck in IGA too given their large number of stores.

Each of their websites had a map or list of stores which was used for this project.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores.geojson)

## 2. Step two - Buffer

There are a couple of ways I could have gone about this project, but I decided to add a 5km buffer around each store, and then determine how many people lived inside and outside.

QGIS has a feature built in to do this, but I decided to go with [RGeo](https://github.com/rgeo/rgeo) in ruby, so I could program a lot of this project from code.

## 3. Step three - mega shape

Step 2 left me with 1000+ different 10km circles, so I decided to mush these together into one mega shape which will help comparing with population.

Again, QGIS has some built functions to help with this (disolve or union) but I stuck with RGeo.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/unique_stores_buffer.geojson)

## 4. Step four - compare

Now came for the step of compare this mega shape to a list of SA1s - determine how much each SA1 fits inside the mega shape.

Like above, QGIS has some functions to help with selecting overlapping shapes, and determining proportions of overlap, but I used the RGeo intersects function and compared each SA1 with my mega shape.

This left me with a CSV of every SA1 that intersecting the mega shape, and what proportion of that SA1 was overlapped.

## 5. Step five - calculate

All that was left was the calculate the percentage of population that is within the the mega shape using some recent SA1 population numbers.

I intially went to the ABS website, but couldn't find any super recent numbers broken down by SA1.

Then I remembered that AEC provides SA1 numbers after an election, for the purposes of see how many people voted from each area. This dataset is only showing electors, as opposed to the full Australian population, but I believe that is sufficient for this purpose. It also excludes children, which is probably good for this purpose.

So I looped through each SA1, got it population, and if it overlapped with the mega shape, I multipled the population by the proportion overlap.

# Results

90.3% of Australian's live within 5km of a Coles, Woolworths or IGA. (Note - this list does include some branded fuel stations, but were intentially left in)

I figured I could then break that down by State (simply by adding some code in Step 5)

| State | % within 5km | % within 5km - metro |
| -- | -- | -- |
| NSW | 91% | 98% |
| Vic | 92% | 98% |
| Qld | 88% | 96% |
| WA | 94% | 99% |
| SA | 86% | 96% |
| Tas | 79% | 88% |
| NT | 78% | 94% |
| ACT | 99% | 99% |

You'll see I also added a metro column column, focusing just to capital cities of each state.

# Bonus Side Quest!!

What about the Golden Arches - McDonalds

Following the same process as above, turns out there is a McD's within 5km of 80.6% of Aussies.

Map [here](https://github.com/jwood74/aus_supermarket_proximity/blob/master/maccas_buffer.geojson)

# ToDo

- Expand on all of the above steps to provide actual details and code snippets of how each were done.
- Chuck in a couple screenshots to make it pretty.