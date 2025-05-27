<p align="center">
  <h1><strong>Codeforces</strong></h1>
</p>



<p> Submission link : https://codeforces.com/submissions/Yousuf2723 </p>

## *Number of problem solved:  (Using OOP)*
## *From : *


----------
## **Experiment No : 01**

## **Code :**
```C++
#include <iostream>
using namespace std;

class Grand {
public:
    void showGrandPublic() {
        cout << "Grand public method" << endl;
    }

protected:
    void showGrandProtected() {
        cout << "Grand protected method" << endl;
    }

private:
    void showGrandPrivate() {
        cout << "Grand private method" << endl;
    }
};

class Father : public Grand {
public:
    void showFatherPublic() {
        cout << "Father public method" << endl;
        showGrandProtected();
    }

protected:
    void showFatherProtected() {
        cout << "Father protected method" << endl;
    }

private:
    void showFatherPrivate() {
        cout << "Father private method" << endl;
    }
};

class Child : public Father {
public:
    void showChildPublic() {
        cout << "Child public method" << endl;
        showGrandProtected();
        showFatherProtected();
    }

protected:
    void showChildProtected() {
        cout << "Child protected method" << endl;
    }

private:
    void showChildPrivate() {
        cout << "Child private method" << endl;
    }
};

int main() {
    Grand g;
    Father f;
    Child c;

    g.showGrandPublic();
    f.showGrandPublic();
    f.showFatherPublic();
    c.showGrandPublic();
    c.showFatherPublic();
    c.showChildPublic();

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/edb0cbad-b251-4c30-b354-34464c1b144d)

----------
## **Experiment No : 02**

## **Code :**
```C++
#include <iostream>
using namespace std;

class Grand {
public:
    void showGrandPublic() {
        cout << "Grand public method" << endl;
    }

protected:
    void showGrandProtected() {
        cout << "Grand protected method" << endl;
    }

private:
    void showGrandPrivate() {
        cout << "Grand private method" << endl;
    }
};

class Father : public Grand {
public:
    void showFatherPublic() {
        cout << "Father public method" << endl;
        showGrandProtected();
    }

protected:
    void showFatherProtected() {
        cout << "Father protected method" << endl;
    }

private:
    void showFatherPrivate() {
        cout << "Father private method" << endl;
    }
};

class Child : public Father {
public:
    void showChildPublic() {
        cout << "Child public method" << endl;
        showGrandProtected();
        showFatherProtected();
    }

protected:
    void showChildProtected() {
        cout << "Child protected method" << endl;
    }

private:
    void showChildPrivate() {
        cout << "Child private method" << endl;
    }
};

int main() {
    Grand g;
    Father f;
    Child c;

    g.showGrandPublic();
    f.showGrandPublic();
    f.showFatherPublic();
    c.showGrandPublic();
    c.showFatherPublic();
    c.showChildPublic();

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/494ff5e1-e9a5-4403-a646-aa49e6a45423)

----------

## **Experiment No : 02**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

class HRDepartment;

class Employee {
private:
    string name;
    int employeeID;
    double baseSalary;
public:
    Employee(string nm, int id, double salary)
        : name(nm), employeeID(id), baseSalary(salary) {}
    friend class HRDepartment;
};

class PermanentEmployee : public Employee {
private:
    int yearsOfService;
public:
    PermanentEmployee(string nm, int id, double salary, int years)
        : Employee(nm, id, salary), yearsOfService(years) {}
    friend class HRDepartment;
};

class ContractEmployee : public Employee {
private:
    int contractDuration;
public:
    ContractEmployee(string nm, int id, double salary, int duration)
        : Employee(nm, id, salary), contractDuration(duration) {}
    friend class HRDepartment;
};

class HRDepartment {
public:
    void displayBonus(PermanentEmployee &pe) {
        double bonus = 0.10 * pe.baseSalary + 1000 * pe.yearsOfService;
        cout << "Bonus for Permanent Employee " << pe.name << ": " << bonus << endl;
    }
    void displayBonus(ContractEmployee &ce) {
        double bonus = 0.05 * ce.baseSalary;
        cout << "Bonus for Contract Employee " << ce.name << ": " << bonus << endl;
    }
};

int main() {
    PermanentEmployee permEmp("John", 1001, 50000, 5);
    ContractEmployee contEmp("Alice", 1002, 50000, 12);

    HRDepartment hr;
    hr.displayBonus(permEmp);
    hr.displayBonus(contEmp);

    return 0;
}

```

## **Output :**
![Image](https://github.com/user-attachments/assets/37ec69b9-48a3-41e0-9815-ab0b0919dd85)

----------

## **Experiment No : 02**

## **Code :**
```C++
#include <iostream>
#include <string>
using namespace std;

class ProjectManager;

class TeamMember {
private:
    string name;
    int memberID;
    double hourlyRate;
public:
    TeamMember(string nm, int id, double rate)
        : name(nm), memberID(id), hourlyRate(rate) {}
    friend class ProjectManager;
};

class Developer : public TeamMember {
private:
    int linesOfCode;
public:
    Developer(string nm, int id, double rate, int loc)
        : TeamMember(nm, id, rate), linesOfCode(loc) {}
    friend class ProjectManager;
};

class Tester : public TeamMember {
private:
    int bugsFound;
public:
    Tester(string nm, int id, double rate, int bugs)
        : TeamMember(nm, id, rate), bugsFound(bugs) {}
    friend class ProjectManager;
};

class ProjectManager {
public:
    void displayCost(Developer &dev) {
        double cost = dev.hourlyRate * 160 + 0.1 * dev.linesOfCode;
        cout << "Cost for Developer " << dev.name << ": " << cost << endl;
    }
    void displayCost(Tester &tst) {
        double cost = tst.hourlyRate * 160 + 50 * tst.bugsFound;
        cout << "Cost for Tester " << tst.name << ": " << cost << endl;
    }
};

int main() {
    Developer dev("Raj", 2001, 200, 20000);
    Tester tst("Neha", 2002, 150, 140);

    ProjectManager pm;
    pm.displayCost(dev);
    pm.displayCost(tst);

    return 0;
}
```

## **Output :**
![Image](https://github.com/user-attachments/assets/07c3564e-c647-423c-a04b-98c21a112ce4)

----------
