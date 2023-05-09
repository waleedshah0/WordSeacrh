# WordSeacrh
Word Seacrh Game in C++
#include <iostream>
#include <string>
#include <stdlib.h>
#include <ctime>
#include <windows.h>
using namespace std;
int main()
{
	char choies;
	int level;
	int win = 0, lose = 0, count = 0;
	//system("Color 60");
	HANDLE h = GetStdHandle(STD_OUTPUT_HANDLE);
	SetConsoleTextAttribute(h, FOREGROUND_RED | FOREGROUND_INTENSITY);
	cout << "WELCOME TO THE WORD SEARCH GAME" << endl;
	cout << endl;
	cout << "You have to types only letter in one try" << endl;
	cout << endl;
	do
	{
		cout << "Select Level : " << endl << "Enter 1 --> Easy " << endl << "Enter 2--> Hard" << endl;
		cin >> level;

		switch (level)
		{
		case 1:
		{


				  cout << "Now" << endl;
				  cout << endl;
				  cout << "Guess the word" << endl;
				  int max_tries = 6;
				  char letter;
				  int wrong_guess = 0;
				  string word;
				  int guess = 0;

				  const string wordlist[12] = { "school", "laptop", "mobile", "pencil", "quetta", "lahore", "source" };
				  /*for (int i = 0; i<20; i++)
				  {
				  cout << words[i] << "  ";
				  }*/

				  srand(time(0));
				  word = wordlist[rand() % 12];
				  // word2[] = { word };

				  cout << word[0] << " _ " << " _ " << word[3] << " _ " << word[4] << " _ " << endl << endl;


				  while (wrong_guess < max_tries)
				  {
					  cin >> letter;
					  if (letter == word[2] || letter == word[1] || letter == word[5])
					  {
						  cout << "You got it " << endl;
						  cout << "Enter another one " << endl;
						  guess++;
						  if (guess == 5)
						  {
							  cout << "Letters are correct" << endl << endl;
							  cout << "Word is " << word << endl << endl;
							  win++;
							  break;
						  }
					  }
					  else
					  {
						  cout << "Wrong Letter " << endl;

						  wrong_guess++;
						  cout << "Remaining Tries " << max_tries - wrong_guess << endl;
						  if (wrong_guess == 6)
						  {
							  cout << "Letters are not correct" << endl << endl;
							  cout << "Word is " << word << endl << endl;
							  lose++;

						  }
					  }
				  }
				  break;
		}
		case 2:
		{
				  cout << "Now" << endl;
				  cout << endl;
				  cout << "Guess the word" << endl;
				  int max_tries = 4;
				  char letter;
				  int wrong_guess = 0;
				  string word;
				  int guess = 0;

				  const string wordlist[12] = { "buzzbombs",
					  "squizzing",
					  "whizzbang",
					  "buzzkills",
					  "jazziness",
					  "showbizzy",
					  "whizzkids",
					  "bemuzzled",
					  "blackjack",
					  "buckjumps",
					  "chazzanim",
					  "chazzenim" };
				  /*for (int i = 0; i<20; i++)
				  {
				  cout << words[i] << "  ";
				  }*/

				  srand(time(0));   //changing word every time because of #include <ctime> library
				  word = wordlist[rand() % 12];
				  // word2[] = { word };

				  cout << word[0] << " _ " << " _ " << word[3] << " _ " << word[4] << " _ " << " _ " << word[7] << " _ " << endl << endl;


				  while (wrong_guess < max_tries)
				  {
					  cin >> letter;
					  if (letter == word[2] || letter == word[1] || letter == word[6] || letter == word[5] || letter == word[8])
					  {
						  cout << "You got it " << endl;
						  cout << "Enter another one " << endl;
						  guess++;
						  if (guess == 5)
						  {
							  cout << "Letters are correct" << endl << endl;
							  cout << "Word is " << word << endl << endl;
							  win++;
							  break;
						  }
					  }
					  else
					  {
						  cout << "Wrong Letter " << endl;

						  wrong_guess++;
						  cout << "Remaining Tries " << max_tries - wrong_guess << endl;
						  if (wrong_guess == 4)
						  {
							  cout << "Letters are not correct" << endl << endl;
							  cout << "Word is " << word << endl << endl;
							  lose++;
						  }
					  }
				  }
				  break;
		}

		}
		cout << "Did you want to play again (Press Y for yes) (Press N for No)" << endl;
		cin >> choies;
	} while (choies == 'y');
	cout << "Loses = " << lose << endl;
	cout << "Wins = " << win << endl;

	system("pause");
	return 0;
}
