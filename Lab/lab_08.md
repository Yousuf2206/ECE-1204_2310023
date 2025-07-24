## **Lab: 08**

## **Experiment No : 01**
## **Submission Date : 28 July, 2025**

## **Code 01:**
```C++
#include <iostream>
using namespace std;

class Number {
private:
    int value;

public:
    // Default constructor
    Number() {
        value = 0;
    }

    // Parameterized constructor
    Number(int val) {
        value = val;
    }

    void display() {
        cout << "Value: " << value << endl;
    }
};

int main() {
    // using default constructor
    Number num1;

    // using parameterized constructor
    int userValue;
    cout << "Enter a number: ";
    cin >> userValue;
    Number num2(userValue);

    // Display values of both objects
    cout << "\nObject 1 (Default Constructor): ";
    num1.display();

    cout << "Object 2 (Parameterized Constructor): ";
    num2.display();

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="801" height="307" alt="Image" src="https://github.com/user-attachments/assets/a52ff9e1-72b7-4002-863d-3989d415beb1" />
</p>

## **Experiment No : 02**
## **Submission Date : 28 July, 2025**

## **Code 02:**
```C++
#include <iostream>
using namespace std;

class Rectangle {
private:
    int width, height;

public:
    // Default constructor
    Rectangle() {
        width = 1;
        height = 1;
    }

    // Parameterized constructor
    Rectangle(int w, int h) {
        width = w;
        height = h;
    }

    // Function to calculate area
    int area() {
        return width * height;
    }
};

int main() {
    // using default constructor
    Rectangle rect1;

    // using parameterized constructor
    Rectangle rect2(5, 3);

    cout << "Area of rectangle 1 (default constructor): " << rect1.area() << endl;
    cout << "Area of rectangle 2 (parameterized constructor): " << rect2.area() << endl;

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="933" height="240" alt="Image" src="https://github.com/user-attachments/assets/65085f15-1cc2-4186-81c5-1ae90cfd1b2b" />
</p>

## **Experiment No : 04**
## **Submission Date : 28 July, 2025**

## **Code 04:**
```C++
#include <iostream>
using namespace std;

class Number {
private:
    int* value;

public:
    Number(int val) {
        value = new int;
        *value = val;       
    }

    // Copy constructor (deep copy)
    Number(const Number& other) {
        value = new int;       
        *value = *(other.value);
    }

    // Function to print value and address
    void display() {
        cout << "Value: " << *value << ", Address: " << value << endl;
    }

    // Destructor to free memory
    ~Number() {
        delete value;
    }
};

int main() {
    Number num1(42);      
    Number num2 = num1;   // copy constructor

    cout << "Original object (num1): ";
    num1.display();

    cout << "Copied object (num2):   ";
    num2.display();

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="906" height="279" alt="Image" src="https://github.com/user-attachments/assets/899120df-0409-4a75-aaf1-6acc341ef3f2" />
</p>

## **Experiment No : 06 [ Codeforces Problem ]**
## **Submission Date : 28 July, 2025**

## **Code 06:**
```C++
#include <iostream>
using namespace std;

int main() {
    int t;
    cin >> t;

    while (t--) {
        int n;
        cin >> n;

        int count1 = 0, count2 = 0, x;

        for (int i = 0; i < n; i++) {
            cin >> x;
            if (x == 1)
                count1++;
            else
                count2++;
        }

        int total = count1 + (2 * count2);

        if (total % 2 != 0) {
            cout << "NO" << endl;
        } else {
            int h = total / 2;
            if (h % 2 != 0 && count1 == 0) {
                cout << "NO" << endl;
            } else {
                cout << "YES" << endl;
            }
        }
    }

    return 0;
}

```

## **Output 01:** 
<p align="center">
<img width="1763" height="160" alt="Image" src="https://github.com/user-attachments/assets/19a6f6dc-7a4e-42ed-9aaf-4c3425cb1af9" />
</p>
