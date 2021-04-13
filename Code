#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<conio.h>
struct name {
	char  name[20], un[20], pass[20], ei[50];
	 long int  phno;
	struct name* next;
};
typedef struct name* NAME;
NAME first=NULL;
char run;
struct stack {
	char pn[10];
	float price;
	struct stack* next;
};
typedef struct stack* STOCK;
STOCK top = NULL;
void login();
void registenr();
void productsearch();
void aboutus();
void help();
void push(char a[], float n);
void payment(char a[], float n);
void ordersum();
void userpage();
struct card {
	char name[10], BN[10];
	long int cardno;
	int cvv;
}s;
void main()
{
	int ch;
	while (1)
	{
		printf("\n_______________________HOME_________________________\n");
		printf("Enter your choice.\n");
		printf("1.Login\n2.Register\n3.About us\n4.Help\n5.Exit\n");
		scanf("%d", &ch);
		switch (ch)
		{
		case 1:
			login();
			break;
		case 2:
			registenr();
			break;
		case 3:
			aboutus();
			break;
		case 4:
			help();
			break;
		case 5:
			exit(1);
		default:
			printf("Invalid Choice\n");
			break;
		}
	}
}
void push(char a[], float n)
{
	STOCK temp;
	temp = (STOCK)malloc(sizeof(struct stack));
	if (temp == NULL)
	{
		printf("Cart is Full\n");
		return;
	}
	else
	{
		strcpy(temp->pn, a);
		temp->price = n;
		temp->next = NULL;
		if (top == NULL)
			top = temp;
		else {
			STOCK t;
			t = top;
			while (t->next != NULL)
				t = t->next;
			t->next = temp;
		}
		printf("Successfully added to cart\n");
	}
}
void login()
{
    int k,l;
	NAME temp=first;
	char un[20], pass[20];
	printf("\nEnter your details\n");
	printf("Username : ");
	scanf("%s", un);
	printf("Password : ");
	scanf("%s", pass);
	while (temp != NULL)
	{
	    k=strcmp(temp->un, un);
        l=strcmp(temp->pass, pass);
		if (k==0&&l==0)
		{
			printf("Welcome!\n");
			printf("%s\n", temp->name);
			userpage();
			return;
		}
		temp = temp->next;
	}
	printf("Incorrect username or password\n");
}
void payment(char a[],float n)
{
	int k;
	char add[100];
	printf("...WELCOME...\n");
	printf("Select a payment method\n");
	printf("1.Credit card\n2.Cash on delivery\n");
	scanf("%d", &k);
	switch (k)
	{
	case 1:
		printf("Enter card details\n1.Name on card\n2.Card no.\n3.CVV\n4.Bank Name\n");
		scanf("%s%d%ld%s", s.name, &s.cardno, &s.cvv, s.BN);
		printf("Enter delivery address: ");
		scanf("%s", add);
		ordersum();
		break;
	case 2: 
		printf("Enter delivery address:");
		scanf("%s", add);
		ordersum();
		break;
	default:
		printf("Invalid choice\n");
	}
}
void registenr() {
	long int phno;
	char name[10], un[20], pass[10], ei[50];
	NAME temp;
	temp = (NAME)malloc(sizeof(struct name));
	printf("\nEnter your details\n1.Name\n2.UserName\n3.MobileNo.\n4.Password\n5.e-mail ID\n");
	scanf("%s%s%ld%s%s", name, un, &phno, pass, ei);
	strcpy(temp->name, name);
	strcpy(temp->un, un);
	strcpy(temp->ei, ei);
	strcpy(temp->pass, pass);
	temp->phno = phno;
	temp->next = NULL;
	if (first == NULL)
		first = temp;
	else
	{
		temp->next = first;
		first = temp;
	}
	printf("Successfully Registered\n");
}
void userpage()
{
s8:
	printf("\n1.Display Cart\n2.Make Payment\n3.Look for products\n4.Logout\n");
	int x;
	scanf("%d", &x);
	switch (x)
	{
	case 1:
		if (top == NULL)
		{
			printf("Cart is empty\n");
			goto s8;
		}
		printf("\n________CART________\n");
		printf("Product\tPrice\n");
		STOCK i;
		for (i = top; i != NULL; i = i->next)
		{
			printf("%s\t%f\n", i->pn, i->price);
		}
		userpage();
		break;
	case 2:
		if (top == NULL)
		{
			printf("Cart is empty\n");
			goto s8;
		}
		payment("abc",50.00);
		break;
	case 3:
		productsearch();
		break;
	case 4:
		printf("Logged out successfully\n");
		break;
	default:
		printf("Invalid choice\n");
	}
}
void productsearch()
{
	int c;
	char u, v;
s7:
	printf("Choose among the following\n");
	printf("Name\tPrice\n");
	printf("1.abc\tRs.50.00\n2.def\tRs.50.00\n3.ghi\tRs.50.00\n\t\t4.Go Back\n");
	scanf("%d", &c);
	switch (c)
	{
	case 1:
		printf("\n.............abc..............\n");
		printf("Previous price\tRs.80.00\nDiscount\tRs.30.00\nCurrent Price\tRs.50.00\n");
		printf("Add to cart? {y/n}\n");
	s1:
		scanf("%s", &v);
		//_getch();
		if (v == 'y' || v == 'Y')
		{
			push("abc", 50.00);
			printf("Proceed to payment? (y/n}\n");
		s2:
			scanf("%s", &u);
			if (u == 'y' || u == 'Y')
				payment("abc", 50.00);
			else if (u == 'n' || u == 'N')
				productsearch();
			else
			{
				printf("Enter y or n only\n");
				goto s2;
			}
		}
		else if (v == 'n' || v == 'N')
			productsearch();
		else
		{
			printf("Enter y or n only\n");
			goto s1;
		}
		break;
	case 2:
		printf("\n.............def..............\n");
		printf("Previous price\tRs.80.00\nDiscount\tRs.30.00\nCurrent Price\tRs.50.00\n");
		printf("Add to cart? {y/n}\n");
	s3:
		scanf("%s", &v);
		if (v == 'y' || v == 'Y')
		{
			push("def", 50.00);
			printf("Proceed to payment? (y/n}\n");
		s4:
			scanf("%s", &u);
			if (u == 'y' || u == 'Y')
				payment("def", 50.00);
			else if (u == 'n' || u == 'N')
				productsearch();
			else
			{
				printf("Enter y or n only\n");
				goto s4;
			}
		}
		else if (v == 'n' || v == 'N')
			productsearch();
		else
		{
			printf("Enter y or n only\n");
			goto s3;
		}
		break;
	case 3:
		printf("\n.............ghi..............\n");
		printf("Previous price\tRs.80.00\nDiscount\tRs.30.00\nCurrent Price\tRs.50.00\n");
		printf("Add to cart? {y/n}\n");
	s5:
		scanf("%s", &v);
		//_getch();
		if (v == 'y' || v == 'Y')
		{
			push("ghi", 50.00);
			printf("Proceed to payment? (y/n}\n");
		s6:
			scanf("%s", &u);
			if (u == 'y' || u == 'Y')
				payment("ghi", 50.00);
			else if (u == 'n' || u == 'N')
				productsearch();
			else
			{
				printf("Enter y or n only\n");
				goto s6;
			}
		}
		else if (v == 'n' || v == 'N')
			productsearch();
		else
		{
			printf("Enter y or n only\n");
			goto s5;
		}
		break;
	case 4:
		userpage();
		break;
	default:
		printf("Invalid choice\n");
		goto s7;
	}
}
void ordersum()
{
	STOCK i;
	float n=0,res;
	printf("Items purchased are : \n");
	for (i = top; i != NULL; i = i->next)
	{
		printf("%s\t%f\n", i->pn, i->price);
		n += i->price;
	}
	printf("Delivery cost = Rs. 50\n");
	res = 50 + n;
	printf("Total = %f \n", res);
	printf("Confirm? {y/n}\n");
	scanf("%s", &run);
	if (run == 'y'||run=='Y')
	{
		printf("Transaction successfull\n");
		printf("Thankyou.\n");
		userpage();
	}
	else
	{
		printf("Order cancelled\n");
		userpage();
	}
}
void aboutus()
{
	char c;
	FILE* in;
	in = fopen("about.txt", "r");
	c = fgetc(in);
	while (c != EOF)
	{
		printf("%c", c);
		c = fgetc(in);
	}
	fclose(in);
}
void help()
{
	char c;
	FILE* in;
	in = fopen("help.txt", "r");
	c = fgetc(in);
	while (c != EOF)
	{
		printf("%c", c);
		c = fgetc(in);
	}
	fclose(in);
}
