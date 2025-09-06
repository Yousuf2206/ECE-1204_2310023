## **Lab: 10**
## **Task No: 01**
## **Task name: Find Maximum of Two Values**
## **Code 01:**
```C++
#include <iostream>
using namespace std;

template <typename T>
T getMax(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    cout << getMax(5, 10) << endl;
    cout << getMax(3.5, 2.7) << endl;
    cout << getMax('a', 'z') << endl;
}

```

## **Output 01:** 
<p align="center">
<img width="1181" height="293" alt="image" src="https://github.com/user-attachments/assets/001c0082-8f74-42f3-8bdc-ac9931aa2eb8" />=
</p>

## **Task No: 02**
## **Task name: Print Array Elements.**
## **Code 01:**
```C++
#include <iostream>
using namespace std;

template <typename T>
void printArray(T arr[], int size) {
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int nums[] = {1, 2, 3, 4, 5};
    double decs[] = {1.1, 2.2, 3.3};
    char letters[] = {'A', 'B', 'C'};

    printArray(nums, 5);
    printArray(decs, 3);
    printArray(letters, 3);
}
```
## **Output 01:** 
<p align="center">
<img width="1169" height="327" alt="image" src="https://github.com/user-attachments/assets/88ad06f8-47fb-4812-b133-71355725aec9" />
</p>

## **Task No: 03**
## **Task name: Write a function template findMaxIndex(T arr[], int size) that returns the 
index of the maximum element in an array.**
## **Code 01:**
```C++
#include <iostream>
using namespace std;

template <typename T>
int findMaxIndex(T arr[], int size) {
    int maxIndex = 0;
    for (int i = 1; i < size; i++)
        if (arr[i] > arr[maxIndex])
            maxIndex = i;
    return maxIndex;
}

int main() {
    int nums[] = {1, 7, 3, 9, 5};
    double decs[] = {2.2, 5.5, 1.1, 4.4};
    char letters[] = {'A', 'Z', 'M', 'B'};

    cout << findMaxIndex(nums, 5) << endl;
    cout << findMaxIndex(decs, 4) << endl;
    cout << findMaxIndex(letters, 4) << endl;
}
```

## **Output 01:** 
<p align="center">
<img width="1150" height="265" alt="image" src="https://github.com/user-attachments/assets/89e7c6bc-c3e1-4e62-9bd0-49d60b8776f8" />
</p>

## **Task No: 04**
## **Task name: Generic Function with Default Arguments.**
## **Code 01:**
```C++
#include <iostream>
using namespace std;

template <typename T>
T multiply(T a, T b = 1) {
    return a * b;
}

int main() {
    cout << multiply(5, 3) << endl;
    cout << multiply(7) << endl;
    cout << multiply(2.5, 4.0) << endl;
    cout << multiply(3.5) << endl;
}
```

## **Output 01:** 
<p align="center">
<img width="1152" height="355" alt="image" src="https://github.com/user-attachments/assets/141a241a-0786-44fe-bec4-9b653f15afc4" />
</p>

## **Task No: 05**
## **Task name: Overloaded add() Function with Special Case.**
## **Code 01:**
```C++
#include <iostream>
#include <string>
using namespace std;

template <typename T>
T add(T a, T b) {
    return a + b;
}

string add(const char* a, const char* b) {
    return string(a) + string(b);
}

int main() {
    cout << add(5, 10) << endl;
    cout << add("Hello, ", "World!") << endl;
}
```

## **Output 01:** 
<p align="center">
<img width="1168" height="245" alt="image" src="https://github.com/user-attachments/assets/da150769-f9da-4231-b662-54253af14156" />
</p>

## **Task No: 06**
## **Task name: Age Validation.**
## **Code 01:**
```C++
#include <iostream>
#include <stdexcept>
using namespace std;

void checkAge(int age) {
    if (age < 0 || age > 150)
        throw invalid_argument("Invalid age");
}

int main() {
    int age;
    cout << "Enter age: ";
    cin >> age;

    try {
        checkAge(age);
        cout << "Age is valid: " << age << endl;
    } catch (const invalid_argument& e) {
        cout << "Invalid age entered" << endl;
    }
}
```

## **Output 01:** 
<p align="center">
<img width="1176" height="427" alt="image" src="https://github.com/user-attachments/assets/c2e1c32e-f635-495b-99ec-362a6fa48546" />
</p>

## **Task No: 07**
## **Task name: Student Marks Validation.**
## **Code 01:**
```C++
#include <iostream>
#include <exception>
using namespace std;

class InvalidMarkException : public exception {
public:
    const char* what() const noexcept override {
        return "Invalid mark entered";
    }
};

void validateMark(int mark) {
    if (mark < 0 || mark > 100)
        throw InvalidMarkException();
}

int main() {
    int marks[5];

    for (int i = 0; i < 5; i++) {
        cout << "Enter mark for subject " << i + 1 << ": ";
        cin >> marks[i];
        try {
            validateMark(marks[i]);
        } catch (const InvalidMarkException& e) {
            cout << e.what() << endl;
            return 1;
        }
    }

    cout << "All marks are valid." << endl;
}
```

## **Output 01:** 
<p align="center">
<img width="1189" height="687" alt="image" src="https://github.com/user-attachments/assets/2fe20cdc-8a55-4a58-8042-87800241d5b5" />
</p>

## **Task No: 08**
## **Task name: Nested Try-Catch Blocks.**
## **Code 01:**
```C++
#include <iostream>
#include <stdexcept>
using namespace std;

int main() {
    int arr[3] = {10, 20, 30};

    try {
        try {
            int a = 10, b = 0;
            if (b == 0)
                throw runtime_error("Arithmetic error: division by zero");
            int c = a / b;
            cout << c << endl;
        } catch (const runtime_error& e) {
            cout << "Inner catch: " << e.what() << endl;
        }

        int index = 5;
        if (index < 0 || index >= 3)
            throw out_of_range("Array index out of range");
        cout << arr[index] << endl;

    } catch (const out_of_range& e) {
        cout << "Outer catch: " << e.what() << endl;
    }

    return 0;
}
```

## **Output 01:** 
<p align="center">
<img width="1193" height="227" alt="image" src="https://github.com/user-attachments/assets/d0b6796a-bc60-4f20-80d0-605fe7a4df3b" />
</p>

## **Experiment No: 01 [ From Book ]**
## **Code 01:**
```C++
#include <bits/stdc++.h>
using namespace std;

int main() {
    int x = 7;
    try {
        if (x % 2 != 0) {
            throw -1;
        }
    }
    catch (int e) {
        cout << "Exception Caught: " << e;
    }
    return 0;
}
```

## **Experiment No: 02 [ From Book ]**
## **Code 02:**
```C++

#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> v = {1, 2, 3};
    
    try {
        v.at(10);
    }
    catch (out_of_range e) {
        cout << "Caught: " << e.what();
    }
    return 0;
}
```

## **Experiment No: 03 [ From Book }**
## **Code 03:**
```C++
#include <bits/stdc++.h>
using namespace std;

int main() {
    try {
        int choice;
        cout << "Enter 1 for invalid argument, "
            << "2 for out of range: ";
        cin >> choice;

        if (choice == 1) {
            throw invalid_argument("Invalid argument");
        }
        else if (choice == 2) {
            throw out_of_range("Out of range");
        }
        else {
            throw "Unknown error";
        }

    }
    catch (invalid_argument e) {
        cout << "Caught exception: " << e.what() << endl;
    }
    catch (out_of_range e) {
        cout << "Caught exception: " << e.what() << endl;
    }
    catch (...) {
        cout << "Caught an unknown exception." << endl;
    }
    return 0;
}
```

## **Experiment No: 04 [ From Book }**
## **Code 04:**
```C++
#include <bits/stdc++.h>
using namespace std;

int main() {
    try {
        throw runtime_error("This is runtime exception");
    }
    
    catch (runtime_error e) {
        cout << "Caught: " << e.what();
    }

    return 0;
}
```

## **Experiment No: 05 [ From Book }**
## **Code 05:**
```C++
#include <bits/stdc++.h>
using namespace std;

int main() {
    try {
        throw runtime_error("This is runtime exception");
    }
    catch (exception& e) {
        cout << "Caught: " << e.what();
    }

    return 0;
}
```
