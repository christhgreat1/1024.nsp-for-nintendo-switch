#include<iostream>
#include<cstdlib>
#include<ctime>
#include<conio.h>
using namespace std;


void new_num(int [4][4]);								//to generate random number ap random place
void instructions();								   //intro before game start up
void new_game(int[4][4]);							  //to start new game at any instance of program
void move_up(int[4][4]);							 //up movement
void move_down(int[4][4]);							//down movement
void move_left(int[4][4]);						   //left movement
void move_right(int[4][4]);						  //right movement
bool block_check(int[4][4], int[4][4]);			 //to add new block or not
bool game_win_check(int[4][4], int);			//linear search to check if you won the game
bool game_over_check(int[4][4]);			   //comparision of elements to check if any move is possib

void instructions() 
{
	cout << "\t\t\tThe purpose of this game is fun!\n";
	cout << "\t\t\t\t\t1024\n\n\n";
	cout << "\t\t\tTO paly the game use keys\n";
	cout << "\t\t\tN: New game\n\t\t\tU: Up\n\t\t\tL: Left\n\t\t\tD: Down\n\t\t\tR: Right\n\t\t\tQ: Quit\nYou can also use ARROW keys to play game\n\n";
	
}

void new_game(int a[4][4])
{
	for (int i = 0; i < 4; i++)
	{
		for (int j = 0; j < 4; j++)
		{
			a[i][j] = 0;
		}
	}

	new_num(a);
}

void move_up(int a[4][4])
{
	int i, j, ci, ri;
	for (j = 0; j < 4; j++)
	{
		ri = 0, ci = j;
		for (i = 1; i < 4; i++)
		{
			if (a[i][j] != 0)
			{
				if (a[i - 1][j] == 0 || a[i - 1][j] == a[i][j])
				{
					if (a[ri][ci] == a[i][j])
					{
						a[ri][ci] *= 2;
						a[i][j] = 0;
						ri++;
					}
					else
					{
						if (a[ri][ci] == 0)
						{
							a[ri++][ci] = a[i][j];
							a[i][j] = 0;
						}
						else
						{
							a[++ri][ci] = a[i][j];
							a[i][j] = 0;
						}
					}
				}
				else ri++;
			}
		}
	}
}

void move_down(int a[4][4])
{
	int i, j, ci, ri;
	for (j = 0; j < 4; j++)
	{
		ci = 3, ri = j;
		for (i = 2; i >= 0; i--)
		{
			if (a[i][j] != 0)
			{
				if (a[i + 1][j] == 0 || a[i + 1][j] == a[i][j])
				{
					if (a[ci][ri] == a[i][j])
					{
						a[ci][ri] *= 2;
						a[i][j] = 0;
						ci--;
					}
					else
					{
						if (a[ci][ri] == 0)
						{
							a[ci--][ri] = a[i][j];
							a[i][j] = 0;
						}
						else
						{
							a[--ci][ri] = a[i][j];
							a[i][j] = 0;
						}
					}
				}
				else ci--;
			}
		}
	}
}

void move_left(int a[4][4])
{
	int i, j, ci, ri;
	for (i = 0; i < 4; i++)
	{
		ci = i, ri = 0;
		for (j = 1; j < 4; j++)
		{
			if (a[i][j] != 0)
			{
				if (a[i][j - 1] == 0 || a[i][j - 1] == a[i][j])
				{
					if (a[ci][ri] == a[i][j])
					{
						a[ci][ri] *= 2;
						a[i][j] = 0;
						ri++;
					}
					else
					{
						if (a[ci][ri] == 0)
						{
							a[ci][ri++] = a[i][j];
							a[i][j] = 0;
						}
						else
						{
							a[ci][++ri] = a[i][j];
							a[i][j] = 0;
						}
					}
				}
				else ri++;
			}
		}
	}
}

void move_right(int a[4][4])
{
	int i, j, ci, ri;
	for (i = 0; i < 4; i++)
	{
		ci = i, ri = 3;
		for (j = 2; j >= 0; j--)
		{
			if (a[i][j] != 0)
			{
				if (a[i][j + 1] == 0 || a[i][j + 1] == a[i][j])
				{
					if (a[ci][ri] == a[i][j])
					{
						a[ci][ri] *= 2;
						a[i][j] = 0;
						ri--;
					}
					else
					{
						if (a[ci][ri] == 0)
						{
							a[ci][ri--] = a[i][j];
							a[i][j] = 0;
						}
						else
						{
							a[ci][--ri] = a[i][j];
							a[i][j] = 0;
						}
					}
				}
				else ri--;
			}
		}
	}
}

bool block_check(int a[4][4], int b[4][4])
{
	bool flag = false;
	for (int i = 0; i < 4; i++)
	{
		for (int j = 0; j < 4; j++)
		{
			if (a[i][j] != b[i][j])
			{
				flag = true;
			}
		}
	}

	return flag ;
}

bool game_win_check(int a[4][4], int key)
{
	bool flag = false;
	for (int i = 0; i < 4 &&!flag; i++)
	{
		for (int j = 0; j < 4; j++)
		{
			if (a[i][j] == key)
			{
				flag = true;
				break;
			}
		}
	}
	return flag;
}

bool game_over_check(int a[4][4])
{
	bool flag = false, flag2 = false;

	int i,j;
	for (i = 0; i < 4; i++)
	{
		for (j = 0; j < 4; j++)
		{
			if (a[i][j] == 0)
			{
				flag = true;
				break;
			}
		}
	}
	for (i = 0; i < 3; i++)
	{
		for (j = 0; j < 3; j++)
		{
			if (a[i + 1][j] == a[i][j] || a[i][j + 1] == a[i][j])
			{
				flag2 = true;
				break;
			}
		}
	}
	if (a[0][3] == a[1][3] || a[1][3] == a[2][3] || a[2][3] == a[3][3] || a[3][0] == a[3][1] || a[3][1] == a[3][2] || a[3][2] == a[3][3])
		flag2 = true;

	if (flag || flag2)
		return true;
	else
		return false;
	
}

void display_rid(int a[4][4])
{
	int i, j;
	cout << endl << endl << endl;
	for (i = 0; i < 4; i++)
	{
		cout << "\t\t\t\t-------------------------\n\t\t\t\t";
		for (j = 0; j < 4; j++)
		{
			if (a[i][j] == 0) 
				cout << "|"<<"     ";
			else if (a[i][j]<10)
				cout << "|  " << a[i][j]<<"  ";
			else if (a[i][j] < 999 && a[i][j]>10)
				cout << "| " << a[i][j] << " ";
			else if (a[i][j] > 999 && a[i][j] < 9999)
				cout << "| " << a[i][j];
		}
		cout << "|" << endl;
	}
	cout << "\t\t\t\t-------------------------\n";
	
}

void new_num(int a[4][4])
{
	srand(time(0));

	int r , c;
	int block = (rand() % 2) + 1;
	while (true)
	{
		r = rand() % 4;
		c = rand() % 4;
		if (a[r][c] == 0)
			break;
	}
	a[r][c] = block;
}

int main()
{
	char ch;
	instructions();
	int j = 0, sum = 0, key=1024;
	
	int a[4][4], temp[4][4] = {};
	cout << "\nPress N key to start the game: ";
	
	while (true)
	{
		
		for (int i = 0; i < 4; i++)
		{
			for (int j = 0; j < 4; j++)
			{
				temp[i][j] = a[i][j];
			}
		}

		if (game_win_check(a, key))
		{
			cout << "Congratulations!!!\nYou won the game\nWould you like to start new game?\nFor new game press N AND to  Exit Press Q ";
			ch = _getch();
			while (ch != 'n' && ch != 'N' && ch != 'q' && ch != 'Q')
			{
				cout << "\nEnter N for new game OR Q to quit ";
				ch = _getch();
			}
		}
		else if (!game_over_check(a))
		{
			cout << "You lost\nGAME OVER\n\nFor new game press N AND to  Exit Press Q ";
			ch=_getch();
			while (ch != 'n' && ch != 'N' && ch != 'q' && ch != 'Q')
			{
				cout << "\nEnter N for new game OR Q to quit ";
				ch = _getch();
			}
		}
		else
		{
			ch = _getch();
			if (j == 0)
			{
				while (ch != 'n' && ch != 'N')
				{
					cout << "\nPress N ";
					ch = _getch();
				}
				j++;
			}
		}

		
		system("cls");
		if (ch == 'q' || ch == 'Q')
		{
			cout << "\t\t\tA game by:\n\t\t\t\tMuhammad Uzair\n\t\t\t\tMohammad Khizar\n\t\t\t\tAli Ahsan\n\n\n\t\t\t";
			system("pause");
			break;

		}
		if (ch == 'n' || ch == 'N')
		{
			sum = 0;
			new_game(a);
		}
		if ( ch == 72||ch=='u'||ch=='U')
		{
			move_up(a);
		}
		if (ch==75||ch=='l'||ch=='L')
		{
			move_left(a);
		}
		if (ch=='d'||ch=='D'||ch==80)
		{
			move_down(a);
		}
		if (ch=='R'||ch=='r'||ch==77)
		{
			move_right(a);
		}
		if (block_check(a, temp))
		{
			new_num(a);
			
		}

		display_rid(a);

		cout << "The total score of the game is: " << " " << sum<<endl;
		 sum = 0;
		for (int i = 0; i < 4; i++)
		{
			for (int j = 0; j < 4; j++)
			{
				sum += a[i][j];
			}
		}
				
		

	}
	
	return 0;
}
