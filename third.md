Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
#include <string>
using namespace std;
struct Book 
{
    string isbn;
    string title;
    string author;
    int year;
    string genre;
};

void searchBook(const Book library[], int size, const string& isbn) 
{

    bool found = false;
    for (int i = 0; i < size; ++i) 
	{
        if (library[i].isbn == isbn) 
		{
            found = true;
            cout << "Book found!" << endl;
            cout << "Title: " << library[i].title << endl;
            cout << "Author: " << library[i].author << endl;
            cout << "Year: " << library[i].year << endl;
            cout << "Genre: " << library[i].genre << endl;
            break;
        }
    }
    
    if (!found) 
	{
        cout << "Book not available in the library." << endl;
    }
}

int main() 
{
	cout<<"TANYA\n";
	cout<<"2310997305\n";
	const int librarySize = 4;
    Book library[librarySize] = 
	{
        {"978-81-933904-8-1", "ACCIDENTS DO NOT HAPPEN", "Dr Sankar Rajeev", 2018},
        {"978-81-933904-6-7", "PROPAGATION OF GLORY LILY","Dr. S. ANANDHI ",2017},
        {"978-81-933904-0-5","SANSRITI"," Dr.Vibha Manoj Sharma", 2017 },
        {"978-81-933199-0-1", "JAVA A Building Approach through Object Oriented Programming", "Dr Shaik Akbar and Ch Hari Prasad", 2017}
    };

    cout << "Enter the ISBN of the book you want to search for: ";
    string isbn;
    cin >> isbn;

    searchBook(library, librarySize, isbn);

    return 0;
}
