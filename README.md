EXERCISE 1
The results of a football team's matches during the league can be represented as a list of even pairs. Each pair represents the result of a match, where the first element of the pair corresponds to the goals scored by the team and the second element to the goals conceded by the opposing team in that match. Given a list that includes the results of a team in the league, we want to construct a five-digit number that describes the following team statistics:
• the total number of matches played
• the total points he has earned, given that for every win he earns three points and for every draw one point
• the total number of goals scored
• the total number of goals conceded
• the goal difference in the best result he has brought. This difference will be positive if the team has achieved at least one victory, zero if it has not achieved a victory but has
at least one draw and a negative if lost in all matches. Write a statistics function in Haskell, which will take as an argument the list of results of a group and return a five integers with the statistics described above. The type of the function should be [(Int, Int)] -> (Int, Int, Int, Int, Int). If the list is empty, then the top five (0,0,0,0,0) must be returned. You can assume that the list is finite and that each pair in the list consists of two non-negative numbers (ie the list contains only valid results). There is no limit to the number of goals a team can score in a match, nor to the length of the list.
Use the following values to check:
Main> statistics []
(0,0,0,0,0)
Main> statistics [(1,5)]
(1,0,1,5,-4)
Main> statistics [(0,1),(1,3),(1,2)]
(3,0,2,6,-1)
Main>statistics [(3,1),(5,2),(7,0)]
(3,9,15,3,7)
Main> statistics [(1,1),(2,2),(4,4)]
(3,3,7,7,0)
Main> statistics [(8,1),(2,3),(3,3),(2,0)]
(4,7,15,7,7)
Main> statistics [(0,4),(2,2),(2,3),(0,0)]
(4,2,4,9,0)
Main> statistics [(1,1),(3,0),(0,2),(4,3),(7,1),(3,3),(1,4),(2,1)]
(8,14,21,15,6)

EXERCISE 2
We call the partition of a string w any sequence consisting of two or more non-empty strings z1, z2,. . . , zk (k ≥ 2), the union of which is w. Write a partition function in Haskell, which will take as its argument a string w and return a list of all w partitions. Each partition of w is represented as a list of strings. The type of the function should be String -> [[String]]. Use the following values to check (the order of the partitions in the list may be different from that shown in the results, however the order of the strings in each internal list should be the same):
Main> partition "on"
[["o","n"]]
Main> partition "sun"
[["s","un"],["s","u","n"],["su","n"]]
Main> partition "band"
[["b","and"],["b","a","nd"],["ba","nd"],["b","a","n","d"],["ba","n","d"],
["b","an","d"],["ban","d"]]
Main> partition "crazy"
[["c","razy"],["c","r","azy"],["cr","azy"],["c","r","a","zy"],["cr","a","zy"],
["c","ra","zy"],["cra","zy"],["c","r","a","z","y"],["cr","a","z","y"],
["c","ra","z","y"],["cra","z","y"],["c","r","az","y"],["cr","az","y"],
["c","raz","y"],["craz","y"]]
Main> partition "a"
[]
Main> length (partition "abcdefghijklmn")
8191

Instructions
1)	To write the functions you need to use the standard Lab2.hs file in which the type statements of the functions you need to construct are ready as well as an equation that defines the functions so that they return a predefined value for all values of the arguments. To answer an exercise you can replace the above equation with the appropriate equations that define the value of the function. You do not need to modify the type or name of the function.
2)	if you use import to embed ready-made code, the corresponding exercise will not be graded.
3)	Each of the functions that you are asked to implement should have the specific name and the specific type that is described in the pronunciation of the corresponding exercise and that exists in the standard file Lab2.hs. If in some exercise the name or type of function does not match the one given in the pronunciation, the exercise will not be graded.
4)	However, if the functions do not return values for some of the control values (eg they cause stack overflow, endless calculation or some runtime error) then the corresponding exercise will not be graded. If the file you submit contains syntax errors, then the entire lab exercise will be reset.

