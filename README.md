# constructor-and-deconstructor
## AIM- To study and implement Constructors and Destructors
## THEORY- 
A constructor in C++ is a special member function of a class that initializes objects. It shares the same name as the class, has no return type, and is called automatically when an object is created. Constructors can be overloaded to allow multiple initialization options.
Types of Constructors:
Default Constructor: Takes no arguments, initializes members to default values. C++ generates one if not provided.
Parameterized Constructor: Takes arguments for specific initialization, allowing overloaded versions.
Copy Constructor: Creates a new object by copying an existing one.
Move Constructor: Transfers resources from a temporary object to a new one, optimizing performance.
Pros and Cons:
Default Constructor:
Advantages: Automatic initialization, easy object creation.
Disadvantages: Limited flexibility, unintended default values.
Parameterized Constructor:
Advantages: Custom initialization, flexibility, explicit value setting.
Disadvantages: Requires arguments, increases complexity.
Copy Constructor:
Advantages: Object duplication, deep copy support, consistency.
Disadvantages: Performance overhead, unintended copies, complexity.
Constructor Defined Outside the Class:
Advantages: Clear separation, better organization, reusability.
Disadvantages: Code fragmentation, maintenance difficulty.

Destructors
A destructor is a special member function which destroys the class objects created by the constructor. It has the same name as their class name preceded by a tilde (~) symbol. There are some key points about destructors which are:
→ They neither require any argument nor do they return any value.
→ They release memory space which are occupied by the objects created by the constructor.
→ Destructor cannot be overloaded.
→ Objects are destroyed in the reverse of an object creation.
→ Only one destructor can be defined.

## Code:

a.
~~~
#include <iostream>
using namespace std;

//defining constructor inside the class
class student
{
    int rn;
    char n[50];
    float avg = 0.0;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<"%"<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}
~~~

b.
~~~
#include <iostream>
using namespace std;

//defining the constructor outside the class
class student
{
    int rn;
    char n[50];
    float avg;
    public:
    student();
    void display();
};
student::student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the average: ";
    cin>>avg;
}
void student::display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<endl;
}
int main()
{
    student s1;
    s1.display();
}
~~~

c.
~~~
#include <iostream>
using namespace std;

//types of constructor - default constructor
class student
{
    int rn;
    char n[50];
    double m1, m2, m3;
    public:
    student()
{
    cout<<"Enter the name: ";
    cin>>n;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the subject 1 marks: ";
    cin>>m1;
    cout<<"Enter the subject 2 marks: ";
    cin>>m2;
    cout<<"Enter the subject 3 marks: ";
    cin>>m3;
}

void display()
{
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Marks for subject 1: "<<m1<<endl;
    cout<<"Marks for subject 2: "<<m2<<endl;
    cout<<"Marks for subject 3: "<<m3<<endl;
}
};
int main()
{
    student s1;
    s1.display();
}

~~~
d.
~~~
#include <iostream>
using namespace std;

//types of constructor - parameterized constructor
class maxop
{
    public:
    maxop(int a, int b)
{
    cout<<"First Number: "<<a<<endl;
    cout<<"Second Number: "<<b<<endl;
    cout<<endl;
    if (a>b)
    {
        cout<<"The first number is greater than the second.";
    }
    else if (b>a)
    {
        cout<<"The second number is greater than the first. ";
    }
    else
    {
        cout<<"Both numbers are equal. ";
    }
}
};

int main()
{
    maxop n1(23,76);
}
~~~

e.
~~~
#include<iostream>
#include<string.h>
using namespace std;

//types of constructors - copy constructor
class student
{
    int rn;
    char n[50];
    float avg = 0;
    public:
    student(int,char[],float);

    student(student &t)
    {
        rn=t.rn;
        strcpy(n,t.n);
        avg=t.avg;
    }
    void display();

};

 student::student(int rno,char na[],float av)
 {
    rn=rno;
    strcpy(n,na);
    avg=av;
 }

void student::display()
 {
    cout<<endl;
    cout<<"Name: "<<n<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Average: "<<avg<<" %"<<endl;
 }

int main()
{
    student s1(36,"Lewis",93.7);
    s1.display();

    student lewis(s1);
    lewis.display();

    return 0;
}
~~~
    

f.
~~~
# include<iostream>
using namespace std;
int c = 0;
//using a destructor
class destruct
{
    public:
    destruct()
    {
        c++;
        cout<<"Number of objects created: "<<c<<endl;
    }
    ~destruct()
    {
        c--;
        cout<<"Number of objects destroyed: "<<c<<endl;
    }
};

int main()
{
    destruct aa,bb,cc,dd;
}

~~~
## Output





