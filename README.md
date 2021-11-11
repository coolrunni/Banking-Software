# Banking-Software
ATM software, create account, debit, credit, withdrawal, verifications.
# include <iostream.h>
# include <conio.h>
# include <stdio.h>
# include <string.h>
# include <fstream.h>
# include <process.h>
# include <iomanip.h>
# include <stdlib.h>
# include <dos.h>
void border()				//BORDER ON THE FIRST PAGE
{
int i,j,k,l;
for(i=1;i<=79;i++) //top
	{
	gotoxy(i,2);
	cout<<char(178);
	delay(10);
	}
for(j=2;j<=22;j++) //left
	{
	 gotoxy(1,j);
	 cout<<char(178);
	 delay(10);
	}
for(k=1;k<=79;k++) //bottom
	{
	gotoxy(k,23);
	cout<<char(178);
	delay(10);
	}
for(l=22;l>=2;l--)
	{
	gotoxy(79,l);
	cout<<char(178);
	delay(10);
	}
}
void presentation()                     //INTRODUCTORY PAGE OF THE BANK
{
cout<<endl<<endl<<endl<<endl<<endl;
cout<<setw(55)<<"WELCOME TO ESTEEM BANK"<<endl;
cout<<setw(57)<<"--------------------------"<<endl;
cout<<endl<<endl;
cout<<setw(57)<<"WE GIVE THE BEST PERFORMANCE"<<endl;
cout<<setw(55)<<"THANK YOU FOR CHOOSING US"<<endl;cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
}
class bank                              //USING OF OOP
	{
	double balance,amount,interest;
	char name[50],fname[50],mname[50],address[60],gender,type[10],phnumber[12];
	int age,pincode;
	long bnumber,adhnumber,accnumber,numb,duration;
	public:
	void create()                   //INITIALISATION OF DETAILS OF THE CUSTOMER
		{interest=0;
		int a,u,t=0;char q,d,e;
		cout<<setw(40)<<"CREATION OF ACCOUNT IN ESTEEM BANK"<<endl<<endl;
		cout<<setw(40)<<"------------------------------------------------"<<endl<<endl;
		cout<<"ACCOUNT HOLDER'S NAME : ";gets(name);cout<<endl;
		cout<<"ACCOUNT HOLDER'S AGE : ";cin>>a;cout<<endl;
		if(a>18)
		{
		randomize();
		numb=rand()%100000000000;
			age=a;
		cout<<"ACCOUNT HOLDER'S GENDER(F/M/T) : ";cin>>gender;cout<<endl;
		cout<<"ACCOUNT HOLDER'S FATHER : ";gets(fname);cout<<endl;
		cout<<"ACCOUNT HOLDER'S MOTHER : ";gets(mname);cout<<endl;
		cout<<"ACCOUNT HOLDER'S ADDRESS : ";gets(address);cout<<endl;
		cout<<"ACCOUNT HOLDER'S MOBILE NUMBER : ";gets(phnumber);cout<<endl;
		cout<<"ACCOUNT HOLDER'S AADHAAR NUMBER : ";cin>>adhnumber;cout<<endl;
		cout<<"BRANCH NUMBER : ";cin>>bnumber;cout<<endl;
		cout<<"GENERATE 4 DIGIT PIN : ";cin>>pincode;cout<<endl;
		sound(500);
		delay(50);
		nosound();
		cout<<"SELECT THE TYPE ACCOUNT (FIXED,SAVINGS) : ";gets(type);cout<<endl;
		if(strcmp(type,"fixed")==0 || strcmp(type,"FIXED")==0)
		{
		cout<<"ENTER THE INITIAL AMOUNT TO BE DEPOSITED(>=1000) : ";cin>>balance;
		if(balance<1000)
			{
			cout<<endl<<"ACCOUNT CREATION UNSUCCESSFUL "<<endl;
			cout<<"ENTER ANY KEY TO EXIT"<<endl;
			cin>>e;
			exit(0);
			}
		if(balance>=1000)
			{
			cout<<"ENTER DURATION (MONTHS)"<<endl;
			cin>>duration;
			}
		}
		if(strcmp(type,"savings")==0 || strcmp(type,"SAVINGS")==0)
		{
		cout<<"ENTER THE INITIAL AMOUNT TO BE DEPOSITED(>=100) : ";cin>>balance;
		if(balance<100)
			{
			cout<<endl<<"ACCOUNT CREATION UNSUCCESSFUL "<<endl;
			cout<<"ENTER ANY KEY TO EXIT"<<endl;
			cin>>e;
			exit(0);
			}
		}
			cout<<endl<<setw(70)<<"CONGRATULATION! YOUR ACCOUNT HAS BEEN CREATED  :-)"<<endl;
			cout<<setw(60)<<"ENJOY OUR BEST FACILITIES......"<<endl;
			cout<<endl<<"ENTER ANY KEY TO PROCEED"<<endl;
			cin>>d;
			}
			if(a<18)
			{
			cout<<"YOU ARE BELOW 18 YEARS OLD"<<endl;
			cout<<"THUS, INELIGIBLE FOR A/c CREATION "<<endl;
			cout<<"ENTER '1' TO EXIT OR ANY OTHER KEY TO CONTINUE "<<endl;
			cin>>q;
			if(q=='1')
			exit(t);
			if(q!=1)
			create();
			}
		}
	void initial()			//OPTION TO SELECT DEBIT OR CREDIT
		{
		 int c;
		 cout<<endl<<endl<<endl<<setw(50)<<"ENTER THE FOLLOWING CHOICE :"<<endl;
		 cout<<setw(51)<<"::::::::::::::::::::::::::::::"<<endl<<endl;
		 cout<<setw(52)<<"'1' FOR DEBIT or '2' FOR CREDIT "<<endl;
		 cin>>c;
		 cout<<endl<<endl<<endl<<endl<<endl;
		 switch(c)
		 {
		 case 1:
		 debit();
		 break;
		 case 2:
		 credit();
		 break;
		 default:
		 cout<<"Wrong choice"<<endl;
		 }
		}
	void debit()                    //DEBIT SECTION
		{
		if(strcmp(type,"fixed")==0 || strcmp(type,"FIXED")==0)
			{
			int p;
			cout<<"ENTER THE PIN"<<endl;
			cin>>p;
			if(pincode==p)
			{
			sound(500);
			delay(50);
			nosound();
			int time,u;char z;
			cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
			cout<<setw(55)<<"ENTER THE FOLLOWING CHOICE"<<endl;
			cout<<setw(58)<<"::::::::::::::::::::::::::::::::"<<endl<<endl;
			cout<<"1.INTEREST CALCULATION"<<endl<<"2.WITHDRAWL"<<endl<<"OR  PRESS ANY OTHER NUMBER"<<endl;
			cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
			cin>>u;
			switch(u)
				{
				case 1:
				cout<<"FOR HOW LONG DID YOU KEEP THE AMOUNT [MONTHS] ?"<<endl;
				cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
				cin>>time;
				interest=(balance*0.08*time)/12;
				cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
				cout<<"YOUR PRESENT GETABLE INTEREST : "<<interest<<endl;
				cout<<"PRESS ANY KEY"<<endl;
				cin>>z;
				break;
				case 2:
				cout<<"FOR HOW LONG DID YOU KEEP THE AMOUNT [MONTHS] ?"<<endl;
				cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
				cin>>time;
				if(time<=duration)
					{
					cout<<duration;
					amount=balance+((balance*0.08*time)/12);
					balance=0;
					cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
					cout<<"AMOUNT WITHDRAWN : "<<amount<<endl;
					cout<<endl<<setw(55)<<"SUCCESSFULLY WITHDRAWN"<<endl<<endl;
					cout<<"PRESS ANY KEY"<<endl;
					cin>>z;
					}
				break;
				default:
				cout<<"WRONG CHOICE"<<endl;
				}
			}
			else
			{
			char v;
			sound(100);
			delay(50);
			nosound();
			cout<<"WRONG PIN"<<endl<<"TRY AGAIN"<<endl<<endl<<endl;
			cout<<setw(50)<<"PRESS ANY KEY"<<endl;
			cin>>v;
			}
			}
		if(strcmp(type,"savings")==0 || strcmp(type,"SAVINGS")==0)
		{
		double purchased,withdrawl,tmoney,anumber;int p,ab,e;
		cout<<"WELCOME TO THE DEBIT SECTION"<<endl;
		cout<<"CHOOSE ANY OF THE FOLLOWING "<<endl<<endl;
		cout<<"1.PURCHASING "<<endl<<"2.WITHDRAWL "<<endl<<"3.MONEY SENDING "<<endl;
		cin>>ab;
		switch(ab)
		{
			case 1:		//FOR PURCHASING
			cout<<"ENTER PIN : ";cin>>p;
			if(pincode==p)
				{
				sound(500);
				delay(40);
				nosound();
				cout<<"ENTER THE PURCHASING AMOUNT : ";cin>>purchased;
				cout<<"ARE YOU SURE?"<<endl<<"TO PROCEED PRESS 1"<<endl;
				cin>>e;
				if(e==1)
				balance-=purchased;
				cout<<endl<<endl<<endl<<endl<<endl<<endl;
				}
			 if(pincode!=p)
				{
				sound(100);
				delay(50);
				nosound();
				}
			break;
			case 2:           //FOR CASH WUTHDRAWL
			cout<<"ENTER PIN : ";cin>>p;
			if(pincode==p)
			{
					sound(500);
					delay(50);
					nosound();
					cout<<"ENTER THE AMOUNT TO BE WITHDRAWL : ";cin>>withdrawl;
					cout<<"ARE YOU SURE?"<<endl<<"TO PROCEED PRESS 1"<<endl;
					cin>>e;
					if(e==1)
					balance-=withdrawl;
					cout<<endl<<endl<<endl<<endl<<endl;
					}
				if(pincode!=p)
					{
					sound(100);
					delay(50);
					nosound();
					}
				break;
			case 3:			//FOR MONEY SENDING
			cout<<"ENTER PIN : ";cin>>p;
			if(pincode==p)
			{
					sound(500);
					delay(50);
					nosound();
					cout<<"ENTER THE ACCOUNT NUMBER OF RECEIVER : ";cin>>anumber;
					cout<<"ENTER THE AMOUNT TO BE SENT : ";cin>>tmoney;
					cout<<"ARE YOU SURE?"<<endl<<"TO PROCEED PRESS 1"<<endl;
					cin>>e;
					if(e==1)
					balance-=tmoney;
					cout<<endl<<endl<<endl<<endl;
					}
				if(pincode!=p)
					{
					sound(100);
					delay(50);
					nosound();
					}
			break;
			default:
			cout<<"Wrong Choice"<<endl;
		}
		}
	}
	void credit()			//CREDIT SECTION
		{
		if(strcmp(type,"savings")==0 || strcmp(type,"SAVINGS")==0)
		{
		int as,p;
		long deposit,ano;
		double amoney,days;
		cout<<"WELCOME TO THE CREDIT SECTION"<<endl;
		cout<<"CHOOSE ANY OF THE FOLLOWING "<<endl<<endl;
		cout<<"1.DEPOSIT "<<endl<<"2.MONEY RECEIVING "<<endl<<"3.INTEREST RECEIVED "<<endl;
		cin>>as;
		switch(as)
		{
		case 1:			//FOR DEPOSIT
		cout<<"ENTER PIN : ";cin>>p;
		if(pincode==p)
		{
				sound(500);
				delay(50);
				nosound();
				cout<<"ENTER THE AMOUNT TO BE DEPOSITED : ";cin>>deposit;
				balance+=deposit;
				cout<<endl<<endl<<endl<<endl<<endl;
				}
			if(pincode!=p)
				{
				sound(100);
				delay(50);
				nosound();
				}
			break;
		case 2:			//FOR MONEY RECEIVING
		cout<<"ENTER PIN : ";cin>>p;
		if(pincode==p)
		{
				sound(500);
				delay(50);
				nosound();
				cout<<"ENTER THE ACCOUNT NUMBER OF SENDER : ";cin>>ano;
				cout<<"ENTER THE AMOUNT WHISH IS BEING RECEIVED : ";cin>>amoney;
				balance+=amoney;
				cout<<endl<<endl<<endl<<endl<<endl;
				}
				if(pincode!=p)
				{
				sound(100);
				delay(50);
				nosound();
				}
			break;
		case 3:			//FOR INTEREST RECEIVING
		cout<<"ENTER PIN : ";cin>>p;
		if(pincode==p)
		{
				sound(500);
				delay(50);
				nosound();
				cout<<"FIXED DEPOSIT HAS A INTEREST OF 8% PER ANNUM AND SAVINGS HAS A INTEREST OF 4%"<<endl;
				cout<<"ENTER THE NO OF DAYS YOU HAVE KEPT THIS MONEY IN BANK : ";cin>>days;
				if(strcmp(type,"savings")==0 || strcmp(type,"SAVINGS")==0)
				balance=balance+(balance*0.04*(days/365));
				cout<<endl<<endl<<endl<<endl<<endl;
				}
			if(pincode!=p)
				{
				sound(100);
				delay(50);
				nosound();
				}
			break;
			default:
			cout<<"Wrong Choice"<<endl;
		}
		}
	}
	void details()			//DETAILS OF THE CUSTOMER'S A/c
	{
	cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
	int p;
	cout<<"ENTER PIN : ";cin>>p;
	cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
	if(pincode==p)
		{
		sound(500);
		delay(50);
		nosound();
		cout<<setw(45)<<"DETAILS OF THE ACCOUNT HOLDER"<<endl;
		cout<<setw(50)<<"::::::::::::::::::::::::::::::::::::::::"<<endl<<endl;
		cout<<"ACCOUNT HOLDER'S NAME : "<<name<<endl;
		cout<<"REGISTERED MOBILE NUMBER : "<<phnumber<<endl;
		cout<<"ACCOUNT NUMBER : "<<numb<<endl;
		cout<<"TYPE OF THE ACCOUNT : "<<type<<endl;
		cout<<"NET BALANCE : "<<balance<<endl<<endl;
		cout<<setw(40)<<"THANK YOU FOR CHECKING WITH US"<<endl;
		cout<<setw(40)<<"SEE YOU SOON "<<endl;
		cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
		int w=0;char z;
		cout<<"ENTER '1' FOR EXIT OR ANY OTHER KEY FOR CONTINUATION"<<endl<<endl<<endl<<endl;
		cin>>z;
		if(z=='1')
		exit(w);
		cout<<endl<<endl<<endl<<endl;
		}
	if(pincode!=p)
		{
		char b;
		sound(100);
		delay(50);
		nosound();
		cout<<"INCORRECT PIN"<<endl;
		cout<<"ENTER 1 TO EXIT OR ANY OTHER KEY TO RETRY"<<endl;
		cin>>b;
		if(b=='1')
		exit(0);
		if(b!=1)
		details();
		}
	}
};
void main()
	{
	int ch,s=0,t;
	clrscr();
	border();                    //CALLING OF BORDER FUNC.
	presentation();              //CALLING OF THE FUNC. TO SHOW INTRODUCTORY PAGE
	cout<<setw(55)<<"TO CONTINUE PRESS 1 : ";cin>>t;
	if(t==1)
	{
	cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
	bank ob;
	ofstream h;
	h.open("ESTEEM.txt",ios::app);
	while(1)
	{
	cout<<setw(45)<<"ENTER THE FOLLOWING CHOICE"<<endl;
	cout<<setw(50)<<":::::::::::::::::::::::::::::::::::"<<endl<<endl;
	cout<<"1.CREATION OF AN ACCOUNT"<<endl<<"2.DEBIT OR CREDIT"<<endl<<"3.DETAILS OF THE ACCOUNT HOLDER"<<endl<<"4.EXIT"<<endl;
	cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
	cin>>ch;
	cout<<endl<<endl;
		switch(ch)
			{
			case 1:
			ob.create();                 //CALLING OF FUNC. TO CREATE A/c
			h.write((char *)&ob,sizeof(ob));
			h.close();
			break;
			case 2:
			ob.initial();               //CALLING OF FUNC. TO SELECT DEBIT OR CREDIT
			h.write((char *)&ob,sizeof(ob));
			h.close();
			break;
			case 3:
			ob.details();               //CALLIN OF FUNC. TO VIEW DETAILS
			h.write((char *)&ob,sizeof(ob));
			h.close();
			break;
			case 4:
			exit(s);                    //FOR EXIT
			default:
			cout<<"Wrong Choice"<<endl;
			}
			}
		}
		getch();
	}
