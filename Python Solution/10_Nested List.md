# 010 - Nested Lists
## Problem
Given the names and grades for each student in a Physics class of `N` students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade.

**Note**: If there are multiple students with the same grade, order their names alphabetically and print each name on a new line.

#### Input Format

The first line contains an integer, `N`, the number of students.

The `2N` subsequent lines describe each student over `N` lines; the first line contains a student's name, and the second line contains their grade.


#### Constraints
2 <= N <= 5

There will always be one or more students having the second lowest grade.

#### Output Format

Print the name(s) of any student(s) having the second lowest grade in Physics; if there are multiple students, order their names alphabetically and print each one on a new line.

```
Sample Input :
5
Harry
37.21
Berry
37.21
Tina
37.2
Akriti
41
Harsh
39
```

```
Sample Output :
Berry
Harry
```

#### Explanation
There are 5 students in this class whose names and grades are assembled to build the following list:

`python students = [['Harry', 37.21], ['Berry', 37.21], ['Tina', 37.2], ['Akriti', 41], ['Harsh', 39]]`

The lowest grade of 37.2 belongs to Tina. The second lowest grade of 37.21 belongs to both Harry and Berry, so we order their names alphabetically and print each name on a new line.


#### Given Code

```python
if __name__ == '__main__':
    for _ in range(int(input())):
        name = input()
        score = float(input())
```


## Solution

```python
if __name__ == '__main__':
    
    score_list = []
    total_list = []
    name_list = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        
        score_list.append(score)
        total_list.append([name,score])
        
    lowest = sorted(set(score_list))
    #print(lowest[1])
    
    for name, score in total_list:
        if score == lowest[1]:
            name_list.append(name)
            
    name_list.sort()
    #print(name_list) 
    for i in name_list:
        print(i)   
    #print(score_list)
    #print(total_list)


```
Explanation:
1) Fisrt we append the score into score_list[] and append name and score into total_list[].
2) To find the second lowest first we sort the list in ascending order then by using indexing lowest[1] find the second lowest element.
3) Once we get lowest score we need to find name of students who have that lowest score for that purpose use for loop to iterate through total_list containing both name and score.
4) If this condition if score == lowest[1]: is true then we append the name in new name_list
5) by iterating through this name list we get out students haveing second lowest score.
