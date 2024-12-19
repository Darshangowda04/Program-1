[19/12, 9:08 am] Adithya Gowda Atme: program 8
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
void create();
void insert_front();
void insert_rear();
void display();
void delete_front();
void delete_rear();
int count=0;
struct node
{
int ssn;
char name[50],dept[20],desg[20];
float sal;
unsigned long long int phno;
struct node *llink,*rlink;
};
struct node *first=NULL,*last=NULL,*temp;
main()
{
int ch,n,i;
while(1)
{
printf("1.create\n 2.insert_front\n 3.insert_rear\n 4.display\n 5.delete_front\n 6.delete_rear\n
7.exit\n");
printf("enter choice\n");
scanf("%d",&ch);
switch(ch)
{
case 1:printf("enter the number of employee\n");
scanf("%d",&n);
for(i=0;i<n;i++)
insert_rear();
break;
case 2:insert_front();break;
case 3:insert_rear();break;
case 4:display();break;
case 5:delete_front();break;
case 6:delete_rear();break;
case 7:exit(0);
default:printf("invalid choice\n");break;
}
}
}
void create()
{
int ssn;
char name[50],dept[20],desg[20];
float sal;
unsigned long long int phno;
temp=(struct node*)malloc(sizeof(struct node));
temp->llink=temp->rlink=NULL;
printf("enter ssn,name,dept,desg,salaryand phno\n");
scanf("%d%s%s%s%f%llu",&ssn,name,dept,desg,&sal,&phno);
temp->ssn=ssn;
strcpy(temp->name,name);
strcpy(temp->dept,dept);
strcpy(temp->desg,desg);
temp->sal=sal;
temp->phno=phno;
count++;
}
void insert_front()
{
if(first==NULL)
{
}
else
{
create();
first=temp;
last=temp;
create();
temp->rlink=first;
first->llink=temp;
first=temp;
}
}
void insert_rear()
{
if(first==NULL)
{
create();
first=temp;
else
{
last=temp;
}
create();
last->rlink=temp;
temp->llink=last;
temp->rlink=NULL;
}
last=temp;
}
void display()
{
struct node *p;
if(first==NULL)
{
printf("list is empty\n");
return;
}
p=first;
printf("contents of list\n");
while(p!=NULL)
{
printf("%d\t%s\t%s\t%s\t%f\t%llu\n",p->ssn,p->name,p->dept,p->desg,p->sal,p->phno);
p=p->rlink;
}
printf("total no. of employee %d\n",count);
}
void delete_front()
{
struct node *p;
if(first==NULL)
{
printf("list is empty,cannot delete\n");
}
else if(first->rlink==NULL)
{
printf("deleted
>sal,first->phno);
data is %d\t%s\t%s\t%s\t%f\t%llu\n",first->ssn,first->name,first->dept,first->desg,first-
first=NULL;
free(first);
count--;
}
else
{
p=first;
first=p->rlink;
printf("deleted
>phno);
data is %d\t%s\t%s\t%s\t%f\t%llu\n",p->ssn,p->name,p->dept,p->desg,p->sal,p-
free(p);
count--;
}
}
void delete_rear()
{
struct node*p;
if(first==NULL)
{
printf("list is empty,cannot delete\n");
}
else if(first->rlink==NULL)
{
printf("deleted data is %d\t%s\t%s\t%s\t%f\t%llu\n",first->ssn,first->name,first-
>dept,first->desg,first->sal,first->phno);
first=NULL;
free(first);
count--;
}
else
{
p=last;
last=p->llink;
printf("deleted data is %d\t%s\t%s\t%s\t%f\t%llu\n",p->ssn,p->name,p->dept,p->desg,p-
>sal,p->phno);
free(p);
last->rlink=NULL;
count--;
}
}
prog 7
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
void create();
void insert_front();
void insert_rear();
void display();
void delete_front();
void delete_rear();
int count=0;
struct node{
char usn[20],name[50],branch[10];
int sem;
unsigned long long int phno;
struct node *link;
};
struct node *first=NULL,*last=NULL,*temp=NULL,*p;
void main()
{
int ch,n,i;
while(1)
{
printf("1.create SLL 2.insert at front 3.insert at rear 4.display 5.delete at front 6.delete at
rear 7.exit\n");
printf("enter choice\n");
scanf("%d",&ch);
switch(ch)
{
Case 1:printf("enter the no. of students\n");
scanf("%d",&n);
for(i=1;i<=n;i++)
insert_front();
break;
case 2:insert_front();
break;
case 3:insert_rear();break;
case 4:display();break;
case 5:delete_front();break;
case 6:delete_rear();break;
case 7:exit(0);
default:printf("invalid choice\n");break;
}
}
}
void create()
{
char usn[20],name[50],branch[10];
int sem;
unsigned long long int phno;
temp=(struct node*)malloc(sizeof(struct node));
printf("enter usn,name,branch,sem,phno\n");
scanf("%s%s%s%d%llu",usn,name,branch,&sem,&phno);
strcpy(temp->usn,usn);
strcpy(temp->name,name);
strcpy(temp->branch,branch);
temp->sem=sem;
temp->phno=phno;
count++;
}
void insert_front()
{
if(first==NULL)
{
create();
temp->link=NULL;
first=temp;
last=temp;
}
else
{
create();
temp->link=first;
first=temp;
}
}
void insert_rear()
{
if(first==NULL)
{
create();
temp->link=NULL;
first=temp;
last=temp;
}
else
{
create();
temp->link=NULL;
last->link=temp;
last=temp;
}
}
void display()
{
if(first==NULL)
{
printf("list is empty\n");
}
else
{
p=first;
printf("content of list is\n");
while(p!=NULL)
{
printf("%s\t%s\t%s\t%d\t%llu\n",p->usn,p->name,p->branch,p->sem,p->phno);
p=p->link;
}
printf("total no.of students %d\n",count);
}
}
void delete_front()
{
p=first;
if(first==NULL)
{
printf("list is empty\n");
}
else if(p->link==NULL)
{
printf("deleted node is %s\t%s\t%s\t%d\t%llu\n",p->usn,p->name,p->branch,p->sem,p->phno);
free(p);
first=NULL;
count--;
}
else
{
first=p->link;
printf("deleted node is %s\t%s\t%s\t%d\t%llu\n",p->usn,p->name,p->branch,p->sem,p->phno);
free(p);
count--;
}
}
void delete_rear()
{
p=first;
if(first==NULL)
{
printf("list is empty\n");
}
else if(p->link==NULL)
{
printf("deleted node is %s\t%s\t%s\t%d\t%llu\n",p->usn,p->name,p->branch,p->sem,p->phno);
free(p);
first=NULL;
count--;
}
else
{
while(p->link!=last)
p=p->link;
printf("deleted node is %s\t%s\t%s\t%d\t%llu\n",last->usn,last->name,last->branch,last-
>sem,last->phno);
free(last);
p->link=NULL;
last=p;
count--;
}
}
