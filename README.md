#include <iostream>
using namespace std;
const int  m=50;
class ITEMS
{
    int itemcode[m];
    float itemPrice[m];
    int count;
    public :
    void CNT(void)
    {
        count=0;
    }
    void getitem(void);
    void displaySum(void);
    void remove(void);
    void displayItems(void);
};
void ITEMS :: getitem(void)
{
    cout<<"How many students do you have?:";
    cin>>itemcode[count];
    cout<<"Enter Student marks:";
    cin>>itemPrice[count];
    count++;
}
void ITEMS::displaySum(void)
{
    float sum=0;
    for(int i=0;i<count;i++)
            sum=sum+itemPrice[i];
            cout<<"\n Total value:"<<sum<<"\n";
}

void ITEMS ::remove(void)
{
    int a;
    cout<<"Enter number of students in class";
    cin>>a;
    for(int i=0;i<count;i++)
        if(itemcode[i]==a)
            itemPrice[i]=0;
}

void ITEMS :: displayItems(void)
{
    cout<<"\n number of students      marks\n";
    for(int i=0;i<count;i++)
    {
        cout<<"\n"<<itemcode[i];
        cout<<"   "<<itemPrice[i];
    }
    cout<<"\n";
}
int main()
{
    ITEMS order;
    order.CNT();
    int x;
    do
    {
        cout<<"\nYou can do the following";
        cout<<"Enter appropriate number\n";
        cout<<"\n 1: Add number of students";
        cout<<"\n 3 Delete a student";
        cout<<"\n 4 Display Marks";
        cout<<"\n 5: Quit";
        cout<<"\n What is your option";
        cin>>x;
        switch (x)
        {
            case 1:order.getitem();
            break;
            case 2: order.displaySum();
            break;
            case 3:order.remove();
            break;
            case 4:order.displayItems();
            break;
            case 5:break;
            default:cout<<"\nError in input: try again\n";
        }
    }
    while(x!=5);
    return 0;
