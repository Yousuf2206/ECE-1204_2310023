## **Lab: 06**

## **Experiment No : 01**
## **Experiment Name : Design a system for input Student name, roll and CGPA and output Their informations and find topper and Honor Candidate**
## **Submission Date : July 14, 2025**

## **Code 01:**
```C++
#include <iostream>
using namespace std;

class RUET
{
protected:
    string name;
    int roll;

public:
    virtual void input()
    {
        cout << "Enter name: ";
        cin >> name;
        cout << "Enter roll: ";
        cin >> roll;
    }

    virtual void display()
    {
        cout << "Name: " << name << ", Roll: " << roll << endl;
    }

    virtual float getCGPA() { return 0.0; }
};

class ECE : public RUET
{
protected:
    string dept_name = "ECE";

public:
    void display() override
    {
        RUET::display();
        cout << "Department: " << dept_name << endl;
    }
};

class STUDENT : public ECE
{
    float cgpa;

public:
    void input() override
    {
        RUET::input();
        cout << "Enter CGPA: ";
        cin >> cgpa;
    }

    void display() override
    {
        ECE::display();
        cout << "CGPA: " << cgpa << endl;
        if (cgpa > 3.75)
            cout << "Honors Candidate" << endl;
    }

    float getCGPA() override
    {
        return cgpa;
    }
};

void findTopper(RUET *students[], int n)
{
    int topperIndex = 0;
    float maxCGPA = students[0]->getCGPA();

    for (int i = 1; i < n; i++)
    {
        if (students[i]->getCGPA() > maxCGPA)
        {
            maxCGPA = students[i]->getCGPA();
            topperIndex = i;
        }
    }

    cout << "\nTopper Information:\n";
    students[topperIndex]->display();
}

int main()
{
    int n;
    cout << "Number of students: ";
    cin >> n;
    RUET *students[n];

    for (int i = 0; i < n; i++)
    {
        cout << "\nEnter details: " << i + 1 << ":\n";
        students[i] = new STUDENT();
        students[i]->input();
    }

    cout << "All Students\n";
    for (int i = 0; i < n; i++)
    {
        students[i]->display();
        cout << endl;
    }

    findTopper(students, n);

    for (int i = 0; i < n; i++)
    {
        delete students[i];
    }

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="470" height="700" alt="Image" src="https://github.com/user-attachments/assets/345a510a-5aec-460f-9e7a-b9f63e52ebfe" />

</p>

## **Experiment No : 02**
## **Experiment Name : Passing Object to Function -1**
## **Submission Date : July 14, 2025**

## **Code 02:**
```C++
#include <iostream>
using namespace std;

class samp
{
    int i;

public:
    samp(int n) { i = n; }
    int get_i() { return i; }
};

int sqr_it(samp o)
{
    return o.get_i() * o.get_i();
}

int main()
{
    samp a(10), b(2);
    cout << sqr_it(a) << "\n";
    cout << sqr_it(b) << "\n";
    return 0;
}

```

## **Output 02:** 
<p align="center">

<img width="470" height="44" alt="Image" src="https://github.com/user-attachments/assets/56ac8173-2629-4369-8ef5-f2d034fe5334" />


</p>

## **Experiment No : 03**
## **Experiment Name : Passing Object to Function -2**
## **Submission Date : July 14, 2025**

## **Code 03:**
```C++
#include <iostream>
using namespace std;
class samp
{
    int i;

public:
    samp(int n) { i = n; }
    void set_i(int n) { i = n; }
    int get_i() { return i; }
};
void sqr_it(samp o)
{
    o.set_i(o.get_i() * o.get_i());
    cout << "Copy of a has i value of " << o.get_i() << endl;
}
int main()
{
    samp a(10);
    sqr_it(a);
    cout << "But , a.i is unchanged in main : ";
    cout << a.get_i() << endl;
    return 0;
}
```

## **Output 03:** 
<p align="center">

<img width="470" height="45" alt="Image" src="https://github.com/user-attachments/assets/238c1e5c-81e9-49a5-b4be-ef8efdc55b74" />


</p>

## **Experiment No : 04**
## **Experiment Name : Passing Object to Function -3**
## **Submission Date : July 14, 2025**

## **Code 04:**
```C++
#include <iostream>
using namespace std;
class samp
{
    int i;

public:
    samp(int n) { i = n; }
    void set_i(int n) { i = n; }
    int get_i() { return i; }
};
void sqr_it(samp *o)
{
    o->set_i(o->get_i() * o->get_i());
    cout << "Copy of a has i value of " << o->get_i();
    cout << "\n ";
}
int main()
{
    samp a(10);
    sqr_it(&a);
    cout << "Now , a in main () has been changed : ";
    cout << a.get_i() << endl;
    return 0;
}
```

## **Output 04:** 
<p align="center">
<img width="470" height="45" alt="Image" src="https://github.com/user-attachments/assets/99493e09-e68f-43f5-b237-4875298d80e6" />

</p>
