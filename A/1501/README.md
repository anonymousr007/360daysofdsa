# A. Alexey and Train

**Solution:** 

- The solution of this task is to basically implement what was written in the statement.
- Let dep_i be the moment of train departure from the station i (dep_0=0 initially).
- Then train arrives at the current station i at moment ar_i = dep_i − 1 + (a_i − b_i − 1) + tm_i
- Departure at moment dep_i = max(b_i, ar_i + b_i − a_i + 12).
- The answer is ar_n.
