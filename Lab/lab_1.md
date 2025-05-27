<p align="center">
  <h1><strong>Codeforces</strong></h1>
</p>

![Image](https://github.com/user-attachments/assets/2bf72086-e5f6-4883-b041-d0e6cbe58700)

<p> Submission link : https://codeforces.com/submissions/Yousuf2723 </p>

## *Number of Solves: 2*
## *From 20 to 27 May 2025*


----------
## **Experiment No : 01**

## **Code :**
```C++
#include <iostream>
using namespace std;

class Rectangle {
private:
    double length;
    double width;

public:
    Rectangle(double l, double w) {
        length = l;
        width = w;
    }

    double calculateArea() {
        return length * width;
    }

    double calculatePerimeter() {
        return 2 * (length + width);
    }

    void display() {
        cout << "\nLength: " << length << endl;
        cout << "Width : " << width << endl;
        cout << "\nArea  : " << calculateArea() << endl;
        cout << "Perimeter: " << calculatePerimeter() << endl;
    }
};

int main() {
    double l, w;

    cout << "Enter length of the rectangle: ";
    cin >> l;
    cout << "Enter width of the rectangle: ";
    cin >> w;

    Rectangle rect(l, w);
    rect.display();

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/e9bb373c-7d4b-4f52-9c50-cba4cfa33cf5)

----------

## **Experiment No : 02 [ Using Constractor ]**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

class Car {
private:
    string company;
    string model;
    int year;

public:
    Car(string c, string m, int y) {
        company = c;
        model = m;
        year = y;
    }

    string getCompany() {
        return company;
    }

    string getModel() {
        return model;
    }

    int getYear() {
        return year;
    }

    void displayInfo() {
        cout << "Car Information:" << endl;
        cout << "Company: " << getCompany() << endl;
        cout << "Model  : " << getModel() << endl;
        cout << "Year   : " << getYear() << endl;
    }
};

int main() {
    string company, model;
    int year;

    cout << "Enter car company: ";
    getline(cin, company);

    cout << "Enter car model: ";
    getline(cin, model);

    cout << "Enter manufacturing year: ";
    cin >> year;

    Car myCar(company, model, year);

    cout << endl;
    myCar.displayInfo();

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/1061b635-ed52-47a4-b251-b4d8426fb70e)

----------

## **Experiment No : 02 [ Using Function ]**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

class Car {
private:
    string company;
    string model;
    int year;

public:
    void setCompany(string c) {
        company = c;
    }

    void setModel(string m) {
        model = m;
    }

    void setYear(int y) {
        year = y;
    }

    string getCompany() {
        return company;
    }

    string getModel() {
        return model;
    }

    int getYear() {
        return year;
    }

    void displayInfo() {
        cout << "Car Information:" << endl;
        cout << "Company: " << getCompany() << endl;
        cout << "Model  : " << getModel() << endl;
        cout << "Year   : " << getYear() << endl;
    }
};

int main() {
    Car myCar;
    string company, model;
    int year;

    cout << "Enter car company: ";
    getline(cin, company);

    cout << "Enter car model: ";
    getline(cin, model);

    cout << "Enter manufacturing year: ";
    cin >> year;

    myCar.setCompany(company);
    myCar.setModel(model);
    myCar.setYear(year);

    cout << endl;
    myCar.displayInfo();

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/bb60a649-e015-4cae-9556-38c0b995b350)

----------

## **Experiment No : 03**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

class Employee {
private:
    string name;
    int employeeID;
    double salary;

public:
    void setData(string n, int id) {
        name = n;
        employeeID = id;
    }

    void setSalary(double base, int performanceRating) {
        if (performanceRating >= 9) {
            salary = base * 1.5;
        } else if (performanceRating >= 7) {
            salary = base * 1.2;
        } else {
            salary = base;
        }
    }

    double getSalary() {
        return salary;
    }

    string getName() {
        return name;
    }
};

int main() {
    int n;
    cout << "Enter number of employees: ";
    cin >> n;

    Employee* employees = new Employee[n];
    string name;
    int id, rating;
    double baseSalary;

    for (int i = 0; i < n; i++) {
        cout << "\nEnter details for employee " << i + 1 << ":\n";
        cin.ignore();
        cout << "Name: ";
        getline(cin, name);
        cout << "Employee ID: ";
        cin >> id;
        cout << "Base Salary: ";
        cin >> baseSalary;
        cout << "Performance Rating (1-10): ";
        cin >> rating;

        employees[i].setData(name, id);
        employees[i].setSalary(baseSalary, rating);
    }

    double maxSalary = employees[0].getSalary();
    string topEmployee = employees[0].getName();

    for (int i = 1; i < n; i++) {
        if (employees[i].getSalary() > maxSalary) {
            maxSalary = employees[i].getSalary();
            topEmployee = employees[i].getName();
        }
    }

    cout << "\nEmployee with highest salary: " << topEmployee << " (Salary: " << maxSalary << ")" << endl;

    delete[] employees;
    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/10c82731-4acf-4cc2-aea3-aeece2fbdf13)

----------

## **Experiment No : 04**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s;
    cin >> s;
    if (s.length() > 1)
        swap(s[0], s[s.length() - 1]);
    cout << s << endl;
    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/b61f0056-42e5-4c7d-bcaf-e999454f1c19)

----------

## **Experiment No : 05**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s;
    getline(cin, s);
    if (s.rfind("c++", 0) == 0)
        cout << 1 << endl;
    else
        cout << 0 << endl;
    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/970192c1-69b5-4fa7-85a6-556ccfe3df5f)

----------

## **Experiment No : 06**

## **Code :**
```C++
#include<iostream>
using namespace std;

int main(){
    int num1, num2;
    cout << "Enter two numbers: ";
    cin >> num1 >> num2;

    if(abs(100 - num1) > abs(100 - num2)){
        cout << num2;
    }else{
        cout << num1;
    }
    
    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/cde86740-87e6-464b-87d0-cd5be525234e)

----------
