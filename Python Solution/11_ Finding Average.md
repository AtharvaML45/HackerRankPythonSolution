# 011 - Finding The Percentage
## Problem

You have a record of `N` students. Each record contains the student's name, and their percent marks in Maths, Physics and Chemistry. The marks can be floating values. The user enters some integer `N` followed by the names and marks for `N` students. You are required to save the record in a dictionary data type. The user then enters a student's name. Output the average percentage marks obtained by that student, correct to two decimal places.

#### Input Format

The first line contains the integer `N`, the number of students. The next `N` lines contains the name and marks obtained by that student separated by a space. The final line contains the name of a particular student previously listed.



#### Constraints

2 <= `N` <= 10
0 <= `Marks` <= 100



#### Output Format

Print one line : The average of the marks obtained by the particular student correct to 2 decimal places.

**Sample Input 0**

```
3
Krishna 67 68 69
Arjun 70 98 63
Malika 52 56 60
Malika
```

**Sample Output 0**

```
56.00
```

**Explanation 0**

Marks for Malika are `{52,56,60}` whose average is (52+56+60)/3 = 56

<br>


**Sample Input 1**

```
2
Harsh 25 26.5 28
Anurag 26 28 30
Harsh
```

**Sample Output 1**

```
26.50
```

<br>


#### Given Code

```python
if __name__ == '__main__':
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
```

## Solution 1

```python
if __name__ == '__main__':
    from statistics import mean 
    import math
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    
    #print(student_marks[name])
    avg_score = (sum(student_marks[query_name])/len(student_marks[query_name]))
    print('%.2f'%avg_score)
```
Explanation:
1) We need to find the average score scored by the student whose query will be raised by the query_name.
2) So for this purpose we just use sum() and len() in built functions of python and then round it off to correct decimal places.



## Solution 2

```python
if __name__ == '__main__':
    from statistics import mean 
    import math
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    
    #print(student_marks[query_name])
    
    
    sum_of = 0
    for i in student_marks[query_name]:
         sum_of += i
         #print(sum_of)
         
    avg_score = sum_of/len(student_marks[query_name]) 
    print('%.2f'%avg_score)


```
Explanation:
1) Only difference is finding average using += shorthand operator and using for loop for iterating from list student_marks[query_name].