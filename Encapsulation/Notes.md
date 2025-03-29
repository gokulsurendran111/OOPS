## Encapsulation
It refers to the bundling of data (variables) and methods (functions) 
that operate on the data into a single unit, typically a class. Encapsulation is
achieved by restricting direct access to some components of an object and only exposing 
a controlled interface.

### Advantages
#### 1. Data Hiding (Security)
Encapsulation hides sensitive data from direct access by marking 
variables as private. Only controlled access is provided via public 
methods.
Eg) Absolute Pressure can't be less than zero. We can restrict the _pressure_ to be 
_less than zero_ through a **setter** method.
Similarly *getter* method can hide sensitive data

#### 2. Improved Maintainability & Modularity
Since internal implementation is hidden, changes to internal logic won’t affect other parts of the program.
Eg) Let's have a tax calculator and tax rate changed from 0.2 to 0.3. `tax = salary * 0.2;`
Every part of the code where tax is calculated has to be changed. But if we modularize it like
`

    class Employee {
        private double salary;
        public Employee(double salary) {
            this.salary = salary;
        }
        public double calculateTax() { 
            return salary * 0.15; // Tax rate logic
        }
    }
`

#### 3. Code reusability
Encapsulated code can be reused multiple times by creating objects.

#### 4. Control over variable modification
Similar to 1st advantage above

#### 5. Enhances loose coupling
Loose coupling means reducing dependencies between different parts of the program.

Eg) In the code below, External classes don't need to know the database details, making changes easier.
`

    class Database {
        private String connectionString = "jdbc:mysql://localhost:3306/db";
    
        public void connect() {
            System.out.println("Connecting to " + connectionString);
        }
    }
    
    public class Main {
        public static void main(String[] args) {
            Database db = new Database();
            db.connect();
        }
    }

`

#### 6. Improved readability and debugging