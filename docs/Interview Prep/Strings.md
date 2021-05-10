# Interview Prep!

!!! Warning "Note"
    Site Under construction



## 1. Make Permuatations

Given a string make all possible permutatations.
example
```
input -> 'ABC'
```

```
output -> ['ABC', 'ACB', 'BAC', 'BCA', 'CAB', 'CBA']
```


```py
def anagram(string,rtn=None):
    if rtn is None:
        rtn = []
    
    if(len(string) == 2):
        x = string[0] + string[1]
        y = string[1] + string[0]
        return [x,y]
    else:
        for x in string:
            data = anagram(string.replace(x,""))
            for y in data:
                rtn.append(x+y)
    return rtn
```