# Cloud-Sorting-Large-Dataset
Sorting of Large dataset (100 GB) using Shared Memory, Hadoop and Spark 

<h3>1. SHARED MEMORY SORT:</h3>
<ul>
<li>The main aim of this code is to perform sorting on large datasets, considering this I have opted for Quick Sort and k-way external merge sort.<br/></li>
<li>The program performs sorting for 1GB and 10GB datasets, where key is of 10 Bytes and value of 90 Bytes.</li>
<li>Sorting is performed based on the key’s ASCII value. <br/></li>
<li>I have divided the original dataset into 80 Chunks and applied Quick Sort on these chunks, which provides me with sorted chunks as output. This part of the program has threads applied to it to parallelize the process of sorting. <br/></li>
<li>Then using k-way external merge sort, I have merged all the Sorted Chunks of earlier phase into a final sorted output file.</li>
</ul>

<h3>2. HADOOP SORT:</h3>
<ul>
<li>Here, I have used Hadoop’s Map-Reduce based implementation to sort large datasets.<br/></li>
<li>Hadoop has a Sort and Shuffle phase, which does the Sorting of data internally, without writing any code particularly for sort.<br/></li>
<li>I have utilized the same in my code, I have provided the <strong>mapper</strong> with input as key (10 Bytes) and value(90 Bytes), the <strong>Sort and Shuffle</strong> phase will categorize the data and sort them according to its Key.</li>
<li>The <strong>reducer</strong> here just has to do the work of emitting the output given by the Sort and Shuffle phase, hence I have used the Identity reducer which will perform the same job as reducer here will.</li>
<li>I have tested the performance of hadoop on 1-Node (1GB, 10GB) and 16-Node (100GB).</li>
</ul>

<h3>3. SPARK SORT:</h3>
<ul>
<li>The code for spark is written using spark shell, which uses Scala as a programming language.</li>
<li>Spark also uses the same Map-Reduce based implementation as Hadoop does.</li>
<li>When installing Spark it installs various features and language packages, like Scala, R-Studio, Python, specifically for Spark.</li>
<li>I have implemented sorting using scala’s sortByKey(), functionality, which sorts the data based on Key value (10 Bytes). The sorted data obtained using spark, is divided into chunks.</li>
<li>I have also implemented the same using Python programming and PySpark package.</li>
</ul>
