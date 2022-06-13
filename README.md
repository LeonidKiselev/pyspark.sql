## PySpark SQL Quick Start
#### Installing pyspark
    !pip install findspark
    !pip install pyspark
#### Creating SparkSession
    from pyspark.sql import SparkSession
    spark = SparkSession.builder.master('local[*]').appName(<name>).getOrCreate()
    spark
#### Uploaing DataFrame
    from pyspark.sql.types import *
    schema = [
        StructField(<name>, <type>, True),
        StructField(<name>, <type>, True),
        ...
    ]
    df = spark.read.csv('file.csv', schema=StructType(fields=schema))
    df.show()
#### Preparing for SQL queries
    df.createOrReplaceTempView(<table name>)
    df.show()
#### Ready for SQL queries
    query = spark.sql('SELECT * FROM <table name>')
    query.show()
Done!
