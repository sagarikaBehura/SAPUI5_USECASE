## Context:
An order management system is a software application that automates the entire process of managing orders. It allows you to manage your inventory, sales and customer information in one place, so you can easily access all this data from anywhere at any time.
## Requirement:
Create a master-detail SAPUI5 application for order management process.
### Master Page
 <img width="946" alt="Screenshot 2023-08-27 150957" src="https://github.com/sagarikaBehura/SAPUI5_USECASE/assets/22025248/0db32c97-90ee-4fac-a339-f96a29c5957a">

 * As part of master page you have to create a list which shows basic information about the order.
 * Search need to be implemented.
 * Fiter and groupby need to be implemented.
 * initially list should display 5 entry, on click of show more button other entries need to be loaded.
 * Please refer Sample app [https://ui5.sap.com/test-resources/sap/m/demokit/orderbrowser/webapp/test/mockServer.html?sap-ui-theme=sap_horizon#] to check expected behaviour.

  ### Order JSON Object
```json
[

	{
	"OrderID": 7918,
	"CustomerID": "TORTU",
	"CustomerName": "Tortuga Restaurante",
	"EmployeeID": 7424,
	"OrderDate": "/Date(1474149600000)/",
	"RequiredDate": "/Date(1475186400000)/",
	"ShippedDate": "/Date(1474840800000)/",
	"ShipVia": 6030,
	"Freight": 7948.67,
	"ShipName": "ExcellentParcel",
	"ShipAddress": "Tottenham Court Road",
	"ShipCity": "London",
	"ShipRegion": "Greater London",
	"ShipPostalCode": "N170AA",
	"ShipCountry": "United Kingdom"
  },
  {
	"OrderID": 7311,
	"CustomerID": "ALFKI",
	"CustomerName": "Alfreds Futterkiste",
	"EmployeeID": 7827,
	"OrderDate": "/Date(1479682800000)/",
	"RequiredDate": "/Date(1481151600000)/",
	"ShippedDate": "/Date(1480028400000)/",
	"ShipVia": 3416,
	"Freight": 7624.42,
	"ShipName": "ExcellentParcel",
	"ShipAddress": "Tottenham Court Road",
	"ShipCity": "London",
	"ShipRegion": "Greater London",
	"ShipPostalCode": "N170AA",
	"ShipCountry": "United Kingdom"
  },
  {
	"OrderID": 7375,
	"CustomerID": "AROUT",
	"CustomerName": "Around the Horn",
	"EmployeeID": 7424,
	"OrderDate": "/Date(1475704800000)/",
	"RequiredDate": "/Date(1479337200000)/",
	"ShippedDate": "/Date(1476396000000)/",
	"ShipVia": 7532,
	"Freight": 4019.56,
	"ShipName": "ExcellentParcel",
	"ShipAddress": "Tottenham Court Road",
	"ShipCity": "London",
	"ShipRegion": "Greater London",
	"ShipPostalCode": "N170AA",
	"ShipCountry": "United Kingdom"
  },
  {
	"OrderID": 6189,
	"CustomerID": "BERGS",
	"CustomerName": "Berglunds snabbköp",
	"EmployeeID": 7829,
	"OrderDate": "/Date(1480287600000)/",
	"RequiredDate": "/Date(1482274800000)/",
	"ShippedDate": "/Date(1480460400000)/",
	"ShipVia": 1923,
	"Freight": 5422.26,
	"ShipName": "1A Paket- und Lieferservice",
	"ShipAddress": "Bismarckstraße 5",
	"ShipCity": "Berlin",
	"ShipRegion": "Berlin",
	"ShipPostalCode": "10179",
	"ShipCountry": "Deutschland"
  },
  {
	"OrderID": 3115,
	"CustomerID": "BERGS",
	  "CustomerName": "",
	"EmployeeID": 7830,
	"OrderDate": "/Date(1480806000000)/",
	"RequiredDate": "/Date(1480978800000)/",
	"ShippedDate": "/Date(1482447600000)/",
	"ShipVia": 3059,
	"Freight": 9130.44,
	"ShipName": "1A Paket- und Lieferservice",
	"ShipAddress": "Bismarckstraße 5",
	"ShipCity": "Berlin",
	"ShipRegion": "Berlin",
	"ShipPostalCode": "10179",
	"ShipCountry": "Deutschland"
  },
  {
	"OrderID": 2686,
	"CustomerID": "BOTTM",
	"CustomerName": "Bottom-Dollar Markets",
	"EmployeeID": 7840,
	"OrderDate": "/Date(1477519200000)/",
	"RequiredDate": "/Date(1478646000000)/",
	"ShippedDate": "/Date(1477954800000)/",
	"ShipVia": 4728,
	"Freight": 8237.06,
	"ShipName": "1A Paket- und Lieferservice",
	"ShipAddress": "Bismarckstraße 5",
	"ShipCity": "Berlin",
	"ShipRegion": "Berlin",
	"ShipPostalCode": "10179",
	"ShipCountry": "Deutschland"
  },
  {
	"OrderID": 6858,
	"CustomerID": "TORTU",
	  "CustomerName": "Tortuga Restaurante",
	"EmployeeID": 7840,
	"OrderDate": "/Date(1478991600000)/",
	"RequiredDate": "/Date(1480460400000)/",
	"ShippedDate": "/Date(1479078000000)/",
	"ShipVia": 6103,
	"Freight": 4097.09,
	"ShipName": "ExcellentParcel",
	"ShipAddress": "Tottenham Court Road",
	"ShipCity": "London",
	"ShipRegion": "Greater London",
	"ShipPostalCode": "N170AA",
	"ShipCountry": "United Kingdom"
  },
  {
	"OrderID": 6368,
	"CustomerID": "ALFKI",
	"CustomerName": "Alfreds Futterkiste",
	"EmployeeID": 7424,
	"OrderDate": "/Date(1478991600000)/",
	"RequiredDate": "/Date(1480460400000)/",
	"ShippedDate": "/Date(1479510000000)/",
	"ShipVia": 9412,
	"Freight": 1858.37,
	"ShipName": "ExcellentParcel",
	"ShipAddress": "Tottenham Court Road",
	"ShipCity": "London",
	"ShipRegion": "Greater London",
	"ShipPostalCode": "N170AA",
	"ShipCountry": "United Kingdom"
  },
  {
	"OrderID": 828,
	"CustomerID": "AROUT",
	"CustomerName": "Around the Horn",
	"EmployeeID": 7829,
	"OrderDate": "/Date(1479682800000)/",
	"RequiredDate": "/Date(1481151600000)/",
	"ShippedDate": "/Date(1480028400000)/",
	"ShipVia": 508,
	"Freight": 2347.15,
	"ShipName": "ShipEx",
	"ShipAddress": "5th Avenue 610",
	"ShipCity": "New York",
	"ShipRegion": "New Jersey",
	"ShipPostalCode": "10020",
	"ShipCountry": "United Stated of America"
  },
  {
	"OrderID": 7991,
	"CustomerID": "BERGS",
	"CustomerName": "Berglunds snabbköp",
	"EmployeeID": 7830,
	"OrderDate": "/Date(1479682800000)/",
	"RequiredDate": "/Date(1481151600000)/",
	"ShippedDate": "/Date(1480028400000)/",
	"ShipVia": 6419,
	"Freight": 6554.71,
	"ShipName": "ShipEx",
	"ShipAddress": "5th Avenue 610",
	"ShipCity": "New York",
	"ShipRegion": "New Jersey",
	"ShipPostalCode": "10020",
	"ShipCountry": "United Stated of America"
  }
]


```
### Detail Page
