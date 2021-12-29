# creating-linked-list
#include <stdio.h>
#include <stdlib.h>

struct node
{
  int data;
  struct node *next;
};
struct node *start, *curr;

void
insertElement ()
{
  int num;
  printf ("Enter a element:");
  scanf ("%d", &num);

  struct node *newNode;
  newNode = (struct node *) malloc (sizeof (struct node));
  if (start == NULL)
    {
      newNode->data = num;
      newNode->next = NULL;
      start = newNode;
      curr = newNode;
    }
  else
    {

      curr->next = newNode;
      newNode->next = NULL;
      newNode->data = num;
      curr = newNode;
    }
}

void
displayElement ()
{
  struct node *temp;
  temp = start;
  if (start == NULL)
    {
      printf ("the link list is empty.");
    }
  else
    {
      printf ("\nLinked list is :");
      while (temp != NULL)
	{
	  printf ("%d ", temp->data);
	  temp = temp->next;
	}
      printf ("\n");
    }

  printf ("\n");
}

int
main ()
{
  int choice;
  printf("***CREATING A LINKED LIST***\n");
  printf ("1. insert.\n2. display.\n3. Exit\n");
  printf ("Enter your choice:");
  scanf ("%d", &choice);

  while (choice != 3)
    {
      switch (choice)
	{
	case 1:
	  insertElement ();
	  break;
	case 2:
	  displayElement ();
	  break;
	case 3:
	  break;

	default:
	  printf ("You have entered a worong number\n");
	  break;
	}
      printf ("Enter your choice:");
      scanf ("%d", &choice);
    }
  printf ("Exit the program\n");
}
