---
layout: page
title: Setup
permalink: /setup/
---
Download the latest release of Apache Spark from [here](http://spark.apache.org/downloads.html). This should work with Windows, Linux, and Mac OS X.

Untar and uncompress the archive, then move it to a known location, e.g. `/home/<my_user>/spark` or `/Users/<my_user>/spark`.

Check that Spark is installed correctly by running the command:

~~~
<path_to_spark_installation>/bin/run-example SparkPi 10
~~~
{: .bash}

To run Spark interactively in a Python interpreter, use `pyspark`:

~~~
<path_to_spark_installation>/bin/pyspark --master local[2]
~~~
{: .bash}

PySpark will automatically create a SparkContext for you to work with using the local Spark configuration. We can check that Spark is loaded:

~~~
from spark import sc
print(sc)
<pyspark.context.SparkContext object at 0x10b47fbd0>
~~~
{: .python}
