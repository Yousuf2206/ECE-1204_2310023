## **Lab: 06**

## **Experiment No : 01**
## **Submission Date : 21 July, 2025**

## **Code 01:**
```C++
/*
Create a class Student with attributes name, roll, and marks. Initialize an array of 5 students 
and write a program to input and display the data for all students.
*/
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int roll;
    float marks;

    void input() {
        cout << "Enter name: "; 
        getline(cin, name);
        cout << "Enter roll number: ";
        cin >> roll;
        cin.ignore();  // Clear newline left in buffer
        cout << "Enter marks: ";
        cin >> marks;
        cin.ignore();  // Clear newline again for next input
    }

    void display() {
        cout << "Name: " << name << endl;
        cout << "Roll: " << roll << endl;
        cout << "Marks: " << marks << endl;
        cout << "---------------------------" << endl;
    }
};

int main() {
    const int SIZE = 5;
    Student students[SIZE];

    cout << "Enter data for " << SIZE << " students:\n";
    for (int i = 0; i < SIZE; i++) {
        cout << "\nStudent " << i + 1 << ":\n";
        students[i].input();
    }

    cout << "\nDisplaying student data:\n";
    for (int i = 0; i < SIZE; i++) {
        cout << "\nStudent " << i + 1 << ":\n";
        students[i].display();
    }

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="690" height="1060" alt="Image" src="https://github.com/user-attachments/assets/ac46d46c-b1ec-4fde-8a61-e7e1f4c80fb9" />
<img width="753" height="1141" alt="Image" src="https://github.com/user-attachments/assets/21f6088f-057f-413b-80ed-89177755874d" />

</p>

## **Experiment No : 02**
## **Submission Date : 21 July, 2025**

## **Code 02:**
```C++
/*
Create a class Book with a function display(). Create a pointer to a Book object and call 
display() using that pointer. Allocate memory dynamically. 
*/
#include <iostream>
using namespace std;

class Book {
public:
    void display() {
        cout << "This is a Book." << endl;
    }
};

int main() {
    // Dynamically allocate memory for a Book object
    Book* ptr = new Book;

    // Call display() using the pointer
    ptr->display();

    // Free the allocated memory
    delete ptr;

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="803" height="180" alt="Image" src="https://github.com/user-attachments/assets/d6a234b3-db9b-45f2-bae6-84ac254b8eb0" />

</p>

## **Experiment No : 03**
## **Submission Date : 21 July, 2025**

## **Code 03:**
```C++
/*
Create a class Rectangle with private members length and breadth. Use the this pointer to 
differentiate between local and member variables in the constructor.
*/
#include <iostream>
using namespace std;

class Rectangle {
private:
    int length;
    int breadth;

public:
    // Constructor using 'this' pointer
    Rectangle(int length, int breadth) {
        this->length = length;
        this->breadth = breadth;
    }

    int area() {
        return length * breadth;
    }

    void display() {
        cout << "Length: " << length << ", Breadth: " << breadth << endl;
        cout << "Area: " << area() << endl;
    }
};

int main() {
    int l, b;
    cout << "Enter length and breadth: ";
    cin >> l >> b;

    Rectangle rect(l, b);
    rect.display();

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="748" height="241" alt="Image" src="https://github.com/user-attachments/assets/ea1e3ed6-c048-427c-9d67-2e04e195b630" />

</p>

## **Experiment No : 04**
## **Submission Date : 21 July, 2025**

## **Code 04:**
```C++
/*
Create a program to dynamically allocate memory for an array of 10 integers, input values, 
calculate their sum, and deallocate memory properly using delete.
*/
#include <iostream>
using namespace std;

int main() {
    // Dynamically allocate memory for 10 integers
    int* arr = new int[10];

    cout << "Enter 10 integers:" << endl;
    for (int i = 0; i < 10; ++i) {
        cin >> arr[i];
    }

    // Calculate the sum
    int sum = 0;
    for (int i = 0; i < 10; ++i) {
        sum += arr[i];
    }

    cout << "Sum of the elements: " << sum << endl;

    // Deallocate memory
    delete[] arr;

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="794" height="269" alt="Image" src="https://github.com/user-attachments/assets/e947afb6-f6cc-4605-b7d4-755457086cc1" />

</p>

## **Experiment No : 05**
## **Submission Date : 21 July, 2025**

## **Code 05:**
```C++
/*
Create a class Employee that has a constructor and destructor. Dynamically allocate an 
object of this class and verify constructor and destructor execution using new and delete. 
*/
#include <iostream>
using namespace std;

class Employee {
public:
    // Constructor
    Employee() {
        cout << "Constructor called: Employee object created." << endl;
    }

    // Destructor
    ~Employee() {
        cout << "Destructor called: Employee object destroyed." << endl;
    }
};

int main() {
    // Dynamically create an Employee object
    Employee* emp = new Employee;

    // Optional: Work with the object
    cout << "Employee is working..." << endl;

    // Delete the dynamically created object
    delete emp;

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="863" height="301" alt="Image" src="https://github.com/user-attachments/assets/c61d4d00-6317-4d29-905a-a8ae1aa54e4d" />

</p>
