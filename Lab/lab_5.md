
## **Lab: 05**

## **Experiment No : 01**
## **Experiment Name : Task 01**
## **Submission Date : July 14, 2025**

## **Code 01 :**
```C++
#include <iostream>
using namespace std;

class Box
{
private:
    int length, width, height;

public:
    inline Box(int l, int w, int h)
    {
        length = l;
        width = w;
        height = h;
    }

    inline int volume()
    {
        return length * width * height;
    }

    inline void compareVolume(Box other)
    {
        int vol1 = volume();
        int vol2 = other.volume();

        if (vol1 > vol2)
        {
            cout << "Box 1 has a larger volume." << endl;
        }
        else if (vol1 < vol2)
        {
            cout << "Box 2 has a larger volume." << endl;
        }
        else
        {
            cout << "Both boxes have equal volume." << endl;
        }
    }
};

int main()
{
    Box box1(5, 4, 6);
    Box box2(3, 4, 5);

    cout << "Volume Box 1: " << box1.volume() << endl;
    cout << "Volume Box 2: " << box2.volume() << endl;

    box1.compareVolume(box2);

    return 0;
}



```

## **Output :** 
<p align="center">
<img width="398" height="63" alt="Image" src="https://github.com/user-attachments/assets/228f2a48-75b3-4ba8-b67c-644d97dceea9" />

</p>


## **Experiment No : 02**
## **Experiment Name : Task 02**
## **Submission Date : July 14, 2025**

## **Code 02 :**
```C++
#include <bits/stdc++.h>
using namespace std;

#define n 10

class stak
{
    int array[n];
    int tos;

public:
    stak()
    {
        tos = 0;
    }

    void push(char c)
    {
        if (tos == 10)
        {
            cout << "Stack Overflow" << endl;
            return;
        }
        array[tos++] = c;
    }

    char pop()
    {
        if (tos == 0)
        {
            cout << "Stuck in empty" << endl;
            return '\0';
        }

        return array[--tos];
    }

    void reverse()
    {
        for (int i = 0; i < tos / 2; i++)
        {
            char temp = array[i];
            array[i] = array[tos - 1 - i];
            array[tos - 1 - i] = temp;
        }
    }
};

int main()
{
    stak s1, s2;
    s1.push('a');
    s1.push('b');
    s1.push('c');

    s2 = s1;

    for (int i = 0; i < 3; i++)
    {
        cout << s1.pop() << endl;
    }

    s2.reverse();

    for (int i = 0; i < 3; i++)
    {
        cout << s2.pop() << endl;
    }
    return 0;
}


```

## **Output :** 
<p align="center">
<img width="398" height="123" alt="Image" src="https://github.com/user-attachments/assets/b42830cc-9b79-4b3e-8e8b-887d34cd668f" />
</p>


## **Experiment No : 03**
## **Experiment Name : Task 03**
## **Submission Date : July 14, 2025**

## **Code 03 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Person
{
public:
    string name;
    int age;
    string city;

    Person(string n, int a, string c)
    {
        name = n;
        age = a;
        city = c;
    }

    void display()
    {
        cout << "Name: " << name << ", Age: " << age << ", city: " << city << endl;
    }
};
void update_data_by_value(Person p)
{
    p.name = "Taufic";
    p.age = 10;
    p.city = "Rajshahi";
};

void update_data_by_ref(Person &p)
{
    p.name = "Taufic";
    p.age = 10;
    p.city = "Rajshahi";
};

int main()
{
    Person p1("Nuhid", 20, "Dhaka");

    cout << "By Value: " << endl;
    cout << "Berfore Update:" << endl;
    p1.display();
    update_data_by_value(p1);
    cout << "After Update:" << endl;
    p1.display();

    cout << "By Reff: " << endl;
    cout << "Berfore Update:" << endl;
    p1.display();
    update_data_by_ref(p1);
    cout << "After Update:" << endl;
    p1.display();

    return 0;
}


```

## **Output :** 
<p align="center">
<img width="398" height="206" alt="Image" src="https://github.com/user-attachments/assets/13662221-8f7c-4c37-8c1d-ececc5f9c578" />

</p>


## **Experiment No : 4.1**
## **Experiment Name : Task 04**
## **Submission Date : July 14, 2025**

## **Code 4.1 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Person
{
public:
    string name;
    int age;

    void input()
    {

        cout << "Input name: " << endl;
        cin >> name;
        cout << "Input Age: " << endl;
        cin >> age;
    }

    void display()
    {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main()
{
    Person *p = new Person;
    p->input();
    p->display();

    delete p;
    return 0;
}


```

## **Output :** 
<p align="center">
<img width="398" height="104" alt="Image" src="https://github.com/user-attachments/assets/88f3c45a-ece5-430c-a44a-9d5be87f7221" />

</p>


## **Experiment No : 4.2**
## **Experiment Name : Task 04**
## **Submission Date : July 14, 2025**

## **Code 4.2 :**
```C++
#include <bits/stdc++.h>
using namespace std;

class Person
{
public:
    string name;
    int age;

    void input()
    {

        cout << "Input name: " << endl;
        cin >> name;
        cout << "Input Age: " << endl;
        cin >> age;
    }

    void display()
    {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main()
{
    int n;
    cin >> n;
    Person *p = new Person[n];

    for (int i = 0; i < n; i++)
    {
        cout << "Student " << i + 1 << ":" << endl;
        p[i].input();
    }
    for (int i = 0; i < n; i++)
    {
        cout << "Student " << i + 1 << ":" << endl;
        p[i].display();
    }

    delete[] p;

    return 0;
}


```

## **Output :** 
<p align="center">
<img width="398" height="308" alt="Image" src="https://github.com/user-attachments/assets/7fddaeb8-b489-43ab-8cee-202f1035648a" />

</p>


## **Experiment No : 4.3**
## **Experiment Name : Task 04**
## **Submission Date : July 14, 2025**

## **Code 4.3 :**
```C++
#include <bits/stdc++.h>
using namespace std;

struct Person
{
    string name;
    int age;
};

int main()
{
    Person *p = new Person;
    cout << "Input Name: " << endl;
    cin >> p->name;

    cout << "Input Age: " << endl;
    cin >> p->age;

    cout << "Name: " << p->name << ", Age: " << p->age << endl;

    delete p;

    return 0;
}


```

## **Output :** 
<p align="center">
<img width="398" height="104" alt="Image" src="https://github.com/user-attachments/assets/8843e5f6-951e-42f0-9e2f-d53869d89d90" />
</p>




