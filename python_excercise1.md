## Problem Description

A cricket coach records the performance of his players in every match. He stores their names, runs made by them, wickets taken, and balls played by them in the match. He then needs to calculate their strike rate and then decide which player is to be awarded man of the match.
The strike rate is calculated by dividing the number of runs by the bowls played by the player. Criteria for the man of the match are as follows:

- If strike rate >(greater than) 4 and wickets >(greater than)2: Man of the match

- If strike rate < 4 but >2 and wickets >4: Man of the match

- Return the final records and man of the match.

**Note: The performance which came later in the match and satisfies any one of the conditions for the man of the match will be given the award. The inputs are given in order of the time in the matches. i.e. Arun's performance came before Sanjay in the sample.**


## Input Format

Space Separated values in the order Name Runs Wickets BallsPlayed


## Output Format

True/False based on the dictionary of records returned
Name of player who is Man of the Match


## Example Input

```sh
Arun 25 3 7
Nihal 50 5 12
Sanjay 10 4 3
```

## Expected Output

```sh
({'Arun': [25, 3, 7], 'Nihal': [50, 5, 12], 'Sanjay': [10, 4, 3]}, 'Nihal')
```

The order of the dictionary doesn't matter, hence we are just checking the dictionary you returned with that of the input.

## Platform Output

The platform does some post-processing on your output and converts it to something easy to check with test cases.

In this case, Platform output will be True if the dictionary is correct, and False if it is not correct.

``sh
True
Nihal
```


```
import copy
def man_of_match(names, runs, wickets, bowls):
    '''
    input:
    names -> list of names of the players
    runs -> list of runs of the respective players
    wickets -> list of wickets taken by the respective players
    bowls -> list of bowls by the respective players
    
    output:
    data -> data of the players in dictionary format
    manOfMatch -> name of the man of the match
    '''
    data = {}
    manOfMatch = ""
    # Your code starts here

    for name, run, wkt, bowl in zip(names, runs, wickets, bowls):
        data[name] = [run, wkt, bowl]
        strike_rate = run/bowl
        if strike_rate > 4 and wkt > 2:
            manOfMatch = name
        elif strike_rate < 4 and strike_rate > 2 and wkt > 4:
            manOfMatch = name

    
    # Your code ends here
    return data, manOfMatch
    ```
