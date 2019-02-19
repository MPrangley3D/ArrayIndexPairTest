# ArrayIndexPairTest
Language: C#

This question was pretty insane on the front-end:

A 'pair' was defined as any set of 2 array index values that shared a value

example:  [3,5,3,6,7,5] would have potential pairs:  (0,2) (1,5) (2,0) (5,1)

Those pairs were then further refuned as follows:  0 <= P < Q < N

Where P was the first element, Q was the 2nd element, and N was the length of the array

So, from the example, the "valid pairs" would be: (0,2) (1,5)

THEN return the count of the number of valid pairs seen.



I wanted a super memory perfomant option, so my mind went immediately to hash tables and dictionary structures.  

The limitation of dictionaries is the 1:1 relationshjip of the key:value pairs.

I was able to overcome this by storing a HashSet as the value relative to the key, with the key being the value character of the array

This would allow me to: Loop through the array and build this dictionary which stored all index locations a value was seen at

Then additionally I cached the unique values in the array, to expedite the actual work loop

Then I looped through that cache of values, and ran the 0 <= P < Q < N check on each pair that was there to clarify which met the criteria

Finally the counter is returned
