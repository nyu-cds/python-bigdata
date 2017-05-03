---
layout: page
title: Setup
permalink: /setup/
---
Download Apache Spark from [here](https://spark.apache.org/downloads.html). Make sure you have at least version 2.1.1.

### Mac and Linux

Uncompress and untar the archive, then move it to a known location such as `/home/<user>/spark` or `/Users/<user>/spark`. We'll refer to
this location as `_path_to_spark_` below.

Set your path with a command like the following:

~~~
PATH=$PATH:/_path_to_spark_/bin
~~~
{: .bash}

### Windows

Uncompress and untar the archive (you may need WinZip or another utility for this), then move it to a known location such as 
`C:\Users\<user>\spark`. We'll refer to this location as `_path_to_spark_` below.

Download the [winutils.exe]({{ page.root }}/files/winutils.exe) program and place it in `C:\winutils\bin`.

Set the following variables:

~~~
set SPARK_PATH=C:\_path_to_spark_\spark
set PATH=%PATH%;%SPARK_PATH%\bin;C:\winutils\bin
set HADOOP_HOME=C:\winutils
set _JAVA_OPTIONS="-Xmx512M"
~~~
{: .bash}

### All Operating Systems

Check that Spark is installed correctly by running the command:

~~~
run-example SparkPi 10
~~~
{: .bash}

To run Spark interactively in a Python interpreter, use `pyspark`:

~~~
pyspark --master local[2]
~~~
{: .bash}

PySpark will automatically create a SparkContext for you to work with using the local Spark configuration. You can check that Spark is loaded using
the following command:

~~~
print(sc)
~~~
{: .python}

This should display output like:

~~~
<pyspark.context.SparkContext object at 0x10b47fbd0>
~~~
{: .output}

Once you are running `pyspark`, you can open Spark UI by pointing your browser at [http://localhost:4040/](http://localhost:4040/).

> ### If you are seeing lots of `INFO` and `WARNING` messages
> To reduce the verbose output from Spark, you can do the following:
> 
> Copy `/_path_to_spark_/conf/log4j.properties.template` to `/_path_to_spark_/conf/log4j.properties` (`\_path_to_spark\conf` for Windows). 
> Edit the file and change the line:
> 
> ~~~
> log4j.rootCategory=INFO, console
> ~~~
> {: .python}
> 
> to
> 
> ~~~
> log4j.rootCategory=ERROR, console
> ~~~
> {: .python}
{: .callout}