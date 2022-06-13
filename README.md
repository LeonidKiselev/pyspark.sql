## PySpark SQL Quick Start
#### Installing pyspark
    !pip install findspark
    !pip install pyspark
#### Creating SparkSession
    from pyspark.sql import SparkSession
    spark = SparkSession.builder.master('local').appName(`name`).getOrCreate()
    spark
#### Creating DataFrame
    data = <array of tuples>
    schema = <array of strings>
    df = spark.createDataFrame(data=data, schema=schema)
    df.show()
#### Preparing for SQL queries
    df.createOrReplaceTempView(<table name>)
    df.show()
#### Ready for SQL queries
    query = spark.sql('SELECT * FROM <table name>')
    query.show()
Done!
