<pre>
  Datawarehousing Interview Questions 1
  Venkata Bhattaram / Tinitiate.com
</pre>
<pre>
0) Whats a DataWarehouse ?
A) A DataWarehouse is the cumulative archival of Operationl Data (Historical + Current)
  ,which is transformed (Usually) to suit specific reporting requirements.

1) what are the types of dimension tables?
A) 3 Types
   1) Comfirmed is a table that can be shared by shared by multiple Fact Tables or multiple DataMarts.
   2) Junk Dimensiions collection of flag values of a specific dimension attribute.(Factory, Products Manufactured ..)
      a smaller set of values mapped to small set of values
      
   3) A degenerate dimension is a dimension that is stored in the fact table rather than the dimension table.
      It eliminates the need to join to a Dimension table.

2) What is a Slowly changing Dimension (SCD)
A) Type I
       This method overwrites old with new data, and therefore does not track historical data.
   Type II
       This method tracks historical data by creating multiple records for a given natural key
       in the dimensional tables with separate surrogate keys using different version numbers or
       effective-from and effective-to date values
   Type III
       This method tracks limited historical data by having a current and previous value columns for 
       dimension records.

3) Whats a FACT table
A) A fact table is a set of values which are measurable, Facts are usually numerical values
   that can be aggregated, and dimension foreign keys.

4) Difference between STAR and SNOWFLAKE schema?
A) STAR
   * Implements Dimension Hierarchy in the same table
   * Dimension Tables are Normalized, but Fact Table is De-Normalized
   * Useful design for smaller sized dimension tables.
   
   SNOWFLAKE
   * Implements Dimension hierarchy in multiple tables.
   * Both Dimension and Fact Tables are De-Normalized
   * Use for Larger Size and more complex dimension tables.
     Like Many-Many on dimensions.
     
5) How to perform testing in datawarehouse?
A) All tests are data-centric, hence validating previous (correct data) reports with most recent load data,
   should validate the load.
   
6) What is the difference between Operational Data Store (ODS) and staging area
A) ODS : Contains realtime or near realtime data from various operational databases (OLTP)
   Staging Area: Are a set of tables that hold data from various (OLTP / ODS), where the data is cleaned
   and validated (Staged), from where, its loaded to the DataWarehouse.
   
7) How to handle errors in loads,
A) These can be handled in ERROR Bucket Tables at Staging / FACT / DIMENSION levels.
</pre>
