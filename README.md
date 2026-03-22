import pandas as pd

# dataset
data = {
    "Product": ["A","B","A","C","B","A"],
    "Price": [100,200,120,300,210,130],
    "Quantity": [1,2,1,3,2,1]
}

df = pd.DataFrame(data)

# create Total column
df["Total"] = df["Price"] * df["Quantity"]

# analysis
total_sales = df["Total"].sum()
top_product = df.groupby("Product")["Total"].sum().idxmax()

# output
print("Total Sales:", total_sales)
print("Top Product:", top_product)
