# osmod

Estimating origin-destination flows from OSM data

## TODO List

1. Choose a test location - Briston, U.K.?
2. Use [`osmdata`](https://github.com/osmdatar/osmdata) to extract all building
   polygons ~~and building heights where given~~. For residential buildings:
   - Construct some kind of simple statistical model to estimate heights of
   buildings lacking OSM heights
   ~~- Polygon area times height ~ residential population density, with census
   data as ground truth and calibration.~~
   - Use global population density data to down-sample to OSM building polygons.

   For commercial and industrial buildings:
   - ~~Repeat same procedure for density of employments (likely using
           different models for commercial and industrial).~~
    - Think of a smarter way to estimate employment densities?
3. Define a distance decay function for proportion of people that cycle to work
   as a function of distance to workplace.
4. Define some kind of function defining for a residential location some
   distance from the city centre the probability of that person working in some
   location a specific distance from both the city centre and their residential
   location. This will be some kind of two-parameter distance decay function.
5. Use output of Step#4 to route population density through the street network
   using a probabilistic router to convert that to relative densities of cycle
   traffic. This can be done separately for travel both *to* and *from* work.

## Refinements

1. Include travel not related to work, through connecting residential densities
   with leisure and commercial locations, to reflect recreation and shopping
   activities.
2. Improve the model suggested in Step#4 to reflect not necessarily radial
   urban structure.
3. Use google earth engine to automatically identify bicycles - that could well
   be possible? - and individual people on pavements. Feed that in as an extra
   parameter to reflect the possibility that those locations where more people
   are out and about without cars are also more likely to see more cycling
   activity.
4. Several spatially-defined variables will ultimately be able to be both
   automatically and globally derived, and the analysis could likely be fed into
   a neural network rather than hard-coding a fixed statistical algorithm.
   OSMODMAI? ODOSMAI?
