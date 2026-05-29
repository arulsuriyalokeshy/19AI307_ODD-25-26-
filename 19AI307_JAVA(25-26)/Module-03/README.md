# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
Create a Super class Person with fields name and age. Create a subclass Student that inherits from Person and adds a field marks (integer). Implement a method in Student called calculateGrade() which returns the grade based on the marks:

Marks ≥ 90: Grade A

Marks ≥ 75 and < 90: Grade B

Marks ≥ 50 and < 75: Grade C

Marks < 50: Grade F


## AIM:
Create a Person superclass and a Student subclass with a marks field, and calculate the grade based on marks.


## ALGORITHM :
1. Start and import Scanner to read user input.

2. Create a superclass Person with fields name and age, and a subclass Student that    adds a marks field.

3. Read the student’s name, age, and marks from the user.

4. Create a Student object and call the calculateGrade() method to determine the       grade based on marks.

5. Display the student’s name, age, marks, and grade, then end the program.





## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:

```
import java.util.Scanner;


class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}


class Student extends Person {
    int marks;

    Student(String name, int age, int marks) {
        super(name, age); 
        this.marks = marks;
    }

    String calculateGrade() {
        if (marks >= 90)
            return "A";
        else if (marks >= 75)
            return "B";
        else if (marks >= 50)
            return "C";
        else
            return "F";
    }
}


public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

       
        String name = sc.nextLine();

        
        int age = sc.nextInt();

       
        int marks = sc.nextInt();

        Student s = new Student(name, age, marks);

       
        System.out.println("Name: " + s.name);
        System.out.println("Age: " + s.age);
        System.out.println("Marks: " + s.marks);
        System.out.println("Grade: " + s.calculateGrade());

        sc.close();
    }
}
```





## OUTPUT:

<img width="499" height="558" alt="image" src="https://github.com/user-attachments/assets/c2496d4c-ee9d-4acd-8869-4320d63a64cb" />



## RESULT:
The program displays the student’s name, age, marks, and corresponding grade.



# Ex.No:3(b) POLYMORPHISM

## QUESTION:
Write a Java program that calculates the area of different shapes using method overloading. Create a class AreaCalculator with:

area(int side) for square

area(int length, int breadth) for rectangle

area(double radius) for circle

<img width="447" height="180" alt="image" src="https://github.com/user-attachments/assets/28afedde-02fe-4562-8c03-3310286a0ab0" />



## AIM:
Create an AreaCalculator class using method overloading to calculate areas of a square, rectangle, and circle.


## ALGORITHM :
1. Start and import Scanner.


2. Create prog class with overloaded area() methods for square, rectangle, and         circle.


3. Read side, length & breadth, and radius from the user.


4. Call the appropriate area() method for each shape.


5. Display the areas and end the program.







## PROGRAM:
 ```
/*
Program to implement a Polymorphism using Java
Developed by:SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

class prog {

    void area(int side) {
        System.out.println("Area of square: " + (side * side));
    }

    void area(int length, int breadth) {
        System.out.println("Area of rectangle: " + (length * breadth));
    }

    void area(double radius) {
        double result = Math.PI * radius * radius;
        System.out.println("Area of circle: " + result);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        prog obj = new prog();

        int side = sc.nextInt();
        obj.area(side);

        int length = sc.nextInt();
        int breadth = sc.nextInt();
        obj.area(length, breadth);

        double radius = sc.nextDouble();
        obj.area(radius);

        sc.close();
    }
}
```





## OUTPUT:

<img width="825" height="372" alt="image" src="https://github.com/user-attachments/assets/c42bf11f-b5fd-4d8a-83ed-5fa4850d2192" />


## RESULT:
The program displays the area of the chosen shape based on the input values.



# Ex.No:3(C) ABSTRACTION

## QUESTION:
Description:
Create abstract class GameScore with method finalScore().
Subclasses:

ArcadeGame: score = baseScore + (level × 100)

PuzzleGame: score = (attempts ≤ 3) ? 1000 - (attempts × 100) : 500

Input Format:

First line: 1 or 2
Second line: base, level (or attempts)

Output Format:

Final score (int)



## AIM:
To write a Java program using an abstract class GameScore with subclasses ArcadeGame and PuzzleGame, each implementing its own finalScore() method.

## ALGORITHM :
1.	Create an abstract class GameScore with an abstract method finalScore().
2.	Define subclass ArcadeGame where finalScore = baseScore + (level × 100).
3.	Define subclass PuzzleGame where
4.	If attempts ≤ 3, score = 1000 - (attempts × 100)
5.	Else score = 500.
6.	Take user input for game type and relevant values.
7.	Display the final score based on game type.



## PROGRAM:
 ```
/*
Program to implement a Abstraction using Java
Developed by: SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:
```JAVA
import java.util.*;

abstract class GameScore {
    abstract int finalScore();
}

class ArcadeGame extends GameScore {
    int base, level;
    ArcadeGame(int base, int level) {
        this.base = base;
        this.level = level;
    }
    int finalScore() {
        return base + (level * 100);
    }
}

class PuzzleGame extends GameScore {
    int attempts;
    PuzzleGame(int attempts) {
        this.attempts = attempts;
    }
    int finalScore() {
        if (attempts <= 3)
            return 1000 - (attempts * 100);
        else
            return 500;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int type = sc.nextInt();
        if (type == 1) {
            int base = sc.nextInt();
            int level = sc.nextInt();
            ArcadeGame game = new ArcadeGame(base, level);
            System.out.println(game.finalScore());
        } else if (type == 2) {
            int attempts = sc.nextInt();
            PuzzleGame game = new PuzzleGame(attempts);
            System.out.println(game.finalScore());
        }
    }
}
```

## OUTPUT:
<img width="1147" height="386" alt="image" src="https://github.com/user-attachments/assets/4447ae81-3e1b-46a2-91a4-e2ad7316e6a6" />

## RESULT:
The program successfully demonstrates abstraction and inheritance by computing the final score for different game types using subclass-specific logic.





# Ex.No:3(D)    INTERFACE 

## QUESTION:
You are programming bots that analyze weather data. Each bot must implement a common interface and give a prediction.


 Bot Types:

SunBot: Predicts "HOT" if temperature > 30, else "MODERATE".

RainBot: Predicts "COLD" if temperature < 20, else "WARM".

Input:

temperature
botType (1 for SunBot, 2 for RainBot)Output:
Prediction as a string.

## AIM:
To implement weather prediction using interfaces with two bots — SunBot and RainBot.

## ALGORITHM :
1.	Create WeatherBot interface with predict() method.
2.	Implement SunBot and RainBot classes with different prediction logic.
3.	Take temperature and botType as input.
4.	Use the chosen bot to call predict().
5.	Display the prediction.

## PROGRAM:
 ```
/*
Program to implement a Interface using Java
Developed by: SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

interface WeatherBot {
    String predict(int temperature);
}

class SunBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature > 30) {
            return "HOT";
        } else {
            return "MODERATE";
        }
    }
}

class RainBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature < 20) {
            return "COLD";
        } else {
            return "WARM";
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int temperature = sc.nextInt();
        int botType = sc.nextInt();
        WeatherBot bot;

        if (botType == 1) {
            bot = new SunBot();
        } else {
            bot = new RainBot();
        }

        System.out.println(bot.predict(temperature));
        sc.close();
    }
}
```

## OUTPUT:
<img width="1148" height="334" alt="image" src="https://github.com/user-attachments/assets/b635390f-88b0-47d2-893e-ab671a5dac52" />


## RESULT:
The program predicts weather conditions using interface implementation and method overriding.





# Ex.No:3(E) INNER CLASS

## QUESTION:
Write a Java program to create an inner class and access it from the outer class.

## AIM:
To demonstrate accessing an inner class from an outer class in Java.

## ALGORITHM :
1.	Create an outer class with a private variable.
2.	Define an inner class inside it with a method to access the outer variable.
3.	In main(), create an object of the outer class.
4.	Use it to create an object of the inner class.
5.	Call the inner class method.

## PROGRAM:
 ```
/*
Program to implement a InnerClass using Java
Developed by:SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

class OuterClass {
    String name;

    OuterClass(String name) {
        this.name = name;
    }

    void display() {
        InnerClass inner = new InnerClass();
        inner.showMessage();
    }

    class InnerClass {
        void showMessage() {
            System.out.println("Hello, " + name + "! This message is from the Inner Class.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("");
        String input = scanner.next();
        scanner.close();

        OuterClass outer = new OuterClass(input);
        outer.display();
    }
}
```

## OUTPUT:
<img width="1223" height="347" alt="image" src="https://github.com/user-attachments/assets/3a4a3b07-7cc7-4e68-877e-4bb04d3aab6d" />

## RESULT:
The program successfully accesses and prints data from the inner class using the outer class.





# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Write a Java program to convert a string to an integer using a wrapper class and perform addition.

## AIM:
To convert string inputs into integers using the wrapper class and perform addition.

## ALGORITHM :
1.	Read two numbers as strings.
2.	Convert them to integers using Integer.parseInt().
3.	Add the two integers.
4.	Display the sum.

## PROGRAM:
 ```
/*
Program to implement a Wrapper Class using Java
Developed by: SURIYA PRAKASH S
RegisterNumber: 212223100055
*/
```

## SOURCE CODE:
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String str1 = scanner.next();

        String str2 = scanner.next();

        scanner.close();

        try {
            int num1 = Integer.parseInt(str1);
            int num2 = Integer.parseInt(str2);


            int sum = num1 + num2;
            System.out.println("Sum = " + sum);
        } catch (NumberFormatException e) {
            System.out.println("Invalid input. Please enter a valid number.");
        }
    }
}
```
## OUTPUT:
<img width="1223" height="414" alt="image" src="https://github.com/user-attachments/assets/899591cc-4837-4c4d-9693-94fdcade6361" />

## RESULT:
The program successfully converts strings to integers and displays their sum.





