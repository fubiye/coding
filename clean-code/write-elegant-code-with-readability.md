# Write elegant code with readability

## Meaningful Name

### Use Intention-Revealing Names

```java
public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList)
        if (x[0] == 4)
            list1.add(x);
    return list1;
}
```

Questions:
1. What kinds of things are in theList?
2. What is the significance of the zeroth subscript of an item in theList?
3. What is the significance of the value 4?
4. How would I use the list being returned?

First version:
```java
public List<int[]> getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard)
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
    return flaggedCells;
}
```

Second version (Object-Oriented Design):

```java
public List<Cell> getFlaggedCells() {
    List<Cell> flaggedCells = new ArrayList<Cell>();
    for (Cell cell : gameBoard)
        if (cell.isFlagged())
            flaggedCells.add(cell);
    return flaggedCells;
}
```

### Use Searchable names

Single-letter names and numeric constants have a particular problem in that they are not easy to locate across a body of text.

* MAX_CLASSES_PER_STUDENT
* 7

*variable, method, log etc.*

## Too long, not read - make it small

### The Single Responsibility Principle(SRP)

***SRP: Each software module should have one and only one reason to change***

***FUNCTIONS SHOULD DO ONE THING. THEY SHOULD DO IT WELL. THEY SHOULD DO IT ONLY.***

Shape of funciton:
+ Lines should not be 150 characters long. 
+ Functions should not be 100 lines long.
+ Functions should hardly ever be 20 lines long.

Abstraction: ***One Level of Abstraction per Function***

Case Study: Switch Statements

**Payroll.java**
```java 
public Money calculatePay(Employee e) throws InvalidEmployeeType {
    switch (e.type) {
        case COMMISSIONED:
            return calculateCommissionedPay(e);
        case HOURLY:
            return calculateHourlyPay(e);
        case SALARIED:
            return calculateSalariedPay(e);
        default:
            throw new InvalidEmployeeType(e.type);
    }
}
```
Problems:
 + it’s large, and when new employee types are added, it will grow. 
 + it very clearly does more than one thing.
 + it violates the Single Responsibility Principle (SRP) because there is more than one reason for it to change. 
 + it violates the Open Closed Principle (OCP) because it
must change whenever new types are added.

*OCP: software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification*

Solution: ABSTRACT FACTORY

Employee and Factory
```java
public abstract class Employee {
    public abstract boolean isPayday();
    public abstract Money calculatePay();
    public abstract void deliverPay(Money pay);
}

public interface EmployeeFactory {
    public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
}

public class EmployeeFactoryImpl implements EmployeeFactory {
    public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType {
        switch (r.type) {
            case COMMISSIONED:
                return new CommissionedEmployee(r) ;
            case HOURLY:
                return new HourlyEmployee(r);
            case SALARIED:
                return new SalariedEmploye(r);
            default:
                throw new InvalidEmployeeType(r.type);
        }
    }
}
```
### Duplication - Don’t Repeat Yourself