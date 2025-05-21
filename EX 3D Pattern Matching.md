# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. A text string T of length n

2. A pattern string P of length m

3. Loop through the text:

4. For each index i from 0 to n - m, do:

5. The index i where match is found.

6. If no match found, return -1 or appropriate message
## Program:
Developed by:  GANESH R

Register Number:  212222240029

```python
def BF(s1,s2):
##############  Add your code here #############
    #Start here
    i = 0
    j = 0
    while(i < len(s1) and j < len(s2)):
        if(s1[i] ==  s2[j]):
            i += 1
            j += 1
        else:
            i = i - j + 1
            j = 0
    if(j >= len(s2)):
        return i - len(s2)
    else:
        return 0
    #End here
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)



```

## Output:
![image](https://github.com/user-attachments/assets/63aff919-8b57-440a-ab4b-8dc31892158c)



## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
