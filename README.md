- 👋 Hi, I’m @AnnieSneha
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
AnnieSneha/AnnieSneha is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// C++ program to illustrate the array
// of Linked Lists
#include <iostream>
using namespace std;

// Structure of Linked Lists
struct info {
	int data;
	info* next;
};

// Driver Code
int main()
{
	int size = 10;

	// Pointer To Pointer Array
	info** head;

	// Array of pointers to info struct
	// of size
	head = new info*[size];

	// Initialize pointer array to NULL
	for (int i = 0; i < size; ++i) {
		*(head + i) = NULL;
	}

	// Traverse the pointer array
	for (int i = 0; i < size; ++i) {

		// To track last node of the list
		info* prev = NULL;

		// Randomly taking 4 nodes in each
		// linked list
		int s = 4;

		while (s--) {

			// Create a new node
			info* n = new info;

			// Input the random data
			n->data = i * s;
			n->next = NULL;

			// If the node is first
			if (*(head + i) == NULL) {
				*(head + i) = n;
			}
			else {
				prev->next = n;
			}
			prev = n;
		}
	}

	// Print the array of linked list
	for (int i = 0; i < size; ++i) {
		info* temp = *(head + i);

		// Linked list number
		cout << i << "-->\t";

		// Print the Linked List
		while (temp != NULL) {
			cout << temp->data << " ";
			temp = temp->next;
		}

		cout << '\n';
	}

	return 0;
}
