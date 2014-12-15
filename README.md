updatedprojectversion2
======================
#include <iostream>
#include <cstdlib>
#include <time.h>
#include <fstream>
#include <string>
#include <iomanip>
using namespace std;

const int NUM_STUDENTS = 30;
const int NUM_QUIZZES = 10;
const int NUM_EXAMS = 5;
int quiz1, quiz2, quiz3, quiz4, quiz5, quiz6, quiz7, quiz8, quiz9, quiz10;
int test1, test2, test3, test4, test5;
int user;

struct Student
{
	string firstName, lastName;
	int quizzes[NUM_QUIZZES];
	int exams[NUM_EXAMS];
};
void structure(Student[]);
void studentname(Student[], int);

int main()
{
	
	int grade;
	Student cop1334[NUM_STUDENTS];

	cout << "\tWelcome to Gradebook \n"
		<< "\n1. Course Grade for a particular student"
		<< "\n2. Average for particularQuiz"
		<< "\n3. Average for particular Test"
		<< "\n4. The lowest quiz average"
		<< "\n5. Summary"
		<< "\n6. Breakdown of letter grades"
		<< "\n~Any other character to exit program~"
		<< "\n\nPlease choose an option from the menu: ";
	cin >> user;
	structure(cop1334);

	if (user == 1)
	{
		string firstname;
		string quizzes;
		studentname(cop1334, NUM_QUIZZES);
	
	}
	else if (user == 2)
	{

		
	}
	else if (user == 3)
	{
		string test;
		cout << "\nYou have choosen option 3" << "\nPlease choose Test #1 - 5 for average" << endl;

		//not done
	}
	else if (user == 4)
	{
		cout << "\nYou have choosen option 4" << "\nThe lowest quiz average is" << endl;
		//connect to file
	}
	else if (user == 5)
	{
		cout << "\nYou have choosen option 5" << "\nSummary: " << endl;

		//course grade for every student 

		//just connect to file
	}
	else if (user == 6)
	{
		cout << "\nYou have choosen option 6" << "\nCourse Breakdown: " << endl;


	}

	else
	{
		cout << "You are exiting the program. Thank you!" << endl;
		system("pause");
		exit(0);
	}

	system("pause");
	return 0;
}


void structure(Student cop1334[])
{
	ifstream inputfile;
	inputfile.open("C:/Users/Mimi/Desktop/simple.txt");

	if (!inputfile)
	{
		cout << "File could not be opened." << endl;
	}

	for (int index = 0; index < NUM_STUDENTS; index++)
	{
		inputfile >> cop1334[index].firstName >> cop1334[index].lastName;

		for (int i = 0; i < NUM_QUIZZES; i++)
		{
			inputfile >> cop1334[index].quizzes[i];
		}

		for (int i = 0; i < NUM_EXAMS; i++)
		{
			inputfile >> cop1334[index].exams[i];
		}

	}

}


void studentName(Student cop1334[], int size)
{
	string studentName;
	

	cout << "Please enter first or last name of student to see his/her grades: ";
	cin >> studentName;

	for (int i = 0; i < size; ++i)
	{
		if (studentName.compare(cop1334[i].firstName + " " + cop1334[i].lastName) == 0)
		{
			// Do grade calculation, average...
			cout << "Grade = " << cop1334[i].quizzes;
		}
	}

}
