# linear-regression
import pandas as pd
from sklearn.linear_model import LinearRegression

# Create the dataset
data = {
    'Product': ['Laptop', 'Tablet', 'Smartphone', 'Monitor', 'Keyboard'],
    'Price': [1000, 500, 800, 300, 50],
    'Quantity Sold': [150, 300, 500, 200, 400],
    'Category': ['Electronics', 'Electronics', 'Electronics', 'Accessories', 'Accessories']
}
df = pd.DataFrame(data)

# Add Total Sales column
df['Total Sales'] = df['Price'] * df['Quantity Sold']

# Linear regression model
X = df[['Price']]  # Input feature: Price
y = df['Total Sales']  # Output feature: Total Sales

model = LinearRegression()
model.fit(X, y)

# Regression equation
slope = model.coef_[0]
intercept = model.intercept_
print(f"Linear Regression Equation: Total Sales = {slope:.2f} * Price + {intercept:.2f}")
