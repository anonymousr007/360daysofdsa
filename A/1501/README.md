# A. Alexey and Train

**Problem:**

* The train starts from the terminal at the moment 0.
* The train will visit n stations numbered from 1 to n along its way
* Destination is the station n.
* The train schedule n integer pairs (a_i, b_i)
* a_i is the expected time of train's arrival at the i-th station
* b_i is the expected time of departure.
* Calculate n integers tm_1, tm_2, …, tm_n
* tm_i is the extra time the train need to travel from the station i−1 to the station i.
* The train needs exactly a_i−b_i−1+tm_i time to travel from station i−1 to station i
* if i=1 then b_0 is the moment the train leave the terminal, and it's equal to 0.
* The train leaves the station i, if both conditions are met:
* It's on the station for at least ⌈b_i−a_i/2⌉ units of time (division with ceiling)
* Current time >= b_i.

Since Alexey spent all his energy on prediction of time delays, help him to calculate the time of arrival at the station n.

**Input:**

* t (1 <= t <= 100) — the number of test cases.
* single integer n (1 <= n <= 100) — the number of stations.
* Next n lines contain two integers each: a_i and b_i (1 <= a_i < b_i <= 10^6). It's guaranteed that b_i < a_i+1.
* Next line contains n integers tm_1, tm_2, …, tm_n (0 <= tm_i <= 10^6).

**Output:**

* For each test case, print one integer — the time of Alexey's arrival at the last station.

**Solution:** 

* The solution of this task is to basically implement what was written in the statement.
* Let dep_i be the moment of train departure from the station i (dep_0=0 initially).
* Then train arrives at the current station i at moment ar_i = dep_i − 1 + (a_i − b_i − 1) + tm_i
* Departure at moment dep_i = max(b_i, ar_i + b_i − a_i + 12).
* The answer is ar_n.
