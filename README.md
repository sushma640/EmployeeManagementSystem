# EmployeeManagementSystem
#include<iostream>
#include<windows.h>
#include<conio.h>
using namespace std;


struct emp{
    string name, id, address;
    long long int contact,salary;
};
emp e[100];
int total=0;
void empdata(){
    int choice;
    cout<<"How many employees data do you want to enter ?"<<endl;
    cin>>choice;
    cout<<endl;
    int i=total;
    while(i<total+choice){
        cout<<"\nEnter data of employee "<<i+1<<endl;
        cout<<"Employee Name: ";
        cin>>e[i].name;
        cout<<"ID: ";
        cin>>e[i].id;
        cout<<"Address: ";
        cin>>e[i].address;
        cout<<"Salary: ";
        cin>>e[i].salary;
        cout<<"Contact: ";
        cin>>e[i].contact;

        i+=1;
    }
    /*for(int i=total;i<total+choice;i++){
        cout<<"\nEnter data of employee "<<i+1<<endl;
        cout<<"Employee Name: ";
        cin>>e[i].name;
        cout<<"ID: ";
        cin>>e[i].id;
        cout<<"Address: ";
        cin>>e[i].address;
        cout<<"Salary: ";
        cin>>e[i].salary;
        cout<<"Contact: ";
        cin>>e[i].contact;

    }*/
    total=total+choice;


}
void show(){
    if(total!=0){
        for(int i=0;i<total;i++){
            cout<<"\nData of Employee "<<i+1<<endl;
            cout<<"Employee Name: "<<e[i].name<<endl;
            cout<<"ID: "<<e[i].id<<endl;
            cout<<"Address: "<<e[i].address<<endl;
            cout<<"Salary: "<<e[i].salary<<endl;
            cout<<"Contact: "<<e[i].contact<<endl;

        }
    }else{
        cout<<"\nYour record is Empty.";
    }

}
void search(){
    if(total!=0){
        string key;
        cout<<"Enter id of data which you want to search ";
        cin>>key;
        for(int i=0;i<total;i++){
            if(key==e[i].id){
                cout<<"\nData of Employee "<<i+1<<endl;
                cout<<"Employee Name: "<<e[i].name<<endl;
                cout<<"ID: "<<e[i].id<<endl;
                cout<<"Address: "<<e[i].address<<endl;
                cout<<"Salary: "<<e[i].salary<<endl;
                cout<<"Contact: "<<e[i].contact<<endl;
                break;
            }
            if(i==total-1){
                cout<<"\nNo such record found."<<endl;
            }
        }
    }else{
        cout<<"\nYour record is Empty.";
    }

}
void update(){
    if(total!=0){
        string key;
        cout<<"\nEnter id of data which you want to search ";
        cin>>key;
        for(int i=0;i<total;i++){
            if(key==e[i].id){
                cout<<"\nPrevious Data"<<endl;
                cout<<"\nData of Employee "<<i+1<<endl;
                cout<<"Employee Name: "<<e[i].name<<endl;
                cout<<"ID: "<<e[i].id<<endl;
                cout<<"Address: "<<e[i].address<<endl;
                cout<<"Salary: "<<e[i].salary<<endl;
                cout<<"Contact: "<<e[i].contact<<endl;
                cout<<"Employee Name: ";
                cin>>e[1].name;
                cout<<"ID: ";
                cin>>e[i].id;
                cout<<"Address: ";
                cin>>e[i].address;
                cout<<"Salary: ";
                cin>>e[i].salary;
                cout<<"Contact: ";
                cin>>e[i].contact;
                break;
            }
            if(i==total-1){
                cout<<"\nNo such record found."<<endl;
            }
        }
    }else{
        cout<<"\nYour record is Empty.";
    }
    
}
void del(){
    if(total!=0){
        char user;
        cout<<"\nPress 1 to delete full record."<<endl;
        cout<<"\tPress 2 to delete specific record."<<endl;
        user=getch();
        if(user=='1'){
            total=0;
            cout<<"\n\t\t\tAll record id deleted....!"<<endl;

        }else if(user=='2'){
            string key;
            cout<<"Enter id of data which you want to delete ";
            cin>>key;
            for(int i=0;i<total;i++){
                if(key==e[i].id){
                    for(int j=i;j<total;j++){
                        e[j].name=e[j+1].name;
                        e[j].id=e[j+1].id;
                        e[j].address=e[j+1].address;
                        e[j].contact=e[j+1].contact;
                        e[j].salary=e[j+1].salary;
                        total--;
                        cout<<"\n\t\t\tYour required record is deleted.";
                        break;
                    }
                    if(i==total-1){
                        cout<<"\nNo such record found"<<endl;
                    }
                }
            }
        }
    }else{
        cout<<"\nYour record is empty."<<endl;
    }

}


int main(){
    cout<<"\n\n\t\t\tEmployee Management System"<<endl;
    cout<<"\n\n\t\t\tSign Up"<<endl;
    string username,password;
    cout<<"\n\t\t\tEnter Username: ";
    cin>>username;
    cout<<"\n\t\t\tEnter Password: ";
    cin>>password;
    cout<<"\n\t\t\tYour id is creating please wait";
    for(int i=0;i<4;i++){
        cout<<".";
        Sleep(1000);
    }
    cout<<"\n\t\t\tYour id is created succesfully"<<endl;
    Sleep(2000);
    system("CLS");
    start:
    system("CLS");
    cout<<"\n\n\t\\ttEmployee Management System"<<endl;
    cout<<"\n\n\t\t\tLogin"<<endl;
    string username1,password1;
    cout<<"\t\t\tEnter Username: ";
    cin>>username1;
    cout<<"\t\t\tEnter Password: ";
    cin>>password1;
    if(username1==username && password1==password){
        system("CLS");
        char user;
        while(1){
            cout<<"\n\n\t\t\tPress 1 to enter data."<<endl;
            cout<<"\t\t\tPress 2 to show data."<<endl;
            cout<<"\t\t\tPress3 to search data."<<endl;
            cout<<"\t\t\tPress 4 to update data."<<endl;
            cout<<"\t\t\tPress 5 to delete data."<<endl;
            cout<<"\t\t\tPress 6 to logout."<<endl;
            cout<<"\t\t\tPress 7 to exit."<<endl;
            user=getch();
            system("CLS");
            switch(user){
                case '1':
                    empdata() ;
                    break;
                case '2':
                    show();
                    break;
                case '3':
                    search();
                    break;
                case '4':
                    update();
                    break;
                case '5':
                    del();
                    break;
                case '6':
                    goto start;
                    break;
                default:
                    cout<<"\aInvalid Input.";
                    break;
                    
                

            }
        }
    }
    else if(username1!=username){
        cout<<"\t\t\tUsername is Incorrect."<<endl;
    }
    else{
        cout<<"\t\t\tPassword is Incorrect."<<endl;
    }
    

    return 0;
}
