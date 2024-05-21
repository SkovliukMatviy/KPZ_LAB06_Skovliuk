# Bankomat
<b>Design Patterns Bankomat Project by Skovliuk Matviy IPZ-22-4</b> <br/>
I have implemented <i>Command</i>, <i>State</i> and <i>Memento</i> design patterns.

<hr />

The app supports the following commands:
<ul>
    <li>
        Account:
        <ul>
            <li><b>AddAccount <i>first_name</i> <i>last_name</i> <i>balance</i></b></li>
            <li><b>RemoveAccount <i>first_name</i> <i>last_name</i></b></li>
        </ul>
    </li>
    <li>
        Check:
        <ul>
            <li><b>CheckAccount <i>first_name</i> <i>last_name</i></b></li>
            <li><b>CheckAccountType <i>first_name</i> <i>last_name</i></b></li>
            <li><b>CheckBalance <i>first_name</i> <i>last_name</i></b></li>
        </ul>
    </li>
    <li>
        Funds:
        <ul>
            <li><b>DrawFunds <i>first_name</i> <i>last_name</i> <i>amount</i></b></li>
            <li><b>RechargeFunds <i>first_name</i> <i>last_name</i> <i>amount</i></b></li>
        </ul>
    </li>
    <li>
        Loan:
        <ul>
            <li><b>DrawLoan <i>first_name</i> <i>last_name</i> <i>amount</i> <i>years_to_return</i></b></li>
            <li><b>ReturnLoan <i>first_name</i> <i>last_name</i> <i>amount</i></b></li>
        </ul>
    </li>
    <li>
        System:
        <ul>
            <li><b>Shutdown</b></li>
            <li><b>Undo</b></li>
        </ul>
    </li>
</ul>
## Programming Principles

### KISS 
The KISS principle states that most systems work best if they are kept simple rather than made complicated. The codebase adheres to this principle by using clear and concise methods and classes.

### DRY 
The DRY principle aims to reduce repetition of information. The code avoids duplication by encapsulating common functionality within methods and classes.
Example: [code](https://github.com/SkovliukMatviy/KPZ_LAB06_Skovliuk/blob/main/BankProject/Mementos/Memento.cs)

### Program to Interfaces, Not Implementations
The application uses interfaces (`IAccount`, `IBank`, `IIdentity`) to define contracts for classes, promoting loose coupling and high cohesion.

### YAGNI
The YAGNI principle suggests not to add functionality until deemed necessary. The code focuses on core functionality without including unnecessary features.

### DYC 
The code follows this principle by implementing the simplest solution that solves the problem at hand, ensuring that the application is built with minimal complexity.

### Open/Closed Principle
The code is open for extension but closed for modification. New functionality can be added without changing existing code.

## Design Patterns
### Command Pattern
Each command (e.g., AddAccountCommand, RemoveAccountCommand, CheckBalanceCommand, etc.) implements a common interface ICommand that defines the Execute and Unexecute methods.
public interface ICommand
{
    void Execute();
    void Unexecute();
}
### Memento Pattern
The Account class uses the Memento pattern to capture its state. The Memento class stores the state of the account, allowing the state to be restored.
### Prototype Pattern
Enables the creation of new objects by copying existing ones, promoting efficient object creation and ensuring that new instances are created with the same properties.
public interface IPrototype<T>
{
    T Clone();
}

## Refactoring Techniques

### Rename Method
The code uses clear and descriptive method names to improve readability.

### Extract Method
Large methods are broken down into smaller, more manageable methods.

### Inline Method
Unnecessary methods are inlined to simplify the code. During the development stage, it was utilized to simplify code comprehension.

### Inline Temp
Temporary variables are inlined to reduce complexity.Helped a lot to simplify and reduce the code

### Replace Temp with Query
Temporary variables are replaced with methods that return the value, improving readability and maintainability.

### Remove Assignments to Parameters
Assignments to method parameters are removed to adhere to the principle of immutability.

### Substitute Algorithm
More efficient algorithms are used where possible to improve performance.

### Move Field
During the development phase, it was used to simplify code, enhance logic, and ensure field-to-class conformity.
