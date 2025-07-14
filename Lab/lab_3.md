## **Lab No : 03**

## **Experiment No : 01**
## **Experiment Name : Bonus Calculator**
## **Submission Date : July 14, 2025**

## **Code 1 :**
```C++
 #include <iostream>
using namespace std;

class Employee
{
private:
    string name;
    int employeeID;
    double baseSalary;

public:
    Employee(string n, int id, double salary)
    {
        name = n;
        employeeID = id;
        baseSalary = salary;
    }

    friend class HRDepartment;
};

class PermanentEmployee : public Employee
{
private:
    int yearsOfService;

public:
    PermanentEmployee(string n, int id, double salary, int years)
        : Employee(n, id, salary)
    {
        yearsOfService = years;
    }

    friend class HRDepartment;
};

class ContractEmployee : public Employee
{
private:
    int contractDuration;

public:
    ContractEmployee(string n, int id, double salary, int duration)
        : Employee(n, id, salary)
    {
        contractDuration = duration;
    }

    friend class HRDepartment;
};

class HRDepartment
{
public:
    void calculateBonus(PermanentEmployee &p)
    {
        double bonus = p.baseSalary * 0.10 + 1000 * p.yearsOfService;
        cout << "Permanent Employee, " << p.name << ": " << bonus << endl;
    }

    void calculateBonus(ContractEmployee &c)
    {
        double bonus = c.baseSalary * 0.05;
        cout << "Contract Employee, " << c.name << ": " << bonus << endl;
    }
};

int main()
{

    PermanentEmployee Nuhid("Nuhid", 1, 50000, 5);
    ContractEmployee Taufic("Taufic", 2, 50000, 12);

    HRDepartment hr;

    hr.calculateBonus(Nuhid);
    hr.calculateBonus(Taufic);

    return 0;
}



```

## **Output :** 
<p align="center">

<img width="388" height="44" alt="Image" src="https://github.com/user-attachments/assets/7f25775d-0f03-45f4-ab1b-58de261e2885" />


</p>



## **Experiment No : 02**
## **Experiment Name : Constructor Inheritance**
## **Submission Date : June 23, 2025**

## **Code 2 :**
```C++
 #include <bits/stdc++.h>
using namespace std;

class Grand
{
private:
    int a;

protected:
    int b;

public:
    int c;
    Grand(int x, int y, int z)
    {
        a = x;
        b = y;
        c = z;
    }
    void display()
    {
        cout << "a = " << a << ", b = " << b << ", c = " << c << endl;
    }
};

class p1 : public Grand
{
public:
    p1(int x, int y, int z) : Grand(x, y, z)
    {
        cout << "p1 constructor called" << endl;
    }
};

class p2 : public p1
{
public:
    p2(int x, int y, int z) : p1(x, y, z)
    {
        cout << "p2 constructor called" << endl;
    }
};

int main()
{
    cout << "Creating object of p2 class:" << endl;
    p2 obj(10, 20, 30);
    obj.display();
    return 0;
}



```

## **Output :** 
<p align="center">

<img width="388" height="83" alt="Image" src="https://github.com/user-attachments/assets/d4869345-e664-4ae6-9551-ccd2962a3f14" />


</p>



## **Experiment No : 03**
## **Experiment Name : Constructor in Multilevel Inheritance**
## **Submission Date : June 23, 2025**

## **Code 3 :**
```C++
 #include <iostream>
using namespace std;

class Base {
public:
    string pub;

    Base(string msg) {
        pub = msg;
        cout << "Base constructor called\n";
    }

protected:
    string pro = "I am protected from Base";

private:
    string pri = "I am private from Base";
};

class D1 : protected Base {
public:
    D1(string msg) : Base(msg) {
        cout << "D1 constructor called\n";
    }

    void show() {
        cout << "D1:\n";
        cout << pub << endl;
        cout << pro << endl;
    }
};

class D2 : private D1 {
public:
    D2(string msg) : D1(msg) {
        cout << "D2 constructor called\n";
    }

    void show2() {
        cout << "D2:\n";
        cout << pub << endl;
        cout << pro << endl;
    }
};

int main() {
    D2 d2("I am public from Base - via parameter");

    cout << "\nCalling functions:\n";
    d2.show2();

    return 0;
}



```

## **Output :** 
<p align="center">

<img width="388" height="473" alt="Image" src="https://github.com/user-attachments/assets/192bd092-643d-4cbf-8f0d-336b8167b7d4" />

</p>



## **Experiment No : 04**
## **Experiment Name : Constructor in Multilevel Inheritance**
## **Submission Date : June 23, 2025**

## **Code 4 :**
```C++
#include <iostream>
using namespace std;

class Base {
public:
    string pub = "I am public from Base";

protected:
    string pro = "I am protected from Base";

private:
    string pri = "I am private from Base";
};

class D1 : protected Base {
public:
    void show() {
        cout << "D1:\n";
        cout << pub << endl;
        cout << pro << endl;
    }
};

class D2 : private D1 {
public:
    void show2() {
        cout << "D2:\n";
        cout << pub << endl;
        cout << pro << endl;
    }
};

int main() {
    Base b;
    D1 d1;
    D2 d2;

    cout << "main:\n";
    cout << b.pub << endl;

    d1.show();
    d2.show2();

    return 0;
}
 


```

## **Output :** 
<p align="center">

<img width="388" height="617" alt="Image" src="https://github.com/user-attachments/assets/7b1fd395-fdf2-425b-9595-8461e3ff70af" />
</p>
