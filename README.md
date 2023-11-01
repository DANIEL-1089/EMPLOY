#include <iostream>
#include <cstdlib>
#include <ctime>
#include <wchar.h>
#include <Windows.h>
#include <algorithm>
#include <vector>
#include <string>
#include <string.h>
#include <stdlib.h>
#include <cstring>
#include <conio.h>
#include <iomanip>
#include <process.h>


using namespace std;
const int LEN = 80;

class employee {
private:
    char name[LEN];
    unsigned long number;
public:
    void getdata() {
        cout << "Enter a last name: ";cin >> name;
        cout << "Enter a number: ";cin >> number;
    }
    void putdata() const {
        cout << "\n  Last name: " << name;
        cout << "\n  Number: " << number;
    }
};
class manager : public employee {
private:
    char title[LEN];
    double dues;
public:
    void getdata() {
        employee::getdata();
        cout << "\n Enter the position: ";cin >> title;
        cout << "\n Enter the amount of contributions to the golf club: ";cin >> dues;
    }
    void putdata() const {
        employee::putdata();
        cout << "\n  position: " << title;
        cout << "\n  the amount of contributions to the golf club: " << dues;
    }
};
class scients : public employee {
private:
    int pubs;
public:
    void getdata() {
        employee::getdata();
        cout << "  Enter the number of publications: "; cin >> pubs;
    }
    void putdata() const {
        cout << "\n  number of publications:  " << pubs;
    }
};
class laborer : public employee {
};


int main()
{
    manager m1, m2;
    scients s1;
    laborer l1;

    cout << endl;
    cout << "\n Entering information about the first manager";
    m1.getdata();

    cout << "\n Entering information about the second manager";
    m2.getdata();

    cout << "\nInformation about the first manager";
    m1.putdata();

    cout << "\nInformation about the second manager";
    m2.putdata();

    return 0;
}
