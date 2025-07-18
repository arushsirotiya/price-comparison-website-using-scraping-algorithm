# Price Comparison Website Using Scraping Algorithm

# Overview
This project is a web scraping tool that compares prices of products across different e-commerce websites. It currently supports three product categories: Titan Watches, HP Victus Laptops, and Boat Airdopes. The tool fetches product information from a MySQL database, scrapes the prices from the specified URLs, and displays a comparison.

# Features
- **Product Selection Menu**: Choose from three different product categories
- **Database Integration**: Stores product URLs and scraping configuration in MySQL
- **Web Scraping**: Uses BeautifulSoup to extract prices from e-commerce sites
- **Price Comparison**: Displays prices from two different websites side by side

# Technologies Used
- Python 3
- MySQL
- BeautifulSoup (for web scraping)
- requests (for HTTP requests)
- mysql-connector-python (for database connectivity)

# Database Schema
The project uses a MySQL database with a single table:
```sql
CREATE TABLE `product_info_table` (
  `product_id` varchar(255) NOT NULL,
  `urls` varchar(255) NOT NULL,
  `class_type` varchar(255) NOT NULL,
  `class_name` varchar(255) NOT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`product_id`)
)
```

# Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/price-comparison-tool.git
   cd price-comparison-tool
   ```

2. Install the required dependencies:
   ```bash
   pip install requests beautifulsoup4 mysql-connector-python
   ```

3. Set up MySQL database:
   - Import the provided SQL dump file (`project_database.sql`)
   - Update the database connection details in the script:
     ```python
     db = mysql.connector.connect(
         host="localhost",
         user="root",
         password="your_password",
         database="project_database"
     )
     ```

# Usage
Run the script:
```bash
python price_comparison.py
```

Follow the on-screen menu to select a product category:
1. Titan Watch
2. Victus Laptop
3. Boat Airdropes
4. Exit

The script will then:
1. Fetch product URLs and scraping configuration from the database
2. Scrape prices from the specified websites
3. Display the price comparison

# Sample Output
```
*******************************************************************************************************************************************************

1.Titan Watch
2.Victus Laptop
3.Boat Airdropes
4.exit
What do you want to compare ? 1

*******************************************************************************************************************************************************

BRAND: TITAN
1639SM01
Silver Dial Silver Stainless Steel Strap Watch
GENDER: Men
MOVEMENT: Quartz
COLLECTION: KARISHMA
FUNCTION: Analog
CASE MATERIAL: Metal
STRAP MATERIAL: Stainless Steel
CASE SHAPE: Round
DIAL COLOR: Silver
WARRANTY PERIOD: 24 Months
WARRANTY DETAILS: This watch offers 24 months warranty on the Movement and 12 months warranty on the Battery from the date of purchase.

*******************************************************************************************************************************************************

Data Fetched succefully from 1st site
Price from 1st website: ₹2,995

*******************************************************************************************************************************************************

Data Fetched succefully from 2nd site
Price from 2nd website: ₹2,995

*******************************************************************************************************************************************************

Price from website-1:
₹2,995

URL of website-1:
https://rameshwatch.com/products/titan-1639sm01

*******************************************************************************************************************************************************

Price from website-2:
₹2,995

URL of website-2:
https://www.price-hunt.com/watches/titan-karishma-analog-multi-colour-dial-mens-watch-1639-sm-01.php

*******************************************************************************************************************************************************
```

# Future Enhancements
1. Add more product categories
2. Implement price history tracking
3. Add graphical comparison (charts)
4. Set up email alerts for price drops
5. Create a web interface
6. Add support for more e-commerce websites

# Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your changes.

# License
This project is licensed under the MIT License.
