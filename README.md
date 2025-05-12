 Part 1: Data Normalization (Up to 3NF)

 Original Dataset -'Sales_data.csv`

The original CSV file (`Sales_data.csv`) was a flat table containing customer, product, location, and order-level details. It was **not normalized** and suffered from data redundancy and update anomalies.

Normalization Process

The dataset was normalized through the following steps:

1. 1NF (First Normal Form):
   - Removed repeating groups.
   - Ensured atomicity in every field.
   - Created individual tables for `Customer`, `Product`, `Region`, etc.

2. 2NF (Second Normal Form):
   - Eliminated partial dependencies by creating lookup tables for `State`, `Region`, `Country`, `Category`, and `SubCategory`.

3. 3NF (Third Normal Form):
   - Removed transitive dependencies such as:
     - `SubCategory → Category`
     - `State → Region → Country`

Final Schema

Key tables in the normalized database:
- `Customer(CustomerID, FirstName, LastName, City, StateID)`
- `Product(ProductID, ProductName, SubCategoryID, Price)`
- `Orders(OrderID, CustomerID, ProductID, OrderDate, Quantity, Sales)`
- `State(StateID, State, RegionID)`
- `Region(RegionID, Region, CountryID)`
- `Country(CountryID, Country)`
- `SubCategory(SubCategoryID, SubCategory, CategoryID)`
- `Category(CategoryID, Category)`

Foreign key constraints were implemented to enforce referential integrity.

---

Part 2: Python-Based Business Analysis

After loading the normalized data into Python, we generated five business-driven visualizations.

Insights & Visuals

1. Year-over-Year Sales Growth
   - 📈 Steady growth from ₹12M to ₹20M between 2015–2018.
 

2. Revenue by Product Category
   - 🗂️ Office Supplies dominated sales with over 60% contribution.


3. Top 5 Customers by Total Spend
   - ⭐ Some customers spent over ₹270K individually.


4. Distribution of Order Values
   - 💳 Many orders ranged between ₹12K–₹22K, showing premium buying behavior.


5. Regional Sales Performance
   - 🌍 The East region led in revenue in the latest year.


All visuals were generated using `pandas` and `matplotlib`.

Tools Used

- SQLite3
- Python 3.8+
- Pandas
- Matplotlib
- Jupyter Notebooks




