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
