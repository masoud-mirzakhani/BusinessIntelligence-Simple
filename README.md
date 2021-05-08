There is a simple BI project, which includes:
-	Data Source: YourCompany; A Microsoft SQL Server database. YourCompany is a simple database that includes Financial, Sales, Inventory and HR tables.

-	Bus Matrix: An excel file which represents business processes, facts and dimensions based on Kimball Multidimensional modeling. 

-	Gathering Views: Some TSQL scripts creates in YourCompany. Their responsibility is to Extract and Transform source data into desired data structure based on Bus Matrix file. 

-	Data Warehouse: YourCompany_DW; A Microsoft SQL Server database. YourCompany_DW has some tables in MD (Meta Data) schema. MD tables are filled based on Bus Matrix file. They represent facts and dimensions that should be created in DW.

-	Data Warehouse Generator: Some TSQL scripts created in DW. They use MD tables' data to generate DW tables. For a full creation run MD.spGenerateDWStructre stored procedure with NULL parameters.

-	ETL Engine: Some TSQL scripts created in DW. They use MD tables' data to generate ETL scripts. For a full ETL process run ETL.spGatheringData stored procedure with NULL parameters.

-	Auxiliary Scripts: Some TSQL scripts to check your meta data or compare it to Gathering views.
