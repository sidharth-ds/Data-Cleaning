
## Cleaning_using_Pandas:

- Null values:
    - isnull(); isnull().sum(); fillna(); isna(); notna()
- Drop():
    - dropna(); dropna(how='all'); dropna(how='any'); dropna(axis="columns"); drop_duplicates()
- subset=['']
- Duplicates:
    - duplicated(); duplicated(keep='last'); duplicated(keep=False) 
- filling null values with mean of that column
- replace(_,_)

## Cleaning_using_PySpark:

- !pip install pyspark
- Connecting the Session:
    - import pyspark
    - from pyspark.sql import SparkSession
    - spark = SparkSession.builder.appName('sample').getOrCreate()
- Creating Dataframe using pyspark:
    - spark.createDataFrame(data=,schema=)
- Converting Spark dataframe into Pandas dataframe:".toPandas()"
- Reading a csv file:
    - spark.read.format("csv").load("__")
    - spark.read.option("header",True).csv("__")
- Writing a csv file:
    - df.write.option("header",True).csv("__")
- Duplicates:
    - distinct(); dropDuplicates()
- Filter: filter()
    - == , != , > , < , & , | , isin()
    - startswith(''), endsswith(''), contains(''), like('')
- Connecting Tables:
    - .join( connecting columns ); inner, outer, left, right, ...
    - .union() : to join similar tables (if schema is same)
- Null values:  
    - df.na.fill(value='__').show()
- Sorting:
    - sort('name').show()
    - sort(df_emp1.name.desc()).show() ; asc()
- SQL sorting in pyspark: "from pyspark.sql.functions import col"
    - sort(col("name").asc()).show()
    - orderBy(col("salary").asc()).show()
- groupBy():
    - groupBy("dept_id").sum(("salary")).show()
    - groupBy("dept_id").count().show()
- SQL operations in pyspark:
    - data.createOrReplaceTempView("tablename")
    - spark.sql("select * from tablename").show()
    - spark.sql("select * from tablename order by name asc").show()
    - spark.sql("select * from emp where salary > 12000").show()
- Mapping from pyspark perspective
- JSON file:
    - reading, writing
