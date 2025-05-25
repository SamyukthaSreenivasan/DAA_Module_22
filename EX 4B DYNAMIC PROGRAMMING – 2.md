# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:25.5.2025
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings.

## Algorithm
1.Create a table lookup to store lengths of matching characters.
2.Compare each character of X with each character of Y.
3.If characters match, update the lookup value and track the maximum length and ending position.
4.After filling the table, the longest common substring is found at the tracked position.
5.Extract and print the substring from X using the recorded indices.

## Program:
```
/*
Program to implement the longest common substring problem
Developed by: Samyuktha S
Register Number: 212222240089
*/
```
```
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```
## Output:
![image](https://github.com/user-attachments/assets/a381f711-2909-4868-81c7-b53ca9436d76)

## Result:
Thus the program was executed successfully for finding the longest common substring .
