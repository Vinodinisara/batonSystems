# batonSystems

As part of this application i have created a trading stem as per the below requirement:
Implement a high-frequency Exchange that receives both BUY orders & SELL orders and matches them based on the Symbol, Price and the sequence in which they were received. For each successful match, it creates a "Trade" record between the two parties that includes the two parties (Buyer & Seller) along with attributes such as the Symbol, Price, Trade Date, etc.

 I have assumed these orders are being fed into the Exchange by http call and hence exposed 4 endpoints.
 
 Note: I used h2 in-memory DB for this POC.
 1) Endpoint to input/sell stocks for which the POST URL would be - http://localhost:8080/v1/sellStocks
        a) This would get the request fields in json format as sellerId, stock and price.
        b) If the stocks are inserted successfully then we would get a success response as "Product sale details completed successfully"
        
 2) Endpoint to buy stocks for which the POST URL would be - http://localhost:8080/v1/buyStocks
        a) If the sell stocks are empty then i would receive an error response saying "No stocks available for sale"
        b) If the stocks are available then it would process based on the requirement and would expect an input in json format as buyerId, stock and price.
        c) It would sort as per the tradedate and the first one will get the stock as per the requirement.
      
 3) Endpoint to fetch the stocks based on parties and stock for which the GET URL would be - http://localhost:8080/v1/trade/{supplierId}/{buyerId}/{symbol}
        E.g.  http://localhost:8080/v1/trade/Party A/Party B/GOOGLE
 4) Endpoint to fetch the stocks based on stocks and price for which the GET URL would be - http://localhost:8080/v1/trade/{symbol}/{price}
        E.g. http://localhost:8080/v1/trade/GOOGLE/500
        
        
 I have also committed the postman collection that i used for testing for your reference.
