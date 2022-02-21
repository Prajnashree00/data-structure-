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

  
2. Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.
 
  
  #include<iostream>
using namespace std;
struct Node{
	int value;
	struct Node*next;
};
struct Node*head=NULL;
struct Node*sHead=NULL;
struct Node*temp=NULL;
void insert(int new_data){
	struct Node*new_node=new Node();//(struct Node*)nalloc(sizeof(structNode));
	new_node->value=new_data;
	new_node->next=head;
	head=new_node;
}
int n;
int ele;
int splitIndex;
int main(){
	int i;
	cout<<"Enter number of elements you want in the list\t";
	cin>>n;
	cout<<"enter the elements:"<<endl;
	for(i=0;i<n;i++){
		cin>>ele;
		insert(ele);
		
	}
	cout<<"\n list of elements"<<endl;
	Node*t;
	t=head;
	while(t!=NULL){
		cout<<t->value<<"\t";
		t=t->next;
	}
	cout<<"\n Enter the position you want the list to split";
	cin>>splitIndex;
	while(splitIndex<0||splitIndex>n-1){
		cout<<"Invalid choice,try again"<<endl;
		cin>>splitIndex;
	}
	temp=head;
	for(i=0;i<=
	splitIndex;i++){
		if(i==splitIndex-1){
			Node*tN;
			tN=temp->next;
			sHead=tN;
			temp->next=NULL;
			break;
		
		}temp=temp->next;
		
	}
	temp=head;
	if(temp==NULL){
		cout<<"\nFirst list is empty"<<endl;
		}else{
			cout<<"\n\n first list element"<<endl;
			while(temp!=NULL){
				cout<<temp->value<<"\t";
				temp=temp->next;
			}
		}
	temp=sHead;
	if(temp==NULL){
		cout<<"\n seconmd list is empty"<<endl;
		}else{
			cout<<"\n \n second list element"<<endl;
			while(temp!=NULL){
				
			cout<<temp->value<<"\t";
			temp=temp->next;
		}
}
return 0;
}
  ![image](https://user-images.githubusercontent.com/97970956/154896425-f23f4095-f13f-4b61-a02f-f0fcfbec5814.png)
