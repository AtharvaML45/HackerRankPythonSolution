# 012 - Lists
## Problem

Consider a list (`list = []`). You can perform the following commands:

1. `insert i e` : Insert integer `e` at position `i`
2. `print` : Print the list
3. `remove e` : Delete the first occurrence of integer `e`
4. `append e` : Insert integer `e` at the end of the list
5. `sort` : Sort the list
6. `pop` : Pop the last element from the list
7. `reverse` : Reverse the list

Initialize your list and read in the value of `n` followed by `n` lines of commands where each command will be of the `7` types listed above. Iterate through each command in order and perform the corresponding operation on your list.


#### Input Format

The first line contains an integer, `n`, denoting the number of commands.

Each line `i` of the `n` subsequent lines contains one of the commands described above.


#### Constraints

The elements added to the list must be integers


#### Output Format

For each command of type `print`, print the list on a new line.


**Sample Input 0**

```
12
insert 0 5
insert 1 10
insert 0 6
print
remove 6
append 9
append 1
sort
print
pop
reverse
print
```

**Sample Output 0**

```
[6, 5, 10]
[1, 5, 9, 10]
[9, 5, 1]
```


<br>


#### Given Code

```python
if __name__ == '__main__':
    N = int(input())
```

## Solution

```python
if __name__ == '__main__':
    N = int(input())
    lst = []
    for i in range(N):
        cm = input().split()
        if cm[0] == 'insert':
            lst.insert(int(cm[1]),int(cm[2]))
        if cm[0]=='print':
            print(lst)
        if cm[0] == 'remove':
            lst.remove(int(cm[1]))
        if cm[0] == 'append':
            lst.append(int(cm[1]))
        if cm[0] == 'sort':
            lst.sort()
        if cm[0] == 'pop':
            lst.pop() 
        if cm[0] == 'reverse':
            lst.reverse()   
        
        
```
Explanation:
1) Fisrt Of all what we need to do is we wil be given N number of commands and we have to perform list operation which will be given in string Format For Eg: append 1 means we need to apppend 1 to the list.
2) first we are inititalitzing list then we are looping through the list
3) We will take input from user we get input in string format and so we will split it and store it in the list.
4) Once we store in list we only need to check cm[0] that is input from user and commands such as insert append are they matching or not.
5) We need to adjust parameters depending upon commands such as remove takes only one argument while insert takes two arguments.


