## Question 1
You are given the set of points below:

{(3,7), (5,1), (3, 3), (4, 2), (2, 8)}

(a) What are the bottom-left and top-right corner points of the minimum bounding box (MBB) that encloses all of them?<br>
(b) What is the centre point and radius of the minimum bounding circle (MBC) that encloses all of them?<br>
(c) Which (if any) of the above two objects contains point (4.5, 5.5)?<br>

## Question 2
You are given the following events:

Earthquake Magnitudes
Lat	Long	Day	Magnitude
59.83	-136.70	5 May 2017	6.3
74.39	-92.42	8 Jan 2017	6.0
51.62	-130.77	24 Apr 2015	6.2
60.35	-140.33	17 Jul 2014	6.0
49.64	-127.73	24 Apr 2014	6.5
51.18	-130.23	4 Sep 2013	6.0
51.24	-130.40	3 Sep 2013	6.1
 

(a) Create and show a set of intervals of earthquake activity, one for each 10-degree range of latitudes (e.g., 
earthquakes at [40,50), occurred between [first_date, last_date]).<br>
(b) Construct and show an interval tree from that set of intervals.<br>
(c) Indicate which path in the tree would be traversed to find the date 1 Jan 2015 and report which latitude 
ranges/intervals include that date.<br>

## Question 3
You are given the following multidimensional data:

Hockey Player Statistics
Name	Goals	Assists
Kucherov	41	87
McDavid	41	75
Kane	44	66
Draisaitl	50	55
Marchand	36	64
Crosby	35	65
MacKinnon	41	58
Gaudreau	36	63
Stamkos	45	53
Barkov	35	61
 

(a) Create a quad tree with goals on the x-axis and assists on the y-axis. You can assume that the data space only ranges 
from [35, 50] goals and [50,90] assists.<br>
(b) Create a binary tree of minimum bounding boxes (as in the lecture notes)<br>
(c) How many point-to-point comparisons are required to traverse each of the structures that you created above in order 
to identify which player has obtained 41 goals and 58 assists?<br>
(d) Given a partitioning of the data space ([35,50], [50,90]) into 16 evenly-sized cells, what is the z-order of each 
player?<br>
