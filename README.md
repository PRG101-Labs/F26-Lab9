# PRG101-Lab9
### Submission Details

In this lab, you will work on two examples to overload math operators and use "Python’s special functions".
Write the scripts in "GitHub Codespaces". 
For this lab, consider taking screenshots and creating a pdf. For some of the tasks, you will need to capture more than one screenshots to show all the code.

### Lab Objectives

- To be able to implement operator overloading in python.
- To be able to use special methods in python.
- Reflect on your learning of object oriented programming

## INVESTIGATION 1: PYTHON OPERATOR OVERLOADING
Operator overloading allows you to define how operators behave with objects of your custom classes. This is done by defining special methods in your class. Let’s explore some of these methods in detail.
Let's create a class that represents ComplexNumbers in maths, we will overload the +, -, __str__, and __repr__ methods.
Complex numbers are numbers that have both a real part and an imaginary part. They are usually written in the form ( a + bi ), where ( a ) is the real part and ( b ) is the imaginary part, and ( i ) is the imaginary unit with the property that ( i^2 = -1 ).

**Example of a Complex Number**

Let’s take the complex number ( 3 + 4i ):

    The real part is ( 3 ).
    The imaginary part is ( 4i ).

**Addition of Complex Numbers**

To add two complex numbers, you add their real parts and their imaginary parts separately.

Example: (3 + 4i) + (1 + 2i) = (3 + 1) + (4i + 2i) = 4 + 6i 
Let's see how can we implement this functionality in Python. We will use the special method `__add__()` which is called when the + operation is performed on two class objects.
```Python
class ComplexNumber:
    def __init__(self, real, imag):
        self._real = real
        self._imag = imag

    def __add__(self, other):
        new_real = self._real + other._real
        new_imag = self._imag + other._imag
        return ComplexNumber(new_real, new_imag)

# Example usage
c1 = ComplexNumber(1, 2)
c2 = ComplexNumber(3, 4)
c3 = c1 + c2 # __add__() method is called when this statement executes. c1 is passed to `self` reference and c2 is passed to `other` reference
```

**Printing our class objects**

Let's add a new method to print the objects, so that we can print the complex number objects  in the correct format. Python allows us to use a special `__str__()` Method.
The` __str__()` method defines the behavior of the str() function and the print statement for class objects. But first lets add a simple method called `display()` to print our objects.


```Python
class ComplexNumber:
    def __init__(self, real, imag):
        self._real = real
        self._imag = imag

    def __add__(self, other):
        new_real = self._real + other._real
        new_imag = self._imag + other._imag
        return ComplexNumber(new_real, new_imag)

    def display(self):
        print(f"{self._real} + {self._imag}i")


# Example usage
c1 = ComplexNumber(1, 2)
c1.display() # output: 1 + 2i
  
c2 = ComplexNumber(3, 4)
c2.display() # output: 3 + 4i

c3 = c1 + c2
c3.display() #4 + 6i

```
Wouldn't it be interesting if we could simply pass our object to print() function and expect the same output as above? We can do this by using the special method `__str__()`.
Lets replace our display method with `__str__()` and then use it.

```Python
class ComplexNumber:
    def __init__(self, real, imag):
        self._real = real
        self._imag = imag

    def __add__(self, other):
        new_real = self._real + other._real
        new_imag = self._imag + other._imag
        return ComplexNumber(new_real, new_imag)

    def __str__(self):
        return(f"{self._real} + {self._imag}i")


# Example usage
c1 = ComplexNumber(1, 2)
print(c1) # output: 1 + 2i
  
c2 = ComplexNumber(3, 4)
print(c2) # output: 3 + 4i

c3 = c1 + c2
print(c3) #4 + 6i

```
This is phenomenal. We are no more calling the boring `display` method. We can simply call the `print` function. When Python sees that there is a call to`print` function with an argument as class objects, it checks for the implementation of `__str__` method and will execute the `__str__` method instead. This is cool!.

We have used two special methods so far: `__add__()` and  `__str__()`.
Now it is your turn.

### lab9a - Overload the subtraction operator `-` [2.0 points]

- Create a new Python file called `complexnumber.py`.
- Copy the above class code in the file.
- Create a new method called `__sub__()`. This method should take two objects of the class and subtract them. This is the same as the implementation of `__add__()`. Just subtract instead of addition.
- Create a new file called `complexnumber_tester.py`.
- Import your class, write the main function and write code to test the functionality of `__sub__()`.
- Run the script from command line using the command: Python ./complexnumbers_tester.py.
- Take a clear screenshot of `__sub__`() method, `main()` from `complexnumbers_tester.py` and, the output. Add this screenshot in the pdf.


## INVESTIGATION 2: UNDERSTANDING AND USING THE GIVEN FRACTION CLASS.
You are given a fraction class that uses many special methods of Python to overload the basic maths operations on fractions. Some of the methods have been completed for you. Go through the methods which have been completed and understand them.
Some of the methods have been left for you to complete.

### lab9b - Complete the methods in fraction class [3.0 points]
- Complete the rest of the methods by following the comments in the given fraction class.
- Create a new file called fraction_tester.py.
- Import fraction class in the fraction_tester.py.
- Create main() in fraction_tester.py.
- Create two objects of `Fraction` class.
- Demonstrate the use of all methods from Fraction class for the two Fraction objects/
- Take clear screenshots of the methods that you have been assigned to complete and the test code and the output.
- Make sure to organise and name the screenshots correctly.
- Add the screenshots in the pdf.

## INVESTIGATION 3: REFLECTION
Over the past three weeks, we have covered several key concepts in Python, including classes, objects, encapsulation, instance variables, calling methods, and operator overloading. Reflect on what you have learned so far and explain your understanding of each of these concepts. Additionally, share your thoughts on how you feel about these topics and how they have impacted your interest in Python programming. This part need not to be submitted but I strongly recommend that you write your understanding of these concepts.
  
## Lab 9 Sign-Off
- Submit the pdf including the above mentioned screenshots.
- The screenshot must show your username on github codespaces.
- Make sure screenshots are readable.
- Name your file as: StudentFullName_PRG101_Lab9.pdf



