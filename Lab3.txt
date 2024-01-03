statistics :: [(Int,Int)] -> (Int,Int,Int,Int,Int)
statistics xs = (totalMatches, totalPoints, totalGoalsScored, totalGoalsConceded, bestGoalDiff)
    where
        totalMatches       = length xs
        -- we just have to map each result to the point system: 3 if more goals, 0 if less goals, 1 if eq goals.
        totalPoints        = sum $ map (\(x,y) -> if x > y then 3 else if x < y then 0 else 1) xs
        totalGoalsScored   = sum $ map fst xs
        totalGoalsConceded = sum $ map snd xs
        -- since maximum returns bottom on empty lists, we need a guard.
        bestGoalDiff       = if null xs then 0 else maximum $ map (uncurry (-)) xs 

partition :: String -> [[String]]
-- partition' also yields the whole string, which doesn't really work since it has length 1, instead of 2 or more.
partition ss = init $ partition' ss

partition' :: String -> [[String]]
partition' [s]    = [[[s]]]
-- Better seen with an example, lets say we are calculating "band", then the iterations will look like this:
-- d
-- [n,d], [nd]
-- [a,n,d], [an,d], [a,nd], [and]
-- [b,a,n,d], [ba,n,d], [b,an,d], [ban,d], [b,a,nd], [ba,nd], [b,and], [band]
-- that is: we either append a new letter to the beggining of each list, or we combine it with the first element of each list.
partition' (s:ss) = map ([s] :) p' ++ map (\(x:xs) ->(s:x):xs) p'
    where
        p' = partition' ss