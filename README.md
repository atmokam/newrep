# newrep
testrep
//1
#include <iostream>
using namespace std;

class A{
    double a[10]; int n;
public:
    A(double *a1, int n1){
        do{cin>>n1;}while(n1<2||n1>10);
        n = n1;
        for(int i = 0; i < n; ++i)
            cin>>a1[i];
        for(int i = 0; i < n; ++i)
            a[i] = a1[i];
    }
    ~A(){};
    
    friend double mijin(A& ob);
    
    
};

double mijin(A& ob){
    double mijin = 0;
    for(int i=0; i<ob.n; ++i){
        mijin+=ob.a[i];
    }
    mijin/=ob.n;
    return mijin;
}

int main(){
    int y; double x[10];
    A obj(x, y);
    cout<<mijin(obj);
    
}
//2
#include <iostream>
using namespace std;

class A {
    int a[10][10]; int n;
public:
    A() {

        do { cin >> n; } while (n < 2 || n > 10);
      
        for (int i = 0; i < n; ++i)
            for (int j = 0; j < n; ++j)
                cin >> a[i][j];
       
    }

    ~A() {}

    int bacas() {
        int s = 1;
        for (int i = 0; i < n; ++i)
            for (int j = 0; j < n; ++j)
                if (a[i][j] < 0)
                    s *= a[i][j];
        return s;
    }

    friend class F;


};

class F {
public:
    int zuyg(A& ob) {
        int s = 0;
        for (int i = 0; i < ob.n; ++i)
            for (int j = 0; j < ob.n; ++j)
                if (ob.a[i][j] % 2 == 0 && ob.a[i][j]>0)
                    s += ob.a[i][j];
        return s;
    }
};

int main() {

    A obj;
    F obj1;
    cout << obj1.zuyg(obj) << endl;
    cout << obj.bacas();

}
//3
#include <iostream>
using namespace std;
#include<cstring>
struct us {
    char an[10], az[10]; double qnn; int bac;
};

class A {
    us* p; int n;
public:
    A(us* p1, int n1) {
        n = n1;
        for (int i = 0; i < n; ++i) {
            strcpy(p[i].az, p1[i].az);
            p[i].bac = p1[i].bac;
            strcpy(p[i].an, p1[i].an);
            p[i].qnn = p1[i].qnn;
        }
    }

    ~A() {}

    int mijin() {
        int s = 0;
        for (int i = 0; i < n; ++i)
            s += p[i].qnn;
        s /= n;
        return s;
    }

    friend class F;


};

class F {
public:
    void artac(A& ob) {
        int mijin = ob.mijin();
        for (int i = 0; i < ob.n; ++i)
            if (ob.p[i].qnn < mijin)
                cout << ob.p[i].an << " " << ob.p[i].az << " " << ob.p[i].qnn << " " << ob.p[i].bac << endl;
        
    }
};

int main() {

    
   
    us a[10]; int n;
    do { cin >> n; } while (n < 2 || n > 10);

    for (int i = 0; i < n; ++i)
        cin >> a[i].an>> a[i].az >> a[i].bac >> a[i].qnn;

    A obj(a, n);
    F obj1;
    obj1.artac(obj);
    cout << obj.mijin();

}
