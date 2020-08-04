## Using Matplotlib to Visualize Data

### Investigating the Effects of Four Cancer Treatments on Tumor Size in Mice


#### Raw Data

![Raw Data](Images/Raw_Data.PNG)


#### Removing Mice with Duplicate Time Points ("t")

        /# Getting the duplicate mice by ID number that shows up for Mouse ID and Timepoint.
        problem_mice = [] #list of mice with more than one timepoint.
        for id in d.id: #Looping thru mice in data series
            unique_timepoints = []
            for timepoint in d[d.id == id].loc[:, 't']: #Looping thru time points for each mouse
                if timepoint not in unique_timepoints:
                    unique_timepoints.append(timepoint)
                else:
                    if id not in problem_mice: 
                        problem_mice.append(id)
        problem_mice
