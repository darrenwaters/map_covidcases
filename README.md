# map_covidcases
Analysis of Covid positive cases in Wales through a Flourish map and Medium story

Step 1 was to consider what kind of story I wanted to tell and whether or not the data is available or can be assembled successfully.

I wanted to look at local Covid-19 rates in my local area - but it seems data at a LSOA (lower super output area) for Wales is not available.

Instead, I looked for LA (local authority) data for Wales. I went to the Public Health Wales (PHW) dashboard where I found data for LA's batched up by weeks, and rolling averages. https://public.tableau.com/profile/public.health.wales.health.protection#!/vizhome/RapidCOVID-19virology-Public/Headlinesummary

Unfortunately there appears to be no way to download this as data - only as a PDF. I considered epxloring a PDF to Excel route (using Excel's new Get Data functionality) but a plea on Twitter led me to this data: http://www2.nphs.wales.nhs.uk:8080/

Interestingly, PHW does not make this data - which includes daily testing figures and positive cases for each Wales LA by day - easy to find.

From there I built a pivot table which allowed me to see the monthly cumulative positive cases for each LA going back to February this year. From there I could see the change over time and start to think about what story do I want to tell based on what the data is showing.

A few things to highlight - the pivot table automatically showed time as **Months**. I'm guessing that might "hide" some interesting week to week changes but I don't know how to turn that into displaying weeks. I probably need to find a way to aggregate up daily data into weekly data - taking into account blank days, i.e. if there were no tests that day does that mean the date doesn't appear in the sheet, but I think this is something R can do more effectively.

I also wanted to calculate the % of the LA population, and Wales, have tested positive in total and over time. To do this I downloaded the ONS' recent mid year population estimates, and from that built a quick pivot table pulling out the LA pop stats in Wales.

From there I could add that information to my working sheet, and start to do a calculation - e.g. total positive tests / total population = positive infection rate.

What stood out to me was that Wales was approaching almost 1 in 100 people testing positive for Coronavirus - and how the rate varied across Wales. That felt like a nice story, and something to visualise.

Thankfully Flourish has the geometry for all of Wales' LAs - but try as I might I couldn't get VLOOKUP to pull the geometry information from one sheet and match to my sheet with my LA data such as total cases/rates. But once I had filtered and done some sorting - it sort of worked.

From there I built my map. I had hoped to do something more interesting with changing rates over time - but in the end decided to KISS it. (Keep it simple, stupid). And so there you have it - one simple story, and one simple map.
