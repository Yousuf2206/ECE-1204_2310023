## **Lab: 09**

## **Experiment No: 01**
## **Experiment Name : Create a simple calculator that performs binary (addition, subtraction, multiplication, division) and unary operations (prefix and postfix) using a class with three variables.**
## **Submission Date: August 11, 2025**

## **Code 01:**
```C++

#include <bits/stdc++.h>
using namespace std;

class calculator
{
    int a, b, c;

public:
    calculator(int p = 0, int q = 0, int r = 0)
    {
        a = p;
        b = q;
        c = r;
    }

    // addition
    calculator operator+(calculator &ob1)
    {
        calculator temp1;
        temp1.a = a + ob1.a;
        return temp1;
    }

    // subtraction
    calculator operator-(calculator &ob2)
    {
        calculator temp2;
        temp2.a = a - ob2.a;
        return temp2;
    }

    // multiplication
    calculator operator*(calculator &ob2)
    {
        calculator temp3;
        temp3.a = a * ob2.a;
        return temp3;
    }

    // division
    calculator operator/(calculator &ob2)
    {
        calculator temp3;
        if (ob2.a == 0)
        {
            cout << "Error: Division by zero!\n";
            temp3.a = 0;
        }
        else
            temp3.a = a / ob2.a;
        return temp3;
    }

    // prefix increment
    void operator++()
    {
        a = a + 1;
    }

    // postfix increment
    void operator++(int)
    {
        a = a + 1;
    }

    // prefix decrement
    void operator--()
    {
        a = a - 1;
    }

    // postfix decrement
    void operator--(int)
    {
        a = a - 1;
    }

    // += operator overloading
    void operator+=(calculator c)
    {
        a = a + c.a;
    }

    // comparison
    bool operator==(calculator bb)
    {
        return a == bb.a;
    }

    // display
    void display()
    {
        cout << a << endl;
    }

    // set value
    void setValue(int x)
    {
        a = x;
    }
};

int main()
{
    int choice, x, y;
    cout << "Enter two numbers: ";
    cin >> x >> y;

    calculator ob1(x), ob2(y), result;

    cout << "\nChoose an operation:\n";
    cout << "1. Addition\n";
    cout << "2. Subtraction\n";
    cout << "3. Multiplication\n";
    cout << "4. Division\n";
    cout << "Enter your choice: ";
    cin >> choice;

    switch (choice)
    {
    case 1:
        result = ob1 + ob2;
        cout << "Initial Addition Result: ";
        result.display();
        break;

    case 2:
        result = ob1 - ob2;
        cout << "Initial Subtraction Result: ";
        result.display();
        break;

    case 3:
        result = ob1 * ob2;
        cout << "Initial Multiplication Result: ";
        result.display();
        break;

    case 4:
        result = ob1 / ob2;
        cout << "Initial Division Result: ";
        result.display();
        break;

    default:
        cout << "Invalid choice!\n";
        return 0;
    }

    char inc_dec;
    cout << "\n(+ for increment, - for decrement, n for no): ";
    cin >> inc_dec;
    if (inc_dec == '+')
    {
        result++;
        cout << "After increment: ";
        result.display();
    }
    else if (inc_dec == '-')
    {
        result--;
        cout << "After decrement: ";
        result.display();
    }

    int extra;
    cout << "Enter the integer to add: ";
    cin >> extra;
    calculator temp(extra);
    result += temp;
    cout << "After adding " << extra << ": ";
    result.display();

    cout << "\nFinal Result: ";
    result.display();

    return 0;
}



```

## **Output 01:** 
<p align="center">
<img width="829" height="717" alt="Image" src="https://github.com/user-attachments/assets/6f6f0263-e48b-4243-81ff-e1d8868c1137" />
</p>

## **Experiment No: 02**
## **Experiment Name Use operator overloading for the same operations, but instead of implementing them as member functions, implement them as friend functions. This means the operator functions will be defined outside the class, but they will still have access to the class's private variables.: **
## **Submission Date: August 11, 2025**

## **Code 02:**
```C++

#include <bits/stdc++.h>
using namespace std;

class calculator
{
    int a, b, c;

public:
    calculator(int p = 0, int q = 0, int r = 0)
    {
        a = p;
        b = q;
        c = r;
    }

    // Friend function declarations
    friend calculator operator+(calculator &ob1, calculator &ob2);
    friend calculator operator-(calculator &ob1, calculator &ob2);
    friend calculator operator*(calculator &ob1, calculator &ob2);
    friend calculator operator/(calculator &ob1, calculator &ob2);
    friend void operator++(calculator &obj);      // prefix increment
    friend void operator++(calculator &obj, int); // postfix increment
    friend void operator--(calculator &obj);      // prefix decrement
    friend void operator--(calculator &obj, int); // postfix decrement
    friend void operator+=(calculator &obj, calculator c);
    friend bool operator==(calculator bb, calculator cc);

    // display
    void display()
    {
        cout << a << endl;
    }
};

// Addition
calculator operator+(calculator &ob1, calculator &ob2)
{
    calculator temp1;
    temp1.a = ob1.a + ob2.a;
    return temp1;
}

// Subtraction
calculator operator-(calculator &ob1, calculator &ob2)
{
    calculator temp2;
    temp2.a = ob1.a - ob2.a;
    return temp2;
}

// Multiplication
calculator operator*(calculator &ob1, calculator &ob2)
{
    calculator temp3;
    temp3.a = ob1.a * ob2.a;
    return temp3;
}

// Division
calculator operator/(calculator &ob1, calculator &ob2)
{
    calculator temp3;
    if (ob2.a == 0)
    {
        cout << "Error: Division by zero!\n";
        temp3.a = 0;
    }
    else
        temp3.a = ob1.a / ob2.a;
    return temp3;
}

// Prefix increment
void operator++(calculator &obj)
{
    obj.a = obj.a + 1;
}

// Postfix increment
void operator++(calculator &obj, int)
{
    obj.a = obj.a + 1;
}

// Prefix decrement
void operator--(calculator &obj)
{
    obj.a = obj.a - 1;
}

// Postfix decrement
void operator--(calculator &obj, int)
{
    obj.a = obj.a - 1;
}

// += operator
void operator+=(calculator &obj, calculator c)
{
    obj.a = obj.a + c.a;
}

// Comparison
bool operator==(calculator bb, calculator cc)
{
    return bb.a == cc.a;
}

int main()
{
    int choice, x, y;
    cout << "Enter two numbers: ";
    cin >> x >> y;

    calculator ob1(x), ob2(y), result;

    cout << "\nChoose an operation:\n";
    cout << "1. Addition\n";
    cout << "2. Subtraction\n";
    cout << "3. Multiplication\n";
    cout << "4. Division\n";
    cout << "Enter your choice: ";
    cin >> choice;

    switch (choice)
    {
    case 1:
        result = ob1 + ob2;
        cout << "Initial Addition Result: ";
        result.display();
        break;

    case 2:
        result = ob1 - ob2;
        cout << "Initial Subtraction Result: ";
        result.display();
        break;

    case 3:
        result = ob1 * ob2;
        cout << "Initial Multiplication Result: ";
        result.display();
        break;

    case 4:
        result = ob1 / ob2;
        cout << "Initial Division Result: ";
        result.display();
        break;

    default:
        cout << "Invalid choice!\n";
        return 0;
    }

    char inc_dec;
    cout << "\n(+ for increment, - for decrement, n for no): ";
    cin >> inc_dec;
    if (inc_dec == '+')
    {
        result++;
        cout << "After increment: ";
        result.display();
    }
    else if (inc_dec == '-')
    {
        result--;
        cout << "After decrement: ";
        result.display();
    }

    int extra;
    cout << "Enter the integer to add: ";
    cin >> extra;
    calculator temp(extra);
    result += temp;
    cout << "After adding " << extra << ": ";
    result.display();

    cout << "\nFinal Result: ";
    result.display();

    return 0;
}



```

## **Output 02:** 
<p align="center">
<img width="845" height="838" alt="Image" src="https://github.com/user-attachments/assets/1ac8b737-3a98-4ce7-a8eb-88645fe17ced" />

</p>

## **Experiment No: 03**
## **Experiment Name : Write necessary code for the following formula. ob1=ob2=ob3=ob4**
## **Submission Date: August 11, 2025**

## **Code 03:**
```C++
#include <bits/stdc++.h>
using namespace std;

class Obj_Ass
{
    int a;

public:
    Obj_Ass(int x = 0)
    {
        a = x;
    }

    Obj_Ass operator=(Obj_Ass o)
    {
        a = o.a;
        return *this;
    }

    void display()
    {
        cout << "a = " << a << endl;
    }
};

int main()
{
    Obj_Ass ob1(10), ob2(20), ob3(30), ob4(40);

    ob1 = ob2 = ob3 = ob4;

    ob1.display();
    ob2.display();
    ob3.display();
    ob4.display();

    return 0;
}



```

## **Output 03:** 
<p align="center">
<img width="845" height="414" alt="Image" src="https://github.com/user-attachments/assets/a97148a4-831d-4d0c-b2c6-6fa2bec02503" />

</p>

## **Experiment No: 04**
## **Experiment Name : A game using Operator Overloading.**
## **Submission Date: August 11, 2025**

## **Code 04:**
```C++
#include <iostream>
using namespace std;

class Score
{
    int points;

public:
    Score(int p = 0)
    {
        points = p;
    }

    // Unary operators
    Score operator++()
    {
        points++;
        return *this;
    } // correct answer
    Score operator--()
    {
        points--;
        return *this;
    } // wrong answer

    // Binary + (add one score to another)
    Score operator+(Score &other)
    {
        points = points + other.points;
        return *this;
    }

    // Comparisons
    bool operator>(Score &other)
    {
        if (points > other.points)
            return true;
        else
            return false;
    }
    bool operator<(Score &other)
    {
        if (points < other.points)
            return true;
        else
            return false;
    }

    // Display score
    void display()
    {
        cout << points;
    }

    // Get score value
    int getPoints()
    {
        return points;
    }
};

int main()
{
    Score player1(0), player2(0);

    // Questions & answers
    string questions[5] = {
        "Is RUET in Rajshahi? (yes (1) / no (0)): ",
        "Is 2 + 2 equal to 5? (yes (1) / no (0)): ",
        "Are you Human? (yes (1) / no (0)): ",
        "Is the Sun a planet? (yes (1) / no (0)): ",
        "Do humans need oxygen to survive? (yes (1) / no (0)): "};
    string correctAnswers[5] = {"1", "0", "1", "0", "1"};

    cout << "Welcome to the Quiz Game!\n";
    cout << "Answer 5 questions each (yes/no). Correct = +1, Wrong = -1.\n\n";

    // Player 1 answers
    cout << "Player 1's turn:\n";
    for (int i = 0; i < 5; i++)
    {
        string ans;
        cout << "Q" << i + 1 << ": " << questions[i];
        cin >> ans;
        if (ans == correctAnswers[i])
            ++player1;
        else
            --player1;
    }

    // Player 2 answers
    cout << "\nPlayer 2's turn:\n";
    for (int i = 0; i < 5; i++)
    {
        string ans;
        cout << "Q" << i + 1 << ": " << questions[i];
        cin >> ans;
        if (ans == correctAnswers[i])
            ++player2;
        else
            --player2;
    }

    // Show final scores
    cout << "\nFinal Scores:\n";
    cout << "Player 1: ";
    player1.display();
    cout << endl;
    cout << "Player 2: ";
    player2.display();
    cout << endl;

    // Announce winner
    if (player1 > player2)
        cout << "\nWinner: Player 1 \n";
    else if (player1 < player2)
        cout << "\nWinner: Player 2 \n";
    else
        cout << "\nIt's a tie!\n";

    return 0;
}



```

## **Output 04:** 
<p align="center">
<img width="855" height="1151" alt="Image" src="https://github.com/user-attachments/assets/a496f3f1-fb14-400f-ad35-fa9c4e9a2ead" />
</p>
