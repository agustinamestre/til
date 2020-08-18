## Variable conversion

If we want to ask the user to enter data, C# provides us with a method that belongs to the *Console* class and is called **ReadLine()**. **This method only returns the value as a string**. Which is a limitation since we cannot use a string in arithmetic operations or assign it directly to a variable.

What we must do is **convert that numeric data saved as a string to a useful numeric value for our purposes**. How do we do that? Well, C # has a method called **Int32.Parse()** that converts the string representation of a number to the equivalent 32-bit signed integer.

An example of this is:

``` csharp
number1 = Int32.Parse(Console.ReadLine());
```

Similarly we can convert the string to a variable of type double:

``` csharp
number2 = double.Parse(Console.ReadLine());
```

Since we have the values converted to numbers, then we can make use of them. Let's see an example:

``` csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            double number2, sum;
            int number1;
            Console.WriteLine("Please, enter the first number: ");
            number1 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Please, enter the second number: ");
            number2 = double.Parse(Console.ReadLine());
            Console.WriteLine();

            sum = number1 + number2;

            Console.WriteLine("The sum of {0} and {1} is {2}", number1, number2, sum);
            Console.ReadKey();

        }
    }
}
```

Once compiled:

![conversion](https://user-images.githubusercontent.com/59721315/90516816-ed12b380-e13a-11ea-8b12-d0973ebb3bdb.png)


