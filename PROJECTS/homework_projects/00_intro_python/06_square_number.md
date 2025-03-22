## Problem Statement

Ask the user for a number and print its square (the product of the number times itself).

Here's a sample run of the program (user input is in bold italics):

Type a number to see its square: 4

4.0 squared is 16.0

## Starter Code

```bash
def main():
    print("Delete this line and write your code here! :)")


# There is no need to edit code beyond this point

if __name__ == '__main__':
    main()
```

## Solution

```bash
def main():
    num: float = float(input("Type a number to see its square: ")) # Make sure to cast the input to a float so we can do math with it!
    print(str(num) + " squared is " + str(num ** 2)) # num * num is equivalent to num ** 2. The ** operator raises something to a power!


# There is no need to edit code beyond this point

if __name__ == '__main__':
    main()
```
