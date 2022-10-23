#include<iostream>
using namespace std;

class Distance 
{
    int feet;
    int inches;
    public:
    void get()
    {
        cout<<"Enter feet and inches:";
        cin>>feet>>inches;
    }
    void show()
    {
        cout<<feet<<","<<inches<<endl;
    }
    Distance add(const Distance &);
};

Distance Distance::add(const Distance &Q)
{
    Distance Temp;
    Temp.feet=feet+Q.feet;
    Temp.inches=inches+Q.inches;
    if(Temp.inches>=12)
    {
        Temp.feet=feet+inches/12;
        Temp.inches=inches%12;
    }
    return Temp;
}

int main()
{
    Distance D1, D2, D3;
    D1.get();
    D2.get();
    D3=D1.add(D2);
    D1.show();
    D2.show();
    D3.show();
    return 0;
}

