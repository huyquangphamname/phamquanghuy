
<picture>
 <source media="(prefers-color-scheme: dark)" srcset="githubBanner/DarkModeBanner.png">
 <source media="(prefers-color-scheme: light)" srcset="githubBanner/LightModeBanner.png">
 <img alt="Contact Information: <Email Address> phquy.0127@gmail.com, <Phone Number> +84 38-588-4754 " src="githubBanner/DefaultModeBanner.png">
</picture>

# Hi there 👋🏻
Good morning or good evening, depending on your time of day!

## Documentation PowerBI - A Hands-On Project
This repository contains the documentation for a hands-on project in PowerBI, which is part of the NC296 class orgainized by the Universiy of Science. The goal of the projects is to design data models, create measures, and develop insightful visualization using retail sales data.

### Data Description
The data used in this project is from a sample Retail Analysis dataset. Below is the description of the tables and their fields:
<details>
<summary> Data Interpret Table </summary>

|  Table  | Frield Name  |Description                         |
|--------:|--------------|------------------------------------|
|Districts| DistrictID   | Mã đại lý                          |
|         | District     | Quận                               |
|         | DM           | Người quản lý của Đại lý           |
|Item     | ItemID       | Mã sản phẩm                        |
|         | Segment      | Bộ Phận                            |
|         | Category     | Nhóm                               |
|Story    |LocationID    | Mã cửa hàng                        |
|         | Territory    | Lãnh thổ                           |
|         | OpenDate     | Ngày khai trương                   |
|         | SellingAreaSize | Diện tích của cửa hàng          |
|         | Chain        | Loại cửa hàng kinh doanh           |
|         | Store Type   | Loại cửa hàng mới (2014) / cũ (trước 2014) |
|Sales    | Sum_Regular_Sales_Dollars     | Doanh thu Regular       |
|         | Sum_Markdown_Sales_Dollars    | Doanh thu Markdown      |
|         | Sum_Regular_Sales_Units       | Số lượng Regular        |
|         | Sum_Markdown_Sales_Units      | Số lượng Markdown       |
|         | ScenarioID                    | =1 là năm hiện hành, =2 là năm trước |
|Time     | Period       | Tháng (bằng số)      |
|         | FiscalMonth  | Tháng (bằng chữ)     |

</details>

### Steps and Visualizations
Data Model Design
1. **Review the data structure from Truc_quan_hoa.pdf.**

2. **Create a group "Key Measure" to contains the following measures:**
- **Markdown_Sales_Dollars** = `SUM(Sales[Sum_Markdown_Sales_Dollars])`
- **Regular_Sales_Dollars** = `SUM(Sales[Sum_Regular_Sales_Dollars])`
- **Markdown_Sales_Units** = `SUM(Sales[Sum_Markdown_Sales_Units])`
- **Regular_Sales_Units** = `SUM(Sales[Sum_Regular_Sales_Units])`
- **Total Sales** = `[Markdown_Sales_Dollars] + [Regular_Sales_Dollars]`
- **Total Units** = `[Markdown_Sales_Units] + [Regular_Sales_Units]`
- **This Year Sales** = `CALCULATE([Total Sales], Sales[ScenarioID] = 1)`
- **Last Year Sales** = `CALCULATE([Total Sales], Sales[ScenarioID] = 2)`

#### Visualizations

1. **Pie Chart**: Visualize This Year Sales by Chain.
2. **Clustered Column Chart**: Visualize Total Sales Variance by FiscalMonth and District Manager.
3. **Map Chart**: Visualize This Year Sales by PostalCode and Store Type.
4. **Scatter Chart**: Visualize Total Sales Variance %, Sales Per Sq Ft, and This Year Sales by District and District.
5. **Line Chart**: Visualize This Year Sales by FiscalMonth.

#### Report Design

1. **Design a "Store Sales Overview" report page.**
2. **Design a "New Stores Analysis" report page.**
3. **Create slicers for District Manager and Stores Name.**

#### Measures for Advanced Calculations

1. **Total Sales Variance** = `[This Year Sales] - [Last Year Sales]`
2. **Total Sales Variance %** = `DIVIDE([Total Sales Variance], [Last Year Sales])`
3. **Sales Per Sq Ft** = `DIVIDE([This Year Sales], CALCULATE(DISTINCTCOUNT(Sales[MonthID]), Sales[ScenarioID] = 1) * SUM(Store[SellingAreaSize])) * 12`
4. **Avg $ / Units TY** = `DIVIDE([This Year Sales], [This Year Units])`

### Conclusions
This project aims to provide practical experience in using PowerBI to analyze and visualize retail sales data. The steps outlined above guide through data modeling, measure creation, and various visualizations to extract meaningful insights and improve decision-making processes.

For any queries or further information, feel free to contact me at:

**Email**: [phquy.0127@gmail.com](mailto:pqhuy.0127@gmail.com)
**Phone**: [+84 38-588-4754](tel:+84385884754)