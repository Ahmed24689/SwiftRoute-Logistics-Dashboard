# SwiftRoute Logistics Dashboard

An interactive Power BI logistics analytics dashboard designed to monitor delivery operations across orders, hubs, drivers, and vehicles.

The project transforms operational logistics data into actionable insights about delivery performance, customer satisfaction, hub capacity, driver performance, and fleet utilization using Power BI, Power Query, and DAX.

![SwiftRoute Logistics Dashboard](https://private-us-east-1.manuscdn.com/sessionFile/F31drDprD25QIzbXnekKQx/sandbox/Wh9F8eEzEw9sSMbq9vZB8a-images_1794646344140_na1fn_L2hvbWUvdWJ1bnR1L1N3aWZ0Um91dGUtTG9naXN0aWNzLURhc2hib2FyZC9zY3JlZW5zaG90cy9leGVjdXRpdmUtb3ZlcnZpZXc.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvRjMxZHJEcHJEMjVRSXpiWG5la0tReC9zYW5kYm94L1doOUY4ZUV6RXc5c1NNYnE5dlpCOGEtaW1hZ2VzXzE3OTQ2NDYzNDQxNDBfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwxTjNhV1owVW05MWRHVXRURzluYVhOMGFXTnpMVVJoYzJoaWIyRnlaQzl6WTNKbFpXNXphRzkwY3k5bGVHVmpkWFJwZG1VdGIzWmxjblpwWlhjLnBuZyIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc5NjA4MzIwMH19fV19&Key-Pair-Id=K2QY5QTL8JSY6C&Signature=MEUCIQCrKSnVxRuf9EotEFQhViRvxtQVUT2wIsu6jEM11byysgIgJop7X9F8VdzMVO450VwefYUFlj9t-J2GAhTtQm6KIVY_)

## Project Overview

SwiftRoute Logistics Dashboard provides an executive-level view of logistics operations for a selected year and month. It compares current-month performance with the previous month and highlights the main operational areas that affect delivery efficiency and customer experience.

The dashboard is built in Microsoft Power BI for logistics managers and operations teams who need to monitor service levels, identify bottlenecks, evaluate workforce performance, and support data-driven planning decisions.

## Business Objectives

The dashboard was developed to answer the following business questions:

- How many orders were processed during the selected period?

- Is delivery performance improving or declining compared with the previous month?

- What is the current on-time delivery rate?

- How satisfied are customers with the delivery service?

- Which hubs are processing the highest workload compared with their capacity?

- Which hubs are performing best and which may require operational attention?

- Is there a relationship between driver experience and performance rating?

- Which drivers have the highest delay rate?

- How many vehicles are available and active?

- Which vehicle models handle the highest order volume?

- Which vehicles or vehicle models may require additional maintenance attention?

## Dashboard Pages

### 1. Executive Overview

The overview page summarizes the most important logistics KPIs for the selected year and month.

Key metrics include:

- Total Orders

- Previous Month Orders

- Month-over-Month Order Growth

- On-Time Delivery Rate

- Previous Month On-Time Delivery Rate

- Customer Satisfaction Score

- Average Delivery Time

- Total Hubs

- Total Drivers

- Total Vehicles

- Hub Performance Ranking

- Driver Experience vs. Performance Rating

- Drivers with the Highest Delay Rate

- Vehicle Status Distribution

- Orders by Vehicle Model

### 2. Hubs Overview

This page focuses on hub capacity, workload, and operational performance.

Key analyses include:

- Total Number of Hubs

- Orders Processed vs. Hub Capacity

- Hub Performance Ranking

- Hub Order Processing Time

- Identification of overloaded or underutilized hubs

### 3. Drivers Overview

This page evaluates driver workforce performance and workload patterns.

Key analyses include:

- Number of Drivers

- Experience vs. Performance Rating

- Drivers with the Highest Delay Rate

- Driver Profile Summary

- Hire Date

- Years of Experience

- Performance Rating

- Deliveries Completed During the Selected Month

- Monthly Order Trends

### 4. Vehicles Overview

This page evaluates fleet availability, utilization, reliability, and maintenance risk.

Key analyses include:

- Number of Vehicles

- Active vs. Maintenance Vehicles

- Orders by Vehicle Model

- Vehicle Age vs. Breakdowns

- Breakdowns by Vehicle Code

- Breakdowns by Vehicle Model

- Orders by Vehicle Type

## Key Performance Indicators

### Total Orders

The total number of orders recorded during the selected year and month.

```
Total Orders = Count of unique Order IDs
```

### On-Time Delivery Rate

The percentage of delivered orders that met the promised delivery time.

```
On-Time Delivery Rate = On-Time Delivered Orders / Total Delivered Orders
```

Cancelled orders should be excluded from this calculation when they were not eligible for delivery.

### Customer Satisfaction Score

The customer satisfaction metric is calculated from valid customer satisfaction responses. The exact calculation depends on the rating scale and business definition used in the source data.

### Average Delivery Time

The average number of hours required to deliver completed orders during the selected period.

```
Average Delivery Time = Average of Delivery Time Hours
```

### Month-over-Month Change

The percentage change between the selected month and the previous month.

```
MoM Change % = (Current Month Value - Previous Month Value) / Previous Month Value
```

For rate-based KPIs, the dashboard may also display the change in percentage points to distinguish it from relative percentage growth.

### Hub Utilization

The proportion of a hub's processing capacity used during the selected period.

```
Hub Utilization % = Orders Processed / Hub Capacity
```

The interpretation of this metric depends on the time period represented by the Hub Capacity field.

### Driver Delay Rate

The percentage of a driver's orders that were delayed.

```
Driver Delay Rate = Delayed Orders by Driver / Total Orders by Driver
```

### Vehicle Age

The age of a vehicle calculated from its purchase date and the selected reference date.

```
Vehicle Age = Reference Date - Purchase Date
```

## Data Model

The project is based on four main operational tables:

### Orders

Contains order-level delivery records and operational outcomes.

Important fields include:

- Order ID

- Order Date

- Actual Delivery Date

- Order Status

- Delay Reason

- Is Delayed

- Is On Time

- Driver ID and Driver Name

- Hub Name

- Vehicle Name and Vehicle Type

- Customer Satisfaction Score

- Delivery Time Hours

- Hub Processing Time Hours

### Hubs

Contains hub master data and operational capacity.

Important fields include:

- Hub ID

- Hub Name

- Hub Capacity

### Drivers

Contains driver master data and workforce attributes.

Important fields include:

- Driver ID

- Driver Name

- Employment Type

- Hire Date

- Experience Years

- Performance Rating

### Vehicles

Contains vehicle master data and fleet reliability information.

Important fields include:

- Vehicle ID or Vehicle Code

- Purchase Date

- Vehicle Model

- Vehicle Type

- Vehicle Status

- Breakdown Count

- Maintenance Count or Maintenance Alert

## Tools and Technologies

- Microsoft Power BI

- Power Query

- Interactive visuals, slicers, and dashboard navigation

- DAX measures and calculated columns

- Data cleaning and transformation

- KPI design and dashboard visualization

## Data Preparation Workflow

The project follows a repeatable data preparation process:

1. Import the four raw logistics files into Power BI.

1. Load the source tables through Power Query.

1. Standardize column names and data types.

1. Validate identifiers such as Order ID, Driver ID, Hub ID, and Vehicle ID.

1. Check for duplicates, missing values, and inconsistent categories.

1. Create date, month, and year fields for time-based analysis.

1. Calculate operational indicators such as delay status, on-time status, vehicle age, utilization, and month-over-month changes.

1. Load the transformed data into the Power BI data model.

1. Create DAX measures, calculated columns, visuals, KPI cards, slicers, and dashboard navigation.

1. Refresh the Power Query connections to update the report when new source data becomes available.

## Project Structure

```
SwiftRoute-Logistics-Dashboard/
│
├── README.md
├── dashboard/
│   └── SwiftRoute_Logistics_Dashboard.pbix
├── data/
│   ├── hubs.xlsx
│   ├── drivers.xlsx
│   ├── orders.xlsx
│   └── vehicles.xlsx
├── documentation/
│   ├── BusinessRequirements.docx
│   └── DomainKnowledge.docx
└── screenshots/
    ├── executive-overview.png
    ├── hubs-overview.png
    ├── drivers-overview.png
    └── vehicles-overview.png
```

The repository structure may be expanded as additional dashboard screenshots, cleaned datasets, and documentation are added.

## How to Use the Dashboard

1. Download or clone the repository.

1. Open the Power BI report file in Microsoft Power BI Desktop.

1. Enable data source permissions if Power BI displays a security prompt.

1. Refresh the Power Query connections from the **Home > Refresh** option.

1. Select the required year and month using the dashboard filters.

1. Navigate between the Executive, Hubs, Drivers, and Vehicles views.

1. Review the KPI cards, charts, rankings, and detailed breakdowns.

## Data Quality Considerations

The quality of the dashboard depends on the quality of the source data. Before using the dashboard for operational decisions, validate the following:

- Order IDs should be unique for unique deliveries.

- Dates should use a consistent date format.

- Order status values should be standardized.

- Cancelled orders should be handled consistently in delivery KPIs.

- Customer satisfaction scores should use a consistent rating scale.

- Hub capacity should have a clearly defined time period.

- Vehicle breakdowns and maintenance records should use consistent definitions.

- Missing Driver, Hub, or Vehicle IDs should be investigated before reporting.

## Project Assumptions

- The dataset is structured for logistics performance analysis.

- The selected month is compared with the immediately preceding month.

- On-time delivery is based on the `Is On Time` field or an equivalent business rule.

- Delayed delivery is based on the `Is Delayed` field or an equivalent business rule.

- Cancelled orders are excluded from delivery-performance calculations unless otherwise specified.

- Vehicle age is calculated from the purchase date and a defined reference date.

- Hub capacity is assumed to use the same reporting period as processed orders.

- The dataset may be synthetic or anonymized and should not be treated as confidential operational reporting without validation.

## Business Value

The dashboard supports several operational decisions:

- Monitoring monthly delivery performance.

- Identifying hubs that may be over capacity.

- Improving workload distribution across hubs.

- Identifying drivers who may benefit from coaching or additional training.

- Tracking customer experience through satisfaction scores.

- Evaluating vehicle utilization and reliability.

- Supporting maintenance and fleet replacement planning.

- Detecting operational trends and recurring causes of delay.

## Limitations

- Dashboard results are limited to the fields and reporting period available in the source data.

- Correlation between driver experience and performance does not prove causation.

- A high delay rate based on a small number of orders may be unstable.

- Total vehicle breakdowns do not necessarily measure the severity or duration of each breakdown.

- Hub utilization depends on the accuracy and time definition of the Hub Capacity field.

- Month-over-month comparisons may be affected by seasonality, holidays, unusual events, or changes in order volume.

## Portfolio Note

This project demonstrates the ability to translate a logistics business problem into a structured Power BI analytics solution. It combines data preparation, business KPI definition, operational analysis, DAX modeling, and interactive dashboard design.

## Author

**Ahmed Ayman Ahmed Thabet**

- LinkedIn: [https://www.linkedin.com/in/ahmed-ayman-551202241?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app](https://www.linkedin.com/in/ahmed-ayman-551202241?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)

- GitHub: [https://github.com/Ahmed24689](https://github.com/Ahmed24689)

- Email: [ahmedayman1332003@gmail.com](mailto:ahmedayman1332003@gmail.com)