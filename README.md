# Surfs_Up

## Challenge Overview

### Purpose:
   The purpose of this analysis is to help the owner to get more information about temperature trends, in order to determine if the surf and ice cream shop business is sustainable year-round,
specifically, the temperature data for the months of June and December in Oahu.    

## Resources
- Software:
   - Jupyter Notebooks 6.4.3
   - Python 3.8.8
- Data sourced: 
   - [hawaii.sqlite](https://github.com/SYDsCorner/Surfs_Up/blob/main/hawaii.sqlite)
   
## Results

- Temperatures in June range between 64°F and 85°F while temperatures in December range between 56°F and 83°F.
- The average temperature in June is about 75°F which is higher than the average temperature in December of 71°F.
- The standard deviation of temperatures in December is higher than that of June which means that the spread of temperatures in December has more variation. 


<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/89308251/138387308-b19ced9f-7f25-4898-a6e4-d802ee836c74.png">
</p> 

 
## Summary

- From the results, we can conclude that it is sustainable year-round to open the surf and ice cream shop business 
  because we have identified that the average temperature in the summer (June) was 75°F and 71°F in the winter (December).
  These are good temperatures for outdoor activities.
  
- There are additional queries to perform to gather more weather data for June and December.
  For example:

  - A query to retrieve the data and precipitation scores with the most active stations for June and December.   
   
    ```
    session.query(Measurement.date, Measurement.prcp).\
        filter(Measurement.station == 'USC00519281').\
        filter(extract('month', Measurement.date) == 6).all()


    session.query(Measurement.date, Measurement.prcp).\
        filter(Measurement.station == 'USC00519281').\
        filter(extract('month', Measurement.date) == 12).all()
    ```
    ![Waihee_JunDec_prcp](https://user-images.githubusercontent.com/89308251/138389063-ac23d426-a142-449b-a847-8b8b11f8c765.png)


    
  - A query to retrieve the temperature observations with the most active stations for June and December.   
   
    ```
    session.query(Measurement.date, Measurement.tobs).\
        filter(Measurement.station == 'USC00519281').\
        filter(extract('month', Measurement.date) == 6).all()

    session.query(Measurement.date, Measurement.tobs).\
        filter(Measurement.station == 'USC00519281').\
        filter(extract('month', Measurement.date) == 12).all() 
    ```    
    ![Waihee_JunDec_temps](https://user-images.githubusercontent.com/89308251/138389303-41f3e492-7e54-49be-924a-50ec75e3df46.png)


