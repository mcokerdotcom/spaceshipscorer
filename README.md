Spaceship Scorer
----------------

At the Intergalactic Space Race, spaceships from across the galaxy compete to determine which spaceship is the fastest. To score the race, the Intergalactic Space Race Association (ISRA) uses the following algorithm:

Each spaceship S is given a score equal to the number of other spaceships who both started after and finished before S.

Note that lower scores indicate a faster spaceship.  The ISRA likes this system because it does not penalize fast ships that were slowed down because they were stuck behind a slow spaceship. Additionally, the algorithm does not reward fast spaceships who passed many slow competitions in comparison to fast spaceships who race when there are not so many slow competitors on the track to pass.

The ISRA has hired you to implement this scoring algorithm.  Given the log of spaceships with their start and end times, your task is to output the score for each spaceship.

Input format
----------------

The first line of input will contain the number of spaceships competing. After that, there will be one line per spaceship in the following format:

spaceshipId startTime endTime

Notes on input:
* The number of spaceships will be an integer from 0 to 70,000
* spaceshipId will be an integer in the range [0, 10^9]
* startTime and endTime are both integers that satisfy 0 < startTime < endTime < 10^18
* spaceshipId is distinct 
* Start and end times (taken as a whole) will not contain any duplicate elements.  If a racer has a start time of x, then no other start or end time will also equal x.
* The fields are space delimited

Output Format
----------------

Given the input, your task is to output a score for each spaceship in the following format:

spaceshipId score

With score as defined above.  The output lines should be sorted in ascending order. The sorting can be accomplished with a simple sort at the end.

Sample Input and Output
-----------------------

Input:
5
2 100 200
3 110 190
4 105 145
1 90 150
5 102 198

Output:
3 0
4 0
1 1
5 2
2 3

Note that in the above example spaceship 3 has a score of 0 because no one starts after spaceship 3 (a drawback to this scoring system is the last spaceship always has a score of 0). Spaceship 4 also has a score of 0 because the only racer who starts after spaceship 4's start time (spaceship 3) has a later finish time. Spaceship 3 is listed ahead of spaceship 4 despite having a slower time because spaceship 3's id is lower.  At the other end, spaceship 2 has a score of 3 because spaceships 3, 4, and 5 start after spaceship 2 and finish before spaceship 2 finished.
