/* Linked-List
implemantion for  linked list using c++               */
#include<iostream>
using namespace std;
template<class type>
class node
{
public:
	type data;
	node *link;
};
template<class type>
class linkedList
{
	node<type>* head, * tail;
	int counter;
public:
	linkedList()
	{
		head = tail = NULL;
		counter = 0;
	}
	bool IsEmpty()
	{
		return (head == nullptr);
	}
	void InsertFirst(type e)
	{
		node<type>* newNode = new node<type>;
		newNode->data = e;
		newNode->link = nullptr;
		if (IsEmpty())
		{
			head = tail = newNode;
		}
		else
		{
			newNode->link = head;
			head = newNode;
		}
		counter++;
	}
	void InsertLast(type e)
	{
		node<type>* newNode = new node<type>;
		newNode->data = e;
		if (IsEmpty())
		{
			head = tail = newNode;
		}
		else
		{
			tail->link = newNode;
			tail = newNode;
		}
		counter++;
	}
	void InsertPossition(type e , int poss)
	{
		node <type> *newNode = new node<type>;
		newNode->data = e;
		if (poss < 1 || poss > counter + 1)
		{
			cout << " INVLID POSSITION !!!" << endl;
			return;
		}
		else if (poss == 1)
		{
			InsertFirst(e);
		}
		else if (poss == counter + 1)
		{
			InsertLast(e);
		}
		else
		{
			node<type>* current = head ;
			int i = 1;
			while (i != poss -1)
			{
				current = current->link;
				i++;
				if (i == poss - 1)
				{
					newNode->link = current->link;
					current->link = newNode;
					break;
				}
			}
			counter++;
		}
	}
	void Delet(type e)
	{
		if(IsEmpty())
		{
			cout << " THE LIST IS EMPTY !! " << endl;
		}
		bool found = false; 
		node<type>* current = head;
		node<type>* preCurrent = NULL;
		while (current != NULL && ! found)
		{
			if (current->data == e)found = true;
			else
			{
				preCurrent = current;
				current = current->link;
			}
		}
		if (!found)
		{
			cout << " THE ITEM IS NOT IN THE LIST !!!" << endl;
			return;
		}
		else
		{
			if (current == head)
			{
				head = current->link;
				if (head == NULL)tail = nullptr;
				delete current;
			}
			else
			{
				preCurrent->link = current->link;
				if (current == tail)tail = preCurrent;
				delete current;
			}
			counter--;
		}
	}
	void display()
	{
		node <type>* temp = head;
		while (temp != nullptr)
		{
			cout << temp->data << "  ";
			temp = temp->link;
		}
	}
};
int main()
{
	// declare an object .....
	linkedList<int> l;
	// call functions from the class
	l.InsertFirst(5);
	l.InsertFirst(10);
	l.InsertLast(4);
	l.InsertLast(8);
	l.InsertPossition(7, 3);
	l.display();
	return 0;
}
