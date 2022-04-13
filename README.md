# data-structure-
**1.Write a C++ program to implement singly linked list**
//write a program to implement the singly linked list ??
#include<iostream><br>
#include<cstdlib> <br>
using namespace std; <br>
struct node<br> 
{ <br>
 int info;<br> 
 struct node *next; <br>
}*start;<br> 
class single_llist<br> 
{ <br>
 public:<br> 
 node* create_node(int); <br>
 void insert_begin();<br> 
 void insert_last();<br>
 void insert_pos();<br> 
 void delete_begin();<br>
 void delete_last();<br> 
 void delete_pos();<br> 
 void update_begin();<br>
 void update_last();<br> 
 void update_pos();<br> 
 void sort();<br> 
 void reverse();<br> 
 void search();<br> 
 void display();<br> 
 single_llist()<br> 
 {<br> 
 start = NULL;<br> 
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice;<br> 
 single_llist sl,s2; <br>
 start = NULL;<br> 
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"Operations on singly linked list"<<endl;<br> 
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl; <br>
 cout<<"3.Insert at position"<<endl; <br>
 cout<<"4.Delete at first"<<endl;<br> 
 cout<<"5.Delete at Last"<<endl; <br>
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl; <br>
 cout<<"9.Update at position"<<endl; <br>
 cout<<"10.Ascending order"<<endl;<br> 
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl;<br> 
 cout<<"14.Exit "<<endl;<br> 
 cout<<"Enter your choice :"; <br>
 cin>>choice; <br>
 switch(choice) <br>
 {<br> 
 case 1: sl.insert_begin();<br> 
 sl.display();<br> 
 break;<br> 
 case 2: sl.insert_last(); <br>
 sl.display(); <br>
 break; <br>
 case 3: sl.insert_pos();<br> 
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last(); <br>
 sl.display();<br> 
 break; <br>
 case 6: sl.delete_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin(); <br>
 sl.display();<br> 
 break; <br>
 case 8: sl.update_last(); <br>
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos(); <br>
 sl.display(); <br><br>
 break; <br>
 case 10:sl.sort(); <br>
 sl.display();<br> 
 break; <br>
 case 11:sl.reverse(); <br>
 sl.display(); <br>
 break; <br>
 case 12:sl.search(); <br>
 sl.display(); <br>
 break; <br>
 case 13:sl.display();<br> 
 break; <br>
 case 14:exit(0); <br>
 break; <br>
 default:cout<<"Wrong choice...???"<<endl; <br>
 break; <br>
 } <br>
 } <br>
 while(choice != 14); <br>
} <br>
node *single_llist::create_node(int value) <br>
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : ";<br> 
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br><br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start;<br> 
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_last() <br>
{ <br>
 int value;<br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next;<br> 
 }<br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 }<br> 
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if(pos == 1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br><br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s;<br> 
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value);<br> 
 while (s->next != NULL) <br>
 { <br><br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin()<br> 
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl;<br> 
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start;<br> 
 while (s != NULL) <br>
 { <br>
 s = s->next; <br><br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next;<br> 
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter)<br> 
 {<br> 
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s;<br> 
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter)<br> 
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br>
 free(s);} <br>
 }<br> 
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } 
  }
} 
void single_llist::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start;<br> 
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++;<br> 
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
  start->info=value;<br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } 
} 
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } 
 s=start;<br> 
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos() <br>
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : ";<br> 
 cin>>pos;<br> 
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 {<br> 
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::sort() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else<br> 
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br> 
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next;<br> 
 } 
 } 
} 
void single_llist::reverse() <br>
{ 
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info < s->info) <br>
 { 
 value = ptr->info;<br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } 
 } 
 ptr = ptr->next; <br>
 } 
 } 
} 
void single_llist::search() <br>
{ 
 int value, loc = 0, pos = 0, counter = 0; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { 
 s = s->next; <br>
  counter++;<br>
 } 
 if (start == NULL){} <br>
 else <br>
 { 
 cout<<"Enter the value to be searched : "; <br>
 cin>>value; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { 
 pos++; <br>
 if (s->info == value) <br>
 { 
 loc++; <br>
 if(loc == 1) <br>
 cout<<"Element "<<value<<" is found at position "<<pos;<br> 
 else if(loc <= counter) <br>
 cout<<" , "<<pos; <br>
 } 
 s = s->next; <br>
 } 
 cout<<endl; <br>
 if (loc == 0) 
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } 
} 
void single_llist::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { 
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL) <br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } 
 cout<<endl; <br>
 } 
}

 ** OUTPUT**:
  ![image](https://user-images.githubusercontent.com/97970956/154893521-f81d458e-5640-432f-ae39-1357aa503e17.png)

![image](https://user-images.githubusercontent.com/97970956/154893698-8c501abd-b684-431b-9149-3fca97d726a8.png)
![image](https://user-images.githubusercontent.com/97970956/154893723-e74288b6-b395-4a26-92f0-ea1b3eb8ffce.png)
![image](https://user-images.githubusercontent.com/97970956/154893754-39f5ed3d-3f33-4333-9881-7740128f0c52.png)
![image](https://user-images.githubusercontent.com/97970956/154893814-83ae36b6-fe31-4cb4-a549-dc5401c40778.png)
![image](https://user-images.githubusercontent.com/97970956/154893853-4c1909a3-6988-4f52-a3a5-887d57cfeea8.png)
![image](https://user-images.githubusercontent.com/97970956/154893894-9e780513-60c9-4964-9f90-38f58d18e8c3.png)
![image](https://user-images.githubusercontent.com/97970956/154893973-19078858-d7b5-41f4-a518-7c2f3309c2d0.png)
  ![image](https://user-images.githubusercontent.com/97970956/154894034-a51ef9f0-9421-4d85-b074-dc4a94b91383.png)
![image](https://user-images.githubusercontent.com/97970956/154895550-dc31164e-d8f8-413a-a96a-c3eb0b9e64e5.png)
![image](https://user-images.githubusercontent.com/97970956/154895598-af69f675-3f00-4219-a17f-e95c65e58bb8.png)
![image](https://user-images.githubusercontent.com/97970956/154895655-a798f472-8892-476a-a47c-e5654306f3d7.png)
![image](https://user-images.githubusercontent.com/97970956/154895733-052c7b21-5233-4a1b-a920-06e0a4c41867.png)
![image](https://user-images.githubusercontent.com/97970956/154895792-5447eac0-0cc4-4f20-8577-f233bc250292.png)
![image](https://user-images.githubusercontent.com/97970956/154895939-58d73a7a-25e7-4de8-b19a-bcec07d5c48f.png)

  
**2. Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.
 **
  #include<iostream><br>
using namespace std;<br>
struct Node{<br>
	int value;<br>
	struct Node*next;<br>
};<br>
struct Node*head=NULL;<br>
struct Node*sHead=NULL;<br>
struct Node*temp=NULL;<br>
void insert(int new_data){<br>
	struct Node*new_node=new Node();//(struct Node*)nalloc(sizeof(structNode));<br>
	new_node->value=new_data;<br>
	new_node->next=head;<br>
	head=new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main(){<br>
	int i;<br>
	cout<<"Enter number of elements you want in the list\t";<br>
	cin>>n;<br>
	cout<<"enter the elements:"<<endl;<br>
	for(i=0;i<n;i++){<br>
		cin>>ele;<br>
		insert(ele);<br>
	}<br>
	cout<<"\n list of elements"<<endl;<br>
	Node*t;<br>
	t=head;<br>
	while(t!=NULL){<br>
		cout<<t->value<<"\t";<br>
		t=t->next;<br>
	}<br>
	cout<<"\n Enter the position you want the list to split";<br>
	cin>>splitIndex;<br>
	while(splitIndex<0||splitIndex>n-1){<br>
		cout<<"Invalid choice,try again"<<endl;<br>
		cin>>splitIndex;<br>
	}<br>
	temp=head;<br>
	for(i=0;i<=
	splitIndex;i++){<br>
		if(i==splitIndex-1){<br>
			Node*tN;<br>
			tN=temp->next;<br>
			sHead=tN;<br>
			temp->next=NULL;<br>
			break;<br>
		}
	temp=temp->next;<br>
		}
	temp=head;<br>
	if(temp==NULL){<br>
		cout<<"\nFirst list is empty"<<endl;<br>
		}else{<br>
			cout<<"\n\n first list element"<<endl;<br>
			while(temp!=NULL){<br>
				cout<<temp->value<<"\t";<br>
				temp=temp->next;<br>
			}
		}
	temp=sHead;<br>
	if(temp==NULL){<br>
		cout<<"\n seconmd list is empty"<<endl;<br>
		}else{<br>
			cout<<"\n \n second list element"<<endl;<br>
			while(temp!=NULL){<br>	
			cout<<temp->value<<"\t";<br>
			temp=temp->next;<br>
	}<br>
}<br>
return 0;<br>
}<br>
  ![image](https://user-images.githubusercontent.com/97970956/154896425-f23f4095-f13f-4b61-a02f-f0fcfbec5814.png)
	
**3.write a  c++ program to implement addition of 2 arrays?** 
#include<iostream><br>
using namespace std;<br>
int main()<br>
{
	int size, i, arr1[10], arr2[10], add[10];<br>
	cout << "\nPlease Enter the Array Size =  ";<br>
	cin >> size;<br>
	cout << "\nPlease Enter the First Array Items =  ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cin >> arr1[i];<br>
	}	<br>
	cout << "\nPlease Enter the Second Array Items =  ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cin >> arr2[i];<br>
	}
	for(i = 0; i < size; i++)<br>
	{
		add[i] = arr1[i] + arr2[i];<br>
		cout << arr1[i] << " + " << arr2[i] << " = " << add[i] << "\n";<br>
	}
	cout << "\nThe Final Result of adding 2 One Dimensional Arrays = ";<br>
	for(i = 0; i < size; i++)<br>
	{<br>
		cout << add[i] << " ";<br>
	}<br>
return 0;<br>
}<br>

**OUTPUT**:
![image](https://user-images.githubusercontent.com/97970956/154901523-bb84c5cb-4bf5-419e-98b7-4020828104bc.png)<br>

	
**4.Write a c++ program to implememnt reverse order of he array element **<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
    int arr[10], i;<br>
    cout<<"Enter 10 Array Elements: ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nThe Original Array is:\n";<br>
    for(i=0; i<10; i++)<br>
        cout<<arr[i]<<" ";<br>
    cout<<"\n\nThe Reverse of Given Array is:\n";<br>
    for(i=(10-1); i>=0; i--)<br>
        cout<<arr[i]<<" ";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>
	
**OUTPUT:**
![image](https://user-images.githubusercontent.com/97970956/154902753-e9b87ef5-1150-4a05-b205-697fdada90c8.png)
	
**5. Write a c++ program to stack using array**
//STACK USING ARRAY
#include <iostream><br>
using namespace std;<br>
int stack[100], n=100, top=-1;<br>
void push(int val) {<br>
   if(top>=n-1)<br>
   cout<<"Stack Overflow"<<endl;<br>
   else {<br>
      top++;<br>
      stack[top]=val;<br>
   }<br>
}<br>
void pop() {<br>
   if(top<=-1)<br>
   cout<<"Stack Underflow"<<endl;<br>
   else {<br>
      cout<<"The popped element is "<< stack[top] <<endl;<br>
      top--;<br>
   }<br>
}<br>
void display() {<br>
   if(top>=0) {<br>
      cout<<"Stack elements are:";<br>
      for(int i=top; i>=0; i--)<br>
      cout<<stack[i]<<" ";<br>
      cout<<endl;<br>
   } else<br>
   cout<<"Stack is empty";<br>
}<br>
int main() {<br>
   int ch, val;<br>
   cout<<"1) Push in stack"<<endl;<br>
   cout<<"2) Pop from stack"<<endl;<br>
   cout<<"3) Display stack"<<endl;<br>
   cout<<"4) Exit"<<endl;<br>
   do {<br>
      cout<<"Enter choice: "<<endl;<br>
      cin>>ch;<br>
      switch(ch) {<br>
         case 1: {<br>
            cout<<"Enter value to be pushed:"<<endl;<br>
            cin>>val;<br>
            push(val);<br>
            break;<br>
         }<br>
         case 2: {<br>
            pop();<br>
            break;<br>
         }<br>
         case 3: {<br>
            display();<br>
            break;<br>
         }<br>
         case 4: {<br>
            cout<<"Exit"<<endl;<br>
            break;<br>
         }<br>
         default: {<br>
            cout<<"Invalid Choice"<<endl;<br>
         }<br>
      }<br>
   }while(ch!=4);<br>
   return 0;<br>
   }<br>
	
**output**
	
![image](https://user-images.githubusercontent.com/97970956/154904414-6cf033f6-4777-4bd0-bfd4-d78e7188b143.png)
	
**6.write c++ program implememnt the binary search**
	#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
    int i, arr[10], num, first, last, middle;<br>
    cout<<"Enter 10 Elements (in ascending order): ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nEnter Element to be Search: ";<br>
    cin>>num;<br>
    first = 0;<br>
    last = 9;<br>
    middle = (first+last)/2;<br>
    while(first <= last)<br>
    {<br>
        if(arr[middle]<num)<br>
            first = middle+1;<br>
        else if(arr[middle]==num)<br>
        {
            cout<<"\nThe number, "<<num<<" found at Position "<<middle+1;<br>
            break;<br>
        }
        else<br>
            last = middle-1;<br>
        middle = (first+last)/2;<br>
    }
    if(first>last)<br>
        cout<<"\nThe number, "<<num<<" is not found in given Array";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>
	
**output**
	
![image](https://user-images.githubusercontent.com/97970956/154905058-42e3717b-ba9c-43c3-94c5-07de98c4821e.png)

**7.Write a program to adding 10 number by using switch statement**<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
	int ch,val;<br>
	cout<<"1.adding 10 numbers using for"<<endl;<br>
	cout<<"2.adding 10 numbers using while"<<endl;<br>
	cout<<"3.adding 10 numbers using do while"<<endl;<br>
	cout<<"4.exit"<<endl;<br>
	do{<br>
		cout<<"enter a choice "<<endl;<br>
		cin>>ch;<br>
		switch(ch)<br>
		{<br>
		case 1:<br>
		{<br>
			int num, sum=0;<br>
  			cout<<"Please enter 10 numbers:"<<endl;<br>
			for(int i=0; i<10; i++)<br>
 			{
 		 	// input is stored in num<br>
   			cin>>num;<br>
   			// adding 10 numbers<br>
   			sum=sum+num;<br>
			}
  			cout << "\n The sum of 10 numbers is: "<<sum << endl;<br>
  			break;<br>
			}<br>
			case 2:<br>
				{<br>
				int n, i=0, num, sum=0;<br>
   				cout<<"Enter the value of n: ";<br>
  				cin>>n;<br>
   				cout<<"Enter "<<n<<" numbers: ";<br>
 				while(i<n)<br>
    					{<br>
   				     	cin>>num;<br>
      				 	sum = sum+num;<br>
        				i++;<br>
    					}<br>
   					 cout<<"\nSum = "<<sum;<br>
 					   cout<<endl;<br>
 					   break;<br>
				}
				case 3: <br>
				{
					int i=0,sum=0,num,n;<br>
					cout<<"enter the value for n";<br>
					cin>>n;<br>
					cout<<"enter the 10 elements"<<endl;<br>
					do <br>
					{
						cin>>num;<br>
						sum=sum+num;<br>
						i++;<br>
					}<br>
					while(i<n);<br>
						cout<<"sum="<<sum;<br>
						break;	<br>				
					}<br>
					case 4:<br>
					{<br>
					cout<<"exit";<br>
						break;<br>
					}<br>
					default:<br>
					cout<<"invalid choice"<<endl;
		}<br>
	}<br>
	while(ch!=4);<br>
	return 0;<br>
	}<br>
	
  ![image](https://user-images.githubusercontent.com/97970956/155065277-1eb33497-3346-4b98-8f79-040d6698cb20.png)

**8.Write a C++ program to implement BST to support the following operations
Assume no duplicate elements while constructing the BST
1.Given a key perform a search in the BST, if the key is found then display “key found”
2.Insert an element into a BST
3.Delete an element from a BST
Display the tree using Inorder,Preorder and Postorder traversal methods
**
# include <iostream> <br>
# include <cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info; <br>
 struct node *left;<br> 
 struct node *right; <br>
}*root; <br>
class BST <br>
{ <br>
 public: <br>
 void find(int, node **, node **); <br>
 void insert(node *, node *); <br>
 void del(int); <br>
 void case_a(node *,node *); <br>
 void case_b(node *,node *); <br>
 void case_c(node *,node *); <br>
 void preorder(node *); <br>
 void inorder(node *); <br>
 void postorder(node *); <br>
 void display(node *, int);<br> 
 BST() <br>
 { <br>
 root = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice, num; <br>
 BST bst; <br>
 node *temp; <br>
 while (1) <br>
 { 
 cou<br>t<<"-----------------"<<endl; <br>
 cout<<"Operations on BST"<<endl; <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"1.Insert Element "<<endl; <br>
 cout<<"2.Delete Element "<<endl; <br>
 cout<<"3.Inorder Traversal"<<endl; <br>
 cout<<"4.Preorder Traversal"<<endl; <br>
 cout<<"5.Postorder Traversal"<<endl;<br> 
 cout<<"6.Display"<<endl; <br>
 cout<<"7.Quit"<<endl; <br>
 cout<<"Enter your choice : "; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: <br>
 temp = new node; <br>
 cout<<"Enter the number to be inserted : "; <br>
 cin>>temp->info; <br>
 bst.insert(root, temp); <br>
 break; <br>
 case 2:<br> 
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty, nothing to delete"<<endl; <br>
 continue; <br>
 } <br>
 cout<<"Enter the number to be deleted : "; <br>
 cin>>num; <br>
 bst.del(num); <br>
 break; <br>
 case 3: <br>
 cout<<"Inorder Traversal of BST:"<<endl; <br>
 bst.inorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 4: <br>
 cout<<"Preorder Traversal of BST:"<<endl; <br>
 bst.preorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 5: 
 cout<<"Postorder Traversal of BST:"<<endl; 
 bst.postorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 6: <br>
 cout<<"Display BST:"<<endl; <br>
 bst.display(root,1); <br>
 cout<<endl; <br>
 break; <br>
 case 7: <br>
 exit(1); <br>
 default: <br>
 cout<<"Wrong choice"<<endl; <br>
 } <br>
 } <br>
} <br>
void BST::find(int item, node **par, node **loc) <br>
{ <br>
 node *ptr, *ptrsave; <br>
 if (root == NULL) <br>
 { <br>
 *loc = NULL; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item == root->info)<br> 
 { <br>
 *loc = root; <br>
 *par = NULL; <br>
 return;<br> 
 } <br>
 if (item < root->info) <br>
 ptr = root->left; <br>
 else <br>
 ptr = root->right; <br>
 ptrsave = root; <br>
 while (ptr != NULL) <br>
 { <br>
 if (item == ptr->info) <br>
 { <br>
 *loc = ptr; <br>
 *par = ptrsave; <br>
 return; <br>
 } <br>
 ptrsave = ptr; <br>
 if (item < ptr->info) <br>
 ptr = ptr->left; <br>
 else <br>
 ptr = ptr->right; <br>
 } <br>
 *loc = NULL; <br>
 *par = ptrsave; <br>
} <br>

void BST::insert(node *tree, node *newnode) <br>
{ <br>
 if (root == NULL) <br>
 { 
 root = new node; <br>
 root->info = newnode->info; <br>
 root->left = NULL; <br>
 root->right = NULL; <br>
 cout<<"Root Node is Added"<<endl; <br>
 return; <br>
 } 
 if (tree->info == newnode->info) <br>
 { 
 cout<<"Element already in the tree"<<endl; <br>
 return; <br>
 } 
 if (tree->info > newnode->info) <br>
 { 
 if (tree->left != NULL) <br>
 { 
 insert(tree->left, newnode); <br>
 } 
 else <br>
 { 
 tree->left = newnode; <br>
 (tree->left)->left = NULL; <br>
 (tree->left)->right = NULL; <br>
 cout<<"Node Added To Left"<<endl; <br>
 return; <br>
 } <br>
 } <br>
 else <br>
 { 
 if (tree->right != NULL) <br>
 { 
 insert(tree->right, newnode);<br> 
 } <br><
 else <br>
 { <br>
 tree->right = newnode; <br>
 (tree->right)->left = NULL; <br>
 (tree->right)->right = NULL; <br>
 cout<<"Node Added To Right"<<endl; <br>
 return; <br>
 } <br>
 } <br>
} <br>

void BST::del(int item) <br>
{ <br>
 node *parent, *location; <br>
 if (root == NULL) <br>
 {<br> 
 cout<<"Tree empty"<<endl; <br>
 return; <br>
 } <br>
 find(item, &parent, &location);<br> 
 if (location == NULL) <br>
 { <br><br>
 cout<<"Item not present in tree"<<endl;<br>
 return; <br>
 } <br>
 if (location->left == NULL && location->right == NULL) <br>
 case_a(parent, location); <br><br>
 if (location->left != NULL && location->right == NULL) <br>
 case_b(parent, location); <br>
 if (location->left == NULL && location->right != NULL) <br>
 case_b(parent, location); <br>
 if (location->left != NULL && location->right != NULL) <br>
 case_c(parent, location); <br>
 free(location); <br>
} <br>
 

void BST::case_a(node *par, node *loc ) <br>
{ <br>
 if (par == NULL) <br>
 { <br>
 root = NULL; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = NULL; <br>
 else <br>
 par->right = NULL;<br> 
 } <br>
} <br>
 

void BST::case_b(node *par, node *loc)<br> 
{ <br>
 node *child;<br> 
 if (loc->left != NULL) <br>
 child = loc->left; <br>
 else <br>
 child = loc->right; <br>
 if (par == NULL) <br>
 { <br>
 root = child; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = child; <br>
 else <br>
 par->right = child;<br> 
 } <br>
} <br>
 

void BST::case_c(node *par, node *loc) <br>
{ <br>
 node *ptr, *ptrsave, *suc, *parsuc;<br> 
 ptrsave = loc; <br>
 ptr = loc->right; <br>
 while (ptr->left != NULL) <br>
 { <br>
 ptrsave = ptr; <br>
 ptr = ptr->left;<br> 
 } <br>
 suc = ptr; <br>
 parsuc = ptrsave; <br>
 if (suc->left == NULL && suc->right == NULL) <br>
 case_a(parsuc, suc); <br>
 else<br> 
 case_b(parsuc, suc); <br>
 if (par == NULL)<br> 
 { <br>
 root = suc; <br>
 } <br>
 else <br>
 { <br>
if(loc==par->left)<br>
 par->left = suc; <br>
 else <br>
 par->right = suc; <br>
 } <br><br>
 suc->left = loc->left; <br>
 suc->right = loc->right; <br>
} <br>
 
 
void BST::preorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 }<br>  
 if (ptr != NULL) <br>
 { 
 cout<<ptr->info<<" "; <br>
 preorder(ptr->left); <br>
 preorder(ptr->right); <br>
 } <br>
} <br>

void BST::inorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br><br>
 cout<<"Tree is empty"<<endl;<br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 {<br>
 inorder(ptr->left); <br>
 cout<<ptr->info<<" "; <br>
 inorder(ptr->right); <br>
 } <br>
}<br> 
 
void BST::postorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl;<br> 
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 postorder(ptr->left); <br>
 postorder(ptr->right); <br>
 cout<<ptr->info<<" "; <br>
 } <br>
} <br>
 
void BST::display(node *ptr, int level) <br>
{ <br>
 int i; <br>
 if (ptr != NULL) <br>
 { <br>
 display(ptr->right, level+1); <br>
 cout<<endl; <br>
 if (ptr == root) <br>
 cout<<"Root->: "; <br>
 else <br>
 { <br>
 for (i = 0;i < level;i++) <br>
 cout<<" "; <br>
 } <br>
 cout<<ptr->info;<br> 
 display(ptr->left, level+1); <br>
 } <br>
}<br>

**OUTPUT:**
![image](https://user-images.githubusercontent.com/97970956/155076069-0d1a9118-7493-4291-b47e-19315efc3362.png)
![image](https://user-images.githubusercontent.com/97970956/155076165-f683b6ae-a494-495e-8513-8e7f7201e159.png)
![image](https://user-images.githubusercontent.com/97970956/155076253-d7fab92f-1750-42d4-bbfd-0c13edc818c2.png)
![image](https://user-images.githubusercontent.com/97970956/155076362-4dc33813-c147-458a-914f-1248cfef5005.png)
![image](https://user-images.githubusercontent.com/97970956/155076431-483339c8-f502-4c7a-a36c-e2a281f478aa.png)

**9.write  a program to implement the min heap**<br>
#include <iostream><br>
#include <conio.h><br>
using namespace std;<br>
void min_heap(int *a, int m, int n){<br>
   int j, t;<br>
   t= a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] < a[j])<br>
         j = j + 1;<br>
      if (t < a[j])<br>
         break;<br>
      else if (t >= a[j]) {<br>
         a[j/2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_minheap(int *a, int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      min_heap(a,k,n);<br>
   }<br>
}<br>
int main() {<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter element"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_minheap(a, n);<br>
   cout<<"Min Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
   getch();<br>
}

![image](https://user-images.githubusercontent.com/97970956/155929437-3949781f-ba2e-4f9b-b577-68d3d789c600.png)

**10.Write a program to implement the maximum heap**<br>
#include <iostream><br>
using namespace std;<br><br>
void max_heap(int *a, int m, int n) {<br>
   int j, t;<br>
   t = a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] > a[j])<br>
         j = j + 1;<br>
      if (t > a[j])<br>
         break;<br>
      else if (t <= a[j]) {<br>
         a[j / 2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_maxheap(int *a,int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      max_heap(a,k,n);<br>
   }<br>
}<br>
int main() {<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter elements"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_maxheap(a,n);<br>
   cout<<"Max Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155931472-5f140705-f1e1-4688-946c-2e9fabf1cd83.png)

**11.Write C++ program for implementing the Heap Sort technique**<br>
#include <iostream><br>
using namespace std;<br>
void MaxHeapify (int a[], int i, int n)<br>
{<br>
	int j, temp;<br>
	temp = a[i];<br>
	j = 2*i;<br>
	while (j <= n)<br>
	{<br>
		if (j < n && a[j+1] > a[j])<br>
		j = j+1;<br>
		if (temp > a[j])<br>
			break;<br>
		else if (temp <= a[j])<br>
		{<br>
			a[j/2] = a[j];<br>
			j = 2*j;<br>
		}<br>
	}<br>
	a[j/2] = temp;<br>
	return;<br>
}<br>
void HeapSort(int a[], int n)<br>
{<br>
	int i, temp;<br>
	for (i = n; i >= 2; i--)<br>
	{<br>
		temp = a[i];<br>
		a[i] = a[1];<br>
		a[1] = temp;<br>
		MaxHeapify(a, 1, i - 1);<br>
	}<br>
}<br>
void Build_MaxHeap(int a[], int n)<br>
{<br>
	int i;<br>
	for(i = n/2; i >= 1; i--)<br>
		MaxHeapify(a, i, n);<br>
}<br>
int main()<br>
{<br>
int n, i,arr[100];<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
	n++;<br>
	for(i=1;i<n;i++)<br>
	 {<br>
	 cout<<"Enter element"<<i<<":";<br>
	 cin>>arr[i];<br>
	 }<br>
	Build_MaxHeap(arr, n-1);<br>
	HeapSort(arr, n-1);<br>
	cout<<"\nSorted Data ";<br>
	for (i = 1; i < n; i++)<br>
		cout<<" "<<arr[i];<br>
	return 0;<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/155935572-ee03a268-ba6f-4bef-9ee2-8617dade488c.png)

**12.Find the subset of given set s={s,s1,s2,s3,.....sn} of n positive integer whose sum is equal to a given positive integer d **
#include <iostream><br>
using namespace std;<br>
void displaySubset(int subSet[], int size) <br>
	{<br>
   		for(int i = 0; i < size; i++)<br>
		    {<br>
      			cout << subSet[i] << "  ";<br>
   			}<br>
        cout << endl;<br>
	}<br>

void subsetSum(int set[], int subSet[], int n, int subSize, int total, int nodeCount ,int sum)<br>
{<br>
   if( total == sum) <br>
  	 	{<br>  
	      displaySubset(subSet, subSize);   <br> 
	      subsetSum(set,subSet,n,subSize-1,total-set[nodeCount],nodeCount+1,sum);  <br>   
	      return;<br>
  		}<br>
   else<br>
    	{<br>
      		for( int i = nodeCount; i < n; i++ )	<br>
	   			{     <br><br>
         			subSet[subSize] = set[i];<br>
         			subsetSum(set,subSet,n,subSize+1,total+set[i],i+1,sum);   <br> 
    			}	<br>		
   		}	<br>
}	<br>	

void findSubset(int set[], int size, int sum) <br>
{<br>
   int *subSet = new int[size]; <br>    
   subsetSum(set, subSet, size, 0, 0, 0, sum);<br>
   delete[] subSet;<br>
}<br>
int main() <br>
{<br>
   int weights[] = {4,6,3,7,5,8,1};<br>
   int size = 7;<br>
   findSubset(weights, size, 11);<br>
}<br>

OUTPUT:
![image](https://user-images.githubusercontent.com/97970956/157186946-dec4a5ad-b19e-4e8f-8a8f-963bd55a487b.png)<br>

**13.WAP to store k keys into an array of size n at the location computed using a hash function, loc = key % n, where k<=n and Key takes values from [1 to m], m>n. Handle the collision using Linear probing technique**<br>
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size)<br>
{<br>
    int element,pos,n=0;<br>
	cout<<"Enter key element to insert\n";<br>
	cin>>element;<br>
	pos = element%hFn; <br>
while(ary[pos]!= INT_MIN) <br><br>
	{ <br> 
			if(ary[pos]== INT_MAX)<br>
            break;<br>
				pos = (pos+1)%hFn;<br>
				n++;<br>
			if(n==Size)<br>
            break; <br>    
	}<br>
		if(n==Size)<br>
        	cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
		else<br>
        	ary[pos] = element; <br>   
}<br>
void display(int ary[],int Size)<br>
{<br>
		int i;<br>
			cout<<"Index\tValue\n";<br>
		for(i=0;i<Size;i++)<br>
			cout<<i<<"\t"<<ary[i]<<"\n";<br>
}
int main()<br>
{<br>
		int Size,hFn,i,choice;<br>
		cout<<"Enter size of hash table\n";<br>
		cin>>Size;<br>
		hFn=Size;<br>
		int ary[Size];<br>
		for(i=0;i<Size;i++)<br>
        ary[i]=INT_MIN; <br>
	do<br>
{<br>
		cout<<"Enter your choice\n";<br>
		cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
		cin>>choice;<br>
		switch(choice)<br>
	{<br>
		case 1:<br>
		Insert(ary,hFn,Size);<br>
		break;<br>
		case 2:<br>
		display(ary,Size);<br>
		break;<br>
		default:<br>
		cout<<"Enter correct choice\n";<br>
		break;<br>
	}<br>
}<br>	
while(choice);<br>
	return 0;<br>
}<br>

![image](https://user-images.githubusercontent.com/97970956/162889229-da473fd7-960d-4632-99f6-ff41d20d0bc0.png)
![image](https://user-images.githubusercontent.com/97970956/162889262-57e922c1-55d5-4fbf-a448-867aeabf4cfa.png)

                                                             
**14.Write a C++ program to implement merge sort technique using divide and conquer method.**
#include <iostream><br>
#include<conio.h><br>
using namespace std;<br>
void Merge(int *a, int low, int high, int mid)<br>
{<br>
	int i, j, k, temp[high-low+1];<br>
	i = low;<br>
	k = 0;<br>
	j = mid + 1;<br>
while (i <= mid && j <= high)<br>
	{<br>
		if (a[i] < a[j])<br>
		{<br>
			temp[k] = a[i];<br>
			k++;<br>
			i++;<br>
		}<br>
		else<br>
		{<br>
			temp[k] = a[j];<br>
			k++;<br>
			j++;<br>
		}<br>
	}<br>
	while (i <= mid)<br>
	{<br>
		temp[k] = a[i];<br>
		k++;<br>
		i++;<br>
	}<br>
	while (j <= high)<br>
	{<br>
		temp[k] = a[j];<br>
		k++;<br>
		j++;<br>
	}<br>
	for (i = low; i <= high; i++)<br><br>
	{<br>
		a[i] = temp[i-low];<br>
	}<br>
}<br>
void MergeSort(int *a, int low, int high)<br>
{<br>
	int mid;<br>
	if (low < high)<br>
	{<br>
		mid=(low+high)/2;<br>
		MergeSort(a, low, mid);<br>
		MergeSort(a, mid+1, high);<br>
		Merge(a, low, high, mid);
	}<br>
}<br>
int main()<br>
{<br>
	int n, i;<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
	int arr[n];<br>
	for(i = 0; i < n; i++)<br>
	{<br>
		cout<<"Enter element "<<i+1<<": ";<br>
		cin>>arr[i];<br>
	}
    	MergeSort(arr, 0, n-1);<br>
		cout<<"\nSorted Data ";<br>
	           for (i = 0; i < n; i++)<br>
                    cout<<"->"<<arr[i]; <br>
	       getch();<br>
}<br>
![image](https://user-images.githubusercontent.com/97970956/162889574-6feda7aa-6fd6-4372-beb6-2919ac5404e6.png)

** **
	#include<iostream>
#include<cstdio>
#include<cstdlib>
using namespace std;
struct node
{
    int info;
    struct node *next;
    struct node *prev;
}*start;
class double_llist
{
    public:
        void create_list(int value);
        void add_begin(int value);
        void add_after(int value, int position);
        void delete_element(int value);
        void search_element(int value);
        void display_dlist();
        void count();
        void reverse();
        double_llist()
        {
            start = NULL;  
        }
};
 int main()
{
    int choice, element, position;
    double_llist dl;
    while (1)
    {
        cout<<endl<<"----------------------------"<<endl;
        cout<<endl<<"Operations on Doubly linked list"<<endl;
        cout<<endl<<"----------------------------"<<endl;        
        cout<<"1.Create Node"<<endl;
        cout<<"2.Add at begining"<<endl;
        cout<<"3.Add after position"<<endl;
        cout<<"4.Delete"<<endl;
        cout<<"5.Display"<<endl;
        cout<<"6.Count"<<endl;
        cout<<"7.Reverse"<<endl;
        cout<<"8.Quit"<<endl;
        cout<<"Enter your choice : ";
        cin>>choice;
        switch ( choice )
        {
        case 1:
            cout<<"Enter the element: ";
            cin>>element;
            dl.create_list(element);
            cout<<endl;
            break;
        case 2:
            cout<<"Enter the element: ";
            cin>>element;
            dl.add_begin(element);
            cout<<endl;
            break;
        case 3:
            cout<<"Enter the element: ";
            cin>>element;
            cout<<"Insert Element after postion: ";
            cin>>position;
            dl.add_after(element, position);
            cout<<endl;
            break;
        case 4:
            if (start == NULL)
            {                      
                cout<<"List empty,nothing to delete"<<endl;  
                break;
            }
            cout<<"Enter the element for deletion: ";
            cin>>element;
            dl.delete_element(element);
            cout<<endl;
            break;
        case 5:
            dl.display_dlist();
            cout<<endl;
            break;
        case 6:
            dl.count();
            break;    
        case 7:
            if (start == NULL)
            {
                cout<<"List empty,nothing to reverse"<<endl;
                break;
            }
            dl.reverse();
            cout<<endl;
            break;
        case 8:
            exit(1);
        default:
            cout<<"Wrong choice"<<endl;
        }
    }
    return 0;
}
 void double_llist::create_list(int value)
{
    struct node *s, *temp;
    temp = new(struct node);
    temp->info = value;
    temp->next = NULL;
    if (start == NULL)
    {
        temp->prev = NULL;
        start = temp;
    }
    else
    {
        s = start;
        while (s->next != NULL)
            s = s->next;
        s->next = temp;
        temp->prev = s;
    }
}
 void double_llist::add_begin(int value)
{
    if (start == NULL)
    {
        cout<<"First Create the list."<<endl;
        return;
    }
    struct node *temp;
    temp = new(struct node);
    temp->prev = NULL;
    temp->info = value;
    temp->next = start;
    start->prev = temp;
    start = temp;
    cout<<"Element Inserted"<<endl;
}
void double_llist::add_after(int value, int pos)
{
    if (start == NULL)
    {
        cout<<"First Create the list."<<endl;
        return;
    }
    struct node *tmp, *q;
    int i;
    q = start;
    for (i = 0;i < pos - 1;i++)
    {
        q = q->next;
        if (q == NULL)
        {
            cout<<"There are less than ";
            cout<<pos<<" elements."<<endl;
            return;
        }
    }
    tmp = new(struct node);
    tmp->info = value;
    if (q->next == NULL)
    {
        q->next = tmp;
        tmp->next = NULL;
        tmp->prev = q;      
    }
    else
    {
        tmp->next = q->next;
        tmp->next->prev = tmp;
        q->next = tmp;
        tmp->prev = q;
    }
    cout<<"Element Inserted"<<endl;
}
 void double_llist::delete_element(int value)
{
    struct node *tmp, *q;
        if (start->info == value)
    {
        tmp = start;
        start = start->next;  
        start->prev = NULL;
        cout<<"Element Deleted"<<endl;
        free(tmp);
        return;
    }
    q = start;
    while (q->next->next != NULL)
    {  
               if (q->next->info == value)  
        {
            tmp = q->next;
            q->next = tmp->next;
            tmp->next->prev = q;
            cout<<"Element Deleted"<<endl;
            free(tmp);
            return;
        }
        q = q->next;
    }
        if (q->next->info == value)    
    {
        tmp = q->next;
        free(tmp);
        q->next = NULL;
        cout<<"Element Deleted"<<endl;
        return;
    }
    cout<<"Element "<<value<<" not found"<<endl;
}
 void double_llist::display_dlist()
{
    struct node *q;
    if (start == NULL)
    {
        cout<<"List empty,nothing to display"<<endl;
        return;
    }
    q = start;
    cout<<"The Doubly Link List is :"<<endl;
    while (q != NULL)
    {
        cout<<q->info<<" <-> ";
        q = q->next;
    }
    cout<<"NULL"<<endl;
}
 void double_llist::count()
{
    struct node *q = start;
    int cnt = 0;
    while (q != NULL)
    {
        q = q->next;
        cnt++;
    }
    cout<<"Number of elements are: "<<cnt<<endl;
}
 void double_llist::reverse()
{
    struct node *p1, *p2;
    p1 = start;
    p2 = p1->next;
    p1->next = NULL;
    p1->prev = p2;
    while (p2 != NULL)
    {
        p2->prev = p2->next;
        p2->next = p1;
        p1 = p2;
        p2 = p2->prev;
    }
    start = p1;
    cout<<"List Reversed"<<endl;
}

	
	
