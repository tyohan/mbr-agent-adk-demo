## Monthly Business Report Agent Demo with ADK
This is a demo of Monthly Business Report Agent using Google ADK. It use the combination of LLM agent for data collection then put it together with analysis agent through sequential workflow to generate the final report.


### How to run

1. Clone this repository
2. Install dependencies `go mod tidy`
3. Run the demo `go run main.go`

### Execution output:

```bash
USER: Please generate the Monthly Business Report for October 2024.

--- Workflow Agent Running ---
[Collector] Calling Tool: find_files Args: map[pattern:*.csv]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:ads_cost.csv start_row:0]
[Collector] Calling Tool: read_columns Args: map[columns:[date cost impressions clicks] file_name:ads_cost.csv]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:coupons.csv start_row:0]
[Collector] Calling Tool: read_columns Args: map[columns:[code discount_percentage] file_name:coupons.csv]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:daily_sales.csv start_row:0]
[Collector] Calling Tool: read_columns Args: map[columns:[date product_name revenue quantity] file_name:daily_sales.csv]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:daily_stock.csv start_row:0]
[Collector] Calling Tool: read_columns Args: map[columns:[date product_id stock_level] file_name:daily_stock.csv]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:market_trends.csv start_row:0]
[Collector] Calling Tool: read_rows Args: map[end_row:1 file_name:website_traffic.csv start_row:0]
[Collector] Calling Tool: read_columns Args: map[columns:[date visits unique_visitors] file_name:website_traffic.csv]
[Collector] Output: Here is the collected data for the Monthly Busines...
[Collector] Output: ```
[
  {"date": "2024-10-01", "cost": "50.00", "i...
[Collector] Output: 

**Coupons Data:**
...
[Collector] Output: ```
[
  {"code": "WELCOME10", "discount_percentage...
[Collector] Output: 

**Sales Data:**
...
[Collector] Output: ```
[
  {"date": "2024-10-01", "product_name": "Er...
[Collector] Output: 

**Stock Data:**
...
[Collector] Output: ```
[
  {"date": "2024-10-01", "product_id": "P001...
[Collector] Output: 

**Traffic Data:**
...
[Collector] Output: ```
[
  {"date": "2024-10-01", "visits": "1500", "...
[Analyst] Output: Of course. As a Senior Business Analyst, I have an...

================================================
FINAL REPORT
================================================

  Here is the collected data for the Monthly Business Report for October 2024:                    
                                                                                                  
  **Ads Data:**                                                                                   
                                                                                                  
    [                                                                                             
      {"date": "2024-10-01", "cost": "50.00", "impressions": "5000", "clicks": "100"},            
      {"date": "2024-10-01", "cost": "40.00", "impressions": "4000", "clicks": "80"},             
      {"date": "2024-10-02", "cost": "55.00", "impressions": "5500", "clicks": "110"},            
      {"date": "2024-10-02", "cost": "42.00", "impressions": "4200", "clicks": "85"},             
      {"date": "2024-10-03", "cost": "45.00", "impressions": "4500", "clicks": "90"},             
      {"date": "2024-10-03", "cost": "60.00", "impressions": "6000", "clicks": "120"},            
      {"date": "2024-10-04", "cost": "70.00", "impressions": "7000", "clicks": "150"},            
      {"date": "2024-10-04", "cost": "50.00", "impressions": "5000", "clicks": "100"},            
      {"date": "2024-10-05", "cost": "80.00", "impressions": "8000", "clicks": "180"},            
      {"date": "2024-10-05", "cost": "65.00", "impressions": "6500", "clicks": "130"}             
    ]                                                                                             
                                                                                                  
  **Coupons Data:**                                                                               
                                                                                                  
    [                                                                                             
      {"code": "WELCOME10", "discount_percentage": "10"},                                         
      {"code": "ERGO20", "discount_percentage": "20"},                                            
      {"code": "DESK15", "discount_percentage": "15"},                                            
      {"code": "FALLSALE", "discount_percentage": "5"}                                            
    ]                                                                                             
                                                                                                  
  **Sales Data:**                                                                                 
                                                                                                  
    [                                                                                             
      {"date": "2024-10-01", "product_name": "ErgoChair", "revenue": "4500", "quantity": "15"},   
      {"date": "2024-10-01", "product_name": "StandingDesk", "revenue": "3200", "quantity": "8"}, 
      {"date": "2024-10-01", "product_name": "MonitorArm", "revenue": "1000", "quantity": "20"},  
      {"date": "2024-10-02", "product_name": "ErgoChair", "revenue": "5400", "quantity": "18"},   
      {"date": "2024-10-02", "product_name": "StandingDesk", "revenue": "4000", "quantity": "10"},
      {"date": "2024-10-02", "product_name": "MonitorArm", "revenue": "1100", "quantity": "22"},  
      {"date": "2024-10-03", "product_name": "ErgoChair", "revenue": "3600", "quantity": "12"},   
      {"date": "2024-10-03", "product_name": "StandingDesk", "revenue": "6000", "quantity": "15"},
      {"date": "2024-10-03", "product_name": "MonitorArm", "revenue": "900", "quantity": "18"},   
      {"date": "2024-10-04", "product_name": "ErgoChair", "revenue": "6000", "quantity": "20"},   
      {"date": "2024-10-04", "product_name": "StandingDesk", "revenue": "4800", "quantity": "12"},
      {"date": "2024-10-04", "product_name": "MonitorArm", "revenue": "1250", "quantity": "25"},  
      {"date": "2024-10-05", "product_name": "ErgoChair", "revenue": "7500", "quantity": "25"},   
      {"date": "2024-10-05", "product_name": "StandingDesk", "revenue": "8000", "quantity": "20"},
      {"date": "2024-10-05", "product_name": "MonitorArm", "revenue": "1500", "quantity": "30"}   
    ]                                                                                             
                                                                                                  
  **Stock Data:**                                                                                 
                                                                                                  
    [                                                                                             
      {"date": "2024-10-01", "product_id": "P001", "stock_level": "100"},                         
      {"date": "2024-10-01", "product_id": "P002", "stock_level": "50"},                          
      {"date": "2024-10-01", "product_id": "P003", "stock_level": "200"},                         
      {"date": "2024-10-02", "product_id": "P001", "stock_level": "85"},                          
      {"date": "2024-10-02", "product_id": "P002", "stock_level": "42"},                          
      {"date": "2024-10-02", "product_id": "P003", "stock_level": "180"},                         
      {"date": "2024-10-03", "product_id": "P001", "stock_level": "73"},                          
      {"date": "2024-10-03", "product_id": "P002", "stock_level": "27"},                          
      {"date": "2024-10-03", "product_id": "P003", "stock_level": "162"},                         
      {"date": "2024-10-04", "product_id": "P001", "stock_level": "53"},                          
      {"date": "2024-10-04", "product_id": "P002", "stock_level": "15"},                          
      {"date": "2024-10-04", "product_id": "P003", "stock_level": "137"},                         
      {"date": "2024-10-05", "product_id": "P001", "stock_level": "28"},                          
      {"date": "2024-10-05", "product_id": "P002", "stock_level": "5"},                           
      {"date": "2024-10-05", "product_id": "P003", "stock_level": "107"}                          
    ]                                                                                             
                                                                                                  
  **Traffic Data:**                                                                               
                                                                                                  
    [                                                                                             
      {"date": "2024-10-01", "visits": "1500", "unique_visitors": "1200"},                        
      {"date": "2024-10-01", "visits": "500", "unique_visitors": "400"},                          
      {"date": "2024-10-01", "visits": "300", "unique_visitors": "250"},                          
      {"date": "2024-10-02", "visits": "1600", "unique_visitors": "1300"},                        
      {"date": "2024-10-02", "visits": "550", "unique_visitors": "450"},                          
      {"date": "2024-10-02", "visits": "320", "unique_visitors": "270"},                          
      {"date": "2024-10-03", "visits": "1450", "unique_visitors": "1150"},                        
      {"date": "2024-10-03", "visits": "480", "unique_visitors": "390"},                          
      {"date": "2024-10-03", "visits": "350", "unique_visitors": "300"},                          
      {"date": "2024-10-04", "visits": "1800", "unique_visitors": "1500"},                        
      {"date": "2024-10-04", "visits": "700", "unique_visitors": "600"},                          
      {"date": "2024-10-04", "visits": "400", "unique_visitors": "350"},                          
      {"date": "2024-10-05", "visits": "2000", "unique_visitors": "1700"},                        
      {"date": "2024-10-05", "visits": "800", "unique_visitors": "700"},                          
      {"date": "2024-10-05", "visits": "500", "unique_visitors": "450"}                           
    ]                                                                                             
    ```Of course. As a Senior Business Analyst, I have analyzed the provided data and synthesized 
  the findings into a comprehensive business report.                                              
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **Monthly Business Report: October 2024**                                                 
                                                                                                  
    **Date of Report:** November 1, 2024                                                          
    **Reporting Period:** October 1, 2024 - October 5, 2024                                       
    **Prepared by:** Senior Business Analyst                                                      
                                                                                                  
    **Disclaimer:** This report is based on an analysis of the data from the first five days of   
  October 2024. The trends and figures represent an early-month snapshot and should be            
  extrapolated with caution.                                                                      
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **1. Executive Summary**                                                                  
                                                                                                  
    The first week of October has shown a strong start, characterized by robust sales growth and  
  increasing website traffic. Total revenue for the period reached **$58,750**, driven primarily  
  by our two flagship products: the **ErgoChair** and the **StandingDesk**. Marketing efforts     
  appear effective, with a clear positive correlation between daily advertising clicks and sales  
  revenue.                                                                                        
                                                                                                  
    However, this strong sales momentum has created a critical challenge: **inventory levels for  
  our top-performing products are dangerously low**. The StandingDesk (P002) is projected to go   
  out of stock within a day, and the ErgoChair (P001) is not far behind. This situation poses an  
  immediate and significant risk to our revenue stream for the remainder of the month.            
                                                                                                  
    Key recommendations for November focus on immediate inventory replenishment, optimizing       
  advertising spend to support in-stock products, and implementing a promotional strategy to      
  leverage lower-performing items while high-demand products are restocked.                       
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **2. Key Performance Indicators (KPIs)**                                                  
                                                                                                  
    The business demonstrated strong performance across key metrics in the first week of the month.
                                                                                                  
    | Metric | Total for Period (Oct 1-5) | Daily Average | Trend |                               
    | :--- | :--- | :--- | :--- |                                                                 
    | **Total Revenue** | $58,750 | $11,750 | **Strongly Increasing** |                           
    | **Total Units Sold** | 270 | 54 | **Increasing** |                                          
    | **Website Visits** | 13,250 | 2,650 | **Increasing** |                                      
    | **Total Ad Spend** | $557 | $111.40 | **Increasing** |                                      
    | **Total Ad Clicks** | 1,145 | 229 | **Increasing** |                                        
    | **Avg. Cost Per Click (CPC)** | $0.49 | - | Stable |                                        
                                                                                                  
    The data indicates a positive daily growth trajectory. Revenue on October 5th ($17,000) was   
  nearly double that of October 1st ($8,700), mirroring a similar increase in website traffic and 
  ad clicks over the same period.                                                                 
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **3. Product Performance Analysis**                                                       
                                                                                                  
    Our core products continue to dominate sales, but the reliance on them is a key risk given    
  current stock levels.                                                                           
                                                                                                  
    **Sales Performance by Product (Oct 1-5):**                                                   
                                                                                                  
    | Product | Total Revenue | % of Total Revenue | Units Sold |                                 
    | :--- | :--- | :--- | :--- |                                                                 
    | **ErgoChair** | $27,000 | 46.0% | 90 |                                                      
    | **StandingDesk** | $26,000 | 44.3% | 65 |                                                   
    | **MonitorArm** | $5,750 | 9.7% | 115 |                                                      
                                                                                                  
    **Key Observations:**                                                                         
                                                                                                  
    *   **Top Performers:** The ErgoChair and StandingDesk collectively account for over 90% of   
  total revenue. Their performance is critical to the business's bottom line.                     
    *   **Volume Driver:** The MonitorArm, while contributing less to revenue, is the highest-    
  selling product by quantity (115 units). This makes it a valuable product for customer          
  acquisition and order up-selling.                                                               
    *   **Growth Trend:** Sales for both the ErgoChair and StandingDesk showed significant growth,
  with quantities sold on October 5th being 67% and 150% higher than on October 1st, respectively.
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **4. Marketing Insights**                                                                 
                                                                                                  
    **Advertising Performance & Sales Correlation:**                                              
    There is a strong positive correlation between advertising efforts and business outcomes. As  
  daily ad spend and clicks increased from October 1st to October 5th, both website visits and    
  total revenue saw a corresponding sharp increase.                                               
                                                                                                  
    *   **October 1st:** $90 Ad Spend -> 180 Clicks -> $8,700 Revenue                             
    *   **October 5th:** $145 Ad Spend -> 310 Clicks -> $17,000 Revenue                           
                                                                                                  
    This suggests our campaigns are effectively driving qualified traffic that converts into sales.
  The average CPC of **$0.49** appears to be a sustainable and effective rate.                    
                                                                                                  
    **Coupon Impact:**                                                                            
    Four promotional codes are currently available: `WELCOME10` (10%), `ERGO20` (20%), `DESK15`   
  (15%), and `FALLSALE` (5%). While direct attribution is not available in the current dataset,   
  the high sales volume of the ErgoChair and StandingDesk suggests that the product-specific      
  coupons (`ERGO20`, `DESK15`) are likely influential drivers of conversion for these items.      
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **5. Inventory/Stock Alerts**                                                             
                                                                                                  
    **This is the most critical area of concern for the business.** Our high sales velocity has   
  led to a rapid depletion of stock for our most profitable products.                             
                                                                                                  
    *Mapping Assumption: P001 = ErgoChair, P002 = StandingDesk, P003 = MonitorArm.*               
                                                                                                  
    | Product ID | Product Name | Stock on Oct 1 | Stock on Oct 5 | Depletion Rate (Avg.          
  Units/Day) | Estimated Stock Remaining (Days) |                                                 
    | :--- | :--- | :--- | :--- | :--- | :--- |                                                   
    | **P002** | **StandingDesk** | 50 | 5 | ~11.3 | **< 1 Day** |                                
    | **P001** | **ErgoChair** | 100 | 28 | ~18.0 | **~1.5 Days** |                               
    | **P003** | **MonitorArm** | 200 | 107 | ~23.3 | **~4.5 Days** |                             
                                                                                                  
    *   **CRITICAL ALERT (P002 - StandingDesk):** With only 5 units remaining and an accelerating 
  sales rate, this product will be out of stock imminently. This represents a potential loss of   
  over $5,200 in daily revenue.                                                                   
    *   **CRITICAL ALERT (P001 - ErgoChair):** A similar situation is developing with the         
  ErgoChair. Stock is projected to last less than two days, risking over $5,400 in average daily  
  revenue.                                                                                        
    *   **HIGH ALERT (P003 - MonitorArm):** While the situation is less dire, the MonitorArm's    
  stock is also depleting quickly and requires attention.                                         
                                                                                                  
    ---                                                                                           
                                                                                                  
    ### **6. Strategic Recommendations for November 2024**                                        
                                                                                                  
    Based on this analysis, the following actions are recommended to mitigate risks and capitalize
  on opportunities:                                                                               
                                                                                                  
    1.  **Immediate Action - Inventory Replenishment (Priority 1):**                              
        *   Initiate emergency purchase orders for **P001 (ErgoChair)** and **P002                
  (StandingDesk)** immediately. Explore expedited shipping options, as the cost will likely be    
  offset by the prevention of lost sales.                                                         
        *   Place a standard restocking order for **P003 (MonitorArm)** to prevent a future       
  stockout.                                                                                       
                                                                                                  
    2.  **Marketing & Sales Pivot (Short-Term):**                                                 
        *   **Pause Ads for Out-of-Stock Products:** Once P001 and P002 are out of stock,         
  immediately pause their dedicated ad campaigns to avoid spending on products customers cannot   
  buy.                                                                                            
        *   **Promote the MonitorArm:** Reallocate the ad budget to a campaign focused on the     
  **MonitorArm** and other in-stock accessories. Create a new promotion, such as "Upgrade Your    
  Workspace," bundled with a unique coupon code.                                                  
        *   **Implement "Notify Me":** Add a "Notify Me When Back in Stock" feature to the        
  ErgoChair and StandingDesk product pages to capture potential sales leads while awaiting        
  inventory.                                                                                      
                                                                                                  
    3.  **Data & Analytics Enhancement:**                                                         
        *   **Integrate Coupon Usage Data:** Update the sales data collection process to include  
  which coupon code was used in each transaction. This will allow for precise measurement of      
  promotion ROI.                                                                                  
        *   **Synchronize Sales and Stock Data:** Investigate and resolve the discrepancies       
  between units sold and stock level depletion to ensure inventory data is 100% accurate for      
  forecasting.                                                                                    
                                                                                                  
    By taking these decisive actions, we can navigate the immediate inventory crisis and set the  
  business up for a successful and profitable November.                                           
  ```