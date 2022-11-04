---
uid: "contribution/xyz-pointcloud-reducer"
uid-meta: "contribution/xyz-pointcloud-reducer-meta"
comments: 
 items: 
  - uid: "233450"
  - uid: "233454"
  - uid: "233505"
  - uid: "233654"
  - uid: "233722"
  - uid: "233750"
  - uid: "233806"
  - uid: "233820"
  - uid: "233821"
  - uid: "233846"
  - uid: "233848"
uid-files: "contribution/xyz-pointcloud-reducer-files"
title: "XYZ Pointcloud reducer"
image: "sample_screenshot.jpg"
contribution: "true"
---

Did you ever needed to reduce the size of a point-cloud file without reducing the point count? 

I've made this tool which shrinks the text file by removing arbitrary amount of fraction point digits, decreasing the precision as well.  

####  Example:
<div class="box">
Before:
12.137491 6.127559 0.303001 48 47 50

After:
12.13 6.12 0.30 48 47 50
</div>


####  Usage:
~np~ XYZPointcloudReduce <-n:0..9> input_file output_file
~/np~

####  Mandatory arguments:
~np~ input_file Input point-cloud file containing space separated values as strings. Supported formats: ASC, XYZ, etc. input_file Output point-cloud file containing space separated values as strings. ~/np~


####  Optional arguments:
~np~ -n:0..9 Specify the count of digits after decimal point, lower number results in lower file size. Default value is 3. ~/np~

####  Source code:
<https://github.com/id144/XYZPointcloudReduce>