---
title: Milk prices in Canada, U.S.A., New Zealand, and Europe
author: Denis Haine
date: '2018-07-31'
slug: milkPrice
categories: ['R', 'Shiny']
tags: ["rstats"]
---

As an exercise for [Coursera](https://www.coursera.org/ "Coursera") [Data
Science
Specialization](https://www.coursera.org/specializations/jhu-data-science) I'm
presently taking, I had to develop a [Shiny](https://shiny.rstudio.com/ "R
Shiny") app with the aim to visualize data.
For this, I wanted to look at milk prices, farm gate and retail, in Canada and
for various countries.
The Shiny app can be found at <https://dhaine.shinyapps.io/milkPrice/>.

I collected data from Canada, U.S.A., New Zealand, and the EU (EU 15: Belgium,
France, Spain, Ireland, Portugal, Germany, Luxembourg, United Kingdom, the
Netherlands, Denmark, Austria, Sweden, Italy, Finland, and Greece; EU 28: the
aforementioned countries plus the Czech Republic, Estonia, Cyprus, Latvia,
Lithuania, Hungary, Malta, Poland, Slovenia, Slovakia, Bulgaria, Romania, and
Croatia).
Obviously, some data are missing for either countries or years.
All prices are given in Canadian dollars, using currency conversion on first day
of the year (obtained from [XE Corporation](https://xe.com/)).
U.S. data on farm gate prices are from USDA-NASS and were converted from cwt to
litre (1 cwt = 44.0242 litres).
Canadian data are from [Les Producteurs de lait du
Québec](http://lait.org/leconomie-du-lait/statistiques/).
New Zealand data are from [CLAL.it](https://www.clal.it/en/).
European data are from DG Agri.
Kilograms of milk were converted to litres (1 kg = 0.9708737864 litre).

Data on retail prices for Canada are coming from Statistics Canada, for the U.S.
from USDA AMS, and for Europe from Eurostat (available only on a yearly basis
from 2013 to 2015).
U.S. prices were converted as price per litres from the reported price for half
a gallon of milk (half a gallon is 1.89270589 litre).
Canadian and European prices are for semi-skimmed milk.

## (Some) Results

So here are the farm gate prices for Canada, EU15, New Zealand, and USA.

![Farm Gate Prices](/blog/2018-07-31-milkPrice_files/figure-html/farm_gate.png "Farm
Gate Prices")

And here's a comparison of retail prices from Canada and a few other countries.

![Retail Prices](/blog/2018-07-31-milkPrice_files/figure-html/retail_price.png
"Retail Prices")

We see that both farm gate and retail prices are very stable in Canada, contrary
to other countries, especially the US.
Farm gate prices are also higher in Canada than the US, EU, and New Zealand.
Canada has a national supply management system, put in place in the '70s to
stabilize prices that were quite volatile before that.
This system set the price of milk according to the cost of producing it, controls
the milk supply to the market, and limits the importation of milk and milk
products.
Export of milk is also limited.
So farm gate prices are higher in Canada than the US.
But let's not forget that US dairy production system is subsidized (22.2 billion USD in 2015
or 0.35 CAD per litre, i.e. 73% of the producer's returns - [realagriculture](https://www.realagriculture.com/2018/02/u-s-dairy-subsidies-equal-73-percent-of-producer-returns-says-new-report/)) while the supply management system do not provide such subsidies to the Canadian
dairy producer.
Moreover, it is not easy to compare prices across countries (farm gate or
retail).
Production systems are different, production and economic records are not
standardized, and the product itself is different.
For example,
[rBST](https://www.realagriculture.com/2018/02/u-s-dairy-subsidies-equal-73-percent-of-producer-returns-says-new-report/)
is allowed in the US but not in Canada, New Zealand or the EU, norms and
regulations varies, etc.

Regarding the retail prices, things are not easy to compare.
First I couldn't find New Zealand prices, and the EU prices for some countries
and/or periods only.
Even units can be different.
US data are given for a gallon, or half a gallon, while it is per litre in the
other countries.
And as always, buying in larger quantities is cheaper than smaller ones, i.e. US
prices here are certainly slightly underestimated.
Therefore we see that retail prices are marginally higher in Canada than the US,
while it can vary greatly between European countries.

Are these graphs trustworthy?
Well, the objective was to design a Shiny app, so the focus was on programming
it, not especially finding the most accurate data.
And as I learned, there are big differences between countries.
The app allows to choose between different milk prices and to compare between
various countries.
Plots can be saved, zoomed in, hover it etc.
Shiny apps are really awesome (I've got another for the use of my R package [episensr](https://dhaine.shinyapps.io/episensr_shiny/)) and, finally, finding data was more difficult than building the app!

