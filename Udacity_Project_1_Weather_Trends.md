
# Data Analyst Nanodegree Program at Udacity
## Project 1: Explore Weather Trends
      
Two SQL queries were written in order to extract the data. First, the one for the global temperature 

    SELECT year, avg_temp
    FROM global_data

and second, the one for the local temperature in the cities where I lived long:

    SELECT year, city, country, avg_temp
    FROM city_data
    WHERE city in ('Munich', 'Warsaw', 'Kiev')

The moving averages are calculated for the 5-year period. This is done in LibreOffice with a standard function SUM and then expanded to the rest of the columns. The period is chosen to be smaller than the 11-years solar cycle. Calculations span from 1750 to 2013, because this is the period, for which gapless data are available. The obtained results are shown in Fig. 1.
<img src="5 years moving average temperature.png" width="100%">
**Fig. 1:** 5-year moving average temperature for the whole world, Warsaw, Kiev, Munich (top to bottom). 

One can see that:
- The **warmest city is Warsaw**, the **coldest is Munich**. All three chosen cities are colder than the average world. This is due to the fact that the cities are situated in the northern hemisphere with rather large latitude.
- **Temperature in Kiev** is highly **correlated with that in Warsaw**. The corresponding correlation coefficient is 0.89, for Munich and Warsaw it is 0.85, while for Munich and Kiev 0.69. The difference is larger for more distant cities. The correlation coefficient between the global and Munich temperature is only 0.56, because local temperatures are much more volatile, see Fig. 1. 
- [**The Year Without a Summer (1816)**](https://en.wikipedia.org/wiki/Year_Without_a_Summer) happened during the ongoing **decreasing temperature trend**.  Therefore, **the 1815 eruption of Mount Tambora** is the reason for the particularly low temperature that year, however, it **is not a primary reason** for the decreasing temperature, which is connected with solar activity minimum, known as [**Dalton Minimum**](https://en.wikipedia.org/wiki/Dalton_Minimum).
- There is a clear **increasing temperature trend** at least **from 1950**, or even from 1900. 

In order to quantify visible trends, one more figure was made. The average temperature from 1750 to 2013 was calculated (300-year average). Then, the deviation of 5-year average from the 300-year average was calculated for the world and for each city, using the formula

$$\frac{\text{5 year average}-\text{300 year average}}{\text{300 year average}}*100 ~=~\text{Deviation [%] }$$

All the curves fluctuate around zero axis by construction. Therefore, for clarity, only two curves are shown in Fig. 2 – the result for the world temperature, and for the temperature in Munich.

<img src="Normalized 5 years moving average temperature.png" width="100%">

**Fig. 2:** Deviation of 5-year average temperature from the 300-year average for the world (thick line) and for Munich (thin line).

One can see that:
- The 5-year average **world temperature is larger** than the **300-year average since** about **1920**. This is in contrast with the data before 1920, which show a semi-periodic cooling.
- The data for Munich fluctuate stronger than for the world, because it is a particular city, while the world data contain the average over many cities, which may not be correlated, see Fig. 1 and the discussion afterwards.
- The Munich **data reflect the 11-year (solar) cycle** clearer than the world data.
- Average **temperatures in Munich are above the world temperature** since about 1990, i.e. **for the last 29 years**. This has **never happened** during the observed period **before 1990**.

**Conclusions:** 
- **The world is getting hotter** since at least **from 1950**, or even from 1900.
- Local temperatures in Munich, Warsaw and Kiev are much more volatile, but also show an **increasing temperature trend** in the same period.
- The **warming in Munich is faster** than for the world since 1990.
