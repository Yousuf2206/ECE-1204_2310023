
## **Lab: 04**

## **Experiment No : 01**
## **Experiment Name : Virtual Function**
## **Submission Date : July 14, 2025**

## **Code 1 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class A
{
public:
    virtual void show()
    {
        cout << "Base Class" << endl;
    }
};

class derived : public A
{
public:
    void show() override
    {
        cout << "Derived Class" << endl;
    }
};

int main()
{
    A *p;
    derived q;

    p = &q;

    p->show();
    q.show();

    return 0;
}


```

## **Output :** 
<p align="center">

<img width="398" height="166" alt="Image" src="https://github.com/user-attachments/assets/a9b0e58d-d48d-4e11-af6c-403f47a0f525" />

</p>




## **Experiment No : 02**
## **Experiment Name : Problem 01**
## **Submission Date : July 14, 2025**

## **Code 2:**
```C++
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void makeSound() {
        cout << "Some generic animal sound" << endl;
    }
};

class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Woof! Woof!" << endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        cout << "Meow! Meow!" << endl;
    }
};

int main() {
    Dog dog;
    Cat cat;

    Animal& a1 = dog;
    Animal& a2 = cat;

    a1.makeSound();
    a2.makeSound();

    return 0;
}


```

## **Output :** 
<p align="center">

<img width="398" height="270" alt="Image" src="https://github.com/user-attachments/assets/b759db02-98d2-4cbe-b818-82ecfb791bcb" />

</p>




## **Experiment No : 03**
## **Experiment Name : Problem 2**
## **Submission Date : July 14, 2025**

## **Code 3:**
```C++
#include <iostream>
using namespace std;

class Person
{
public:
    string name = "Person";
    virtual void show_info()
    {
        cout << name << endl;
    }
};
class Student : public Person
{
public:
    string name = "Student";
    void show_info()
    {
        cout << name << endl;
    }
};

void call_b_value(Person obj)
{
    obj.show_info();
}
void call_b_reff(Person &obj)
{
    obj.show_info();
}

int main()
{
    Person p;
    Student s;
    call_b_value(p);
    cout << endl;
    call_b_reff(s);

    return 0;
}


```

## **Output :** 
<p align="center">

<img width="398" height="330" alt="Image" src="https://github.com/user-attachments/assets/7dde2ae0-72a3-4d33-adb8-84e79397d753" />

</p>



## **Experiment No : 04**
## **Experiment Name : Problem 3**
## **Submission Date : July 14, 2025**

## **Code 4 :**
```C++
#include <iostream>
using namespace std;

class Vehicle
{
public:
    virtual void start()
    {
        cout << "This is base function" << endl;
    }
};

class Car : public Vehicle
{
public:
    void start() override
    {
        cout << "This is car" << endl;
    }
};

class Bike : public Vehicle
{
public:
    void start() override
    {
        cout << "This is bike" << endl;
    }
};

int main()
{
    Car carObject;
    Bike bikeObject;

    Vehicle *arr[2];
    arr[0] = &carObject;
    arr[1] = &bikeObject;

    arr[0]->start();
    arr[1]->start();

    return 0;
}


```

## **Output :** 
<p align="center">

<img width="398" height="268" alt="Image" src="https://github.com/user-attachments/assets/062037e6-015a-41a3-b212-9ca05f3da517" />

</p>


## **Experiment No : 05**
## **Experiment Name : Problem 4 **
## **Submission Date : July 14, 2025**

## **Code 5:**
```C++
#include <iostream>
using namespace std;

class LibraryItem
{
public:
    virtual void displayInfo()
    {
        cout << "Library Item Info" << endl;
    }
};

class Book : public LibraryItem
{
public:
    void displayInfo() override
    {
        cout << "Book Info: Title - 'The Art by Nuhid Taufic'" << endl;
    }
};

class Magazine : public LibraryItem
{
public:
    void displayInfo() override
    {
        cout << "Magazine Info: Title - '31 July'" << endl;
    }
};

void showLibraryItems(LibraryItem *items[], int size)
{
    for (int i = 0; i < size; ++i)
    {
        items[i]->displayInfo();
    }
}

int main()
{
    Book book1;
    Magazine mag1;

    LibraryItem *library[2];
    library[0] = &book1;
    library[1] = &mag1;

    showLibraryItems(library, 2);

    return 0;
}


```

## **Output :** 
<p align="center">

<img width="398" height="290" alt="Image" src="https://github.com/user-attachments/assets/4c6d767b-7ead-4d66-b8c2-fdd594e21b36" />

</p>
