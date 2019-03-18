# Data-Arrays-with-Pandas-Plotting-Attendees-at-Davos-with-Dummy-Data
# Plotting the attendees at Davos with a dummy Data Frame
# This python code is formatted for Jupyter Notebook

from matplotlib import pyplot as plt
import pandas as pd

# DAVOS Dummy Data
# Data from hosting 3 events in different years, with the number of 
#  attendees and and the average age of the attendees. A data frame
#  takes the form:

data = {'year': [2008, 2012, 2016],
       'attendees': [112, 321, 729],
       'average age': [24, 43, 31]}

# This is a dictionary with 3 attributes. To parse this data with a 
#  data frame, saved in the variable df:

df = pd.DataFrame(data)

df

# Printing the data frame:

df['year']
# Printing the pandas series:

type(df['year'])

# Applying an inequality on the list, which produces a series of boolean
#  values.

earlier_than_2013 = df['year'] < 2013

# Boolean indexing: selecting part of the data frame you want by using
#  inequalities.

df[earlier_than_2013]


# To visualise how the number of attendees has changed over the years:
plt.plot(df['year'], df['attendees'], color='c') # Plot: x = year, y = attendees
plt.plot(df['year'], df['average age'], color='r')
plt.legend(['Number of Attendees', 'Average Age'])
plt.title('How the number of attendees at Davos has changed:', fontsize=17, color='b')
plt.xlabel('Year')
plt.show()
# Note: this is dummy data.

