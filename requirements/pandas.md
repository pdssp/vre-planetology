# Pandas

## Description
- **Main Functionality**: Data manipulation and analysis library for Python, providing data structures and operations for manipulating numerical tables and time series.
- **Use in Planetology**: Essential for data cleaning, transformation, and analysis of planetary datasets.

## Technical Requirements
- **Version**: Pandas 2.0 or higher.

## Links and Resources
- **Official Documentation**: [Pandas Documentation](https://pandas.pydata.org/docs/)

## code snippet

```python
import pandas as pd

# Load data from a CSV file containing Mars rover measurements
df = pd.read_csv('mars_rover_data.csv')

# Display the first few rows of the dataframe
print(df.head())

# Calculate the mean value of a specific measurement
mean_temperature = df['temperature'].mean()
print(f"Mean temperature: {mean_temperature}°C")
```
