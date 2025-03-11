## Problem Description
Complete the classes **Smaller** and **Larger**.

- **Smaller** class gets instantiated when the argument of the function (a:string) has a length smaller than 6 otherwise **Larger** is instantiated.
Both the classes have the same two methods, **display()** printing the type of a (**class**), and
evaluate() printing the number of **vowels** if the Name is Smaller otherwise it prints the number of consonants.


## Input Format

'For each testcase there will be a single line of input which will be a string (it can contain both uppercase and lowercase alphabets).' 


## Output Format

For each testcase there will be two lines of outputs. First line will write the type of object and second line will print the output of evaluate() according to the object type.
The type of Name is Smaller or Larger # Line 1
Number vowels or consonants # Line 2


**Example Input 1**
```sh
aman
```


**Example Output 1**
```sh
The type of Name is Smaller
2
```


**Example Explanation 1**

Since the length of "aman" is 4 which is smaller than 6, therefore, it will be called with Smaller class and in the second line evaluate() will print the frequency of vowels in the Name.



**Example Input 2**
```sh
rajnandini
```


**Example Output**

```sh
The type of Name is Larger
6
```


**Example Explanation**

Since the length of "rajnandini" is 10 which is larger than 6, therefore, it will be called with Larger class and in the second line evaluate() will print the frequency of consonants in the Name.


## Solution


```sh

    
class Smaller:
    def __init__(self, a):
        self.string = a
    
    def display(self):
        print("The type of Name is Smaller")
    
    def evaluate(self):
        vowels = "aeiouAEIOU"
        ans = sum(1 for char in self.string if char in vowels)  # Counting vowels
        print(ans)
        
class Larger:
    def __init__(self, a):
        self.string = a
    
    def display(self):
        print("The type of Name is Larger")
    
    def evaluate(self):
        vowels = "aeiouAEIOU"
        ans = sum(1 for char in self.string if char.isalpha() and char not in vowels)  # Counting consonants
        print(ans)

def main(a):
    '''
    input a is string
    '''
    if len(a)<6:
        obj=Smaller(a)
        obj.display()
        obj.evaluate()
    else:
        obj=Larger(a)
        obj.display()
        obj.evaluate()
    ```
