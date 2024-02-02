
# #9 Find the Runner-Up Score!




# 09 - Find the Runner-Up Score
## Problem

Given the participants' score sheet for your University Sports Day, you are required to find the runner-up `n` score. You are given  scores. Store them in a list and find the score of the runner-up.


#### Input Format

The first line contains `n`. The second line contains an array `A[]`  of `n` integers each separated by a space.


#### Constraints
2 <= n <= 10
-100 <= A[i] <= 100

#### Output Format

Print the runner-up score.

```
Sample Input :
5
2 3 6 6 5
```

```
Sample Output :
5
```

#### Explanation
Given list is `[2,3,6,6,5]`. The maximum score is 6, second maximum is 5. Hence, we print 5 as the runner-up score.


#### Given Code

```python
if __name__ == '__main__':
    n = int(input())
    arr = map(int, input().split())
```


## Solution 1

```python
if __name__ == '__main__':
    n = int(input())
    arr = list(set(map(int, input().split())))
    
    arr.sort()
    print(arr[-2])
```
Explanation: We convert array into set so that we can get distinct values and then conver it to the list so that we do sort function
since sort can't be directly used on set.
After sorting we use slicing to get second last element that is Second Largest element in list.



     



## Solution 4

```
if __name__ == '__main__':
    n = int(input())
    arr = list(set(map(int, input().split())))
    
    arr.sort(reverse=True) 
    #arr = [9,8,7,4,3,1]
    count = 1
    maxi = arr[0] 
    
    for i in range(len(arr)):
        if (arr[i] != maxi):
            count = count + 1
            maxi = arr[i]
        if count == 2:
            print(arr[i])
```
Explanation :1) Converting it to list so that sort can be applied.

2)Reverse true so that we can get descending order arr = [9,8,7,4,3,1]

3)defining variable count

4)iterating through the list

5)Checking in first iteration where A[0] which is 9 is not equal to 9 condition is false so we go to next if condition even count is 1 so not equal to 3 so again loop starts.

6)Checking A[1] is not equal to 9 so condition is true so now count increases by 1 and then count = 2 and secondif condition is also True sinec 2 == 2. 


7) So we got second highest element in list.

Note : for finding second, third, fourth we only need to change count vlaue in second if loop.


