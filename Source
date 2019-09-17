#include<iostream>
using namespace std;
class Game {
private:
	int count = 0;//count krega k kitne elements packman khagya
	int pos_x=0, pos_y = 0;//packman ki location kia hai x, y k hisab mein yani arr[x][y] hogi position or wahan packman 
	//SHOW KRE GA postx or pos y 
	int tempx = 0, tempy = 0;//ye packman ki old location hai jahan pr hmne * gayab krk space store krni
	bool check_win = false;//jb hm game jeet jayeingay to ye True hojayegaaa
	char arr[15][15]; //ye hmari main array hai jo display horhi jismein * star store hua wa hai
	char ch = 'P'; char input=' ';
public:
	//defualt contructor mein sb kuch initialize krwarhe hain
	Game(){
		for(int i=0;i<15;i++)
			for (int j = 0; j < 15; j++)
			{
				arr[i][j]='*';
				
				pos_x,pos_y = 0;
			}
		arr[0][0] = ch;
	}
	~Game() {
		for (int i = 0; i < 15; i++)
			for (int j = 0; j < 15; j++)
			{
				arr[i][j] = '\0';
			}
	}
	bool check() {
		return check_win;//loop ko btayega k jeet gaye hain ya nhi
			
	}
	void display();//function prototypes
	void Move();
	void checkwin();
};
int main(){
	Game obj; 
	//!obj,check ka mtlb hai k funtion jo btarha is loop ko k jeetgaye ya nhi...agr wo false ho to loop true ho
	//islie ! ka sign use kia haui
	while (!obj.check()) {
		
		
		obj.display();//display ka fucntion call horha...ab jakr display ka function dekho..seedha isk bad
	
		obj.Move();//ye input lene k bad ab character move krwayega pacman ko move krayega..ab ye ye wala function prho pehle
	
		obj.checkwin();//ab checkwin call hoga wo wala dekho
	

	}
	
	return 0;
}
void Game::display() {
	system("cls");//take screen clear krde

	cout << "\t \t";//do bar tab space chorde or game cneter mein chle
	for (int i = 0; i < 16; i++) { cout << "-"; }//game k oper ----------- cshow krne k lie loop
	cout << endl;//usk bad line chorne k lie
	//ab array show kreingay jismein * store hain 
	for (int j = 0; j < 15; j++)
	{
		cout << "\t \t"; cout << "|";//hr line k shuru mein | ka sign lgega border
		for (int k = 0; k < 15; k++)
		{
			cout << arr[j][k];//ye show krega * ya jb ismein pac man hua wo..ya jb isko khalia to space
		}
		cout << "|" << endl;//hr line k end pr bhi border
	}
	cout << "\t \t";//2 tab space
	for (int i = 0; i < 16; i++) { cout << "-"; }//ab array etc k end pr ------- show krega
	cout << endl;//eik line chorne k lie
	cout << "Eat the all * to win the game";//msg
	cout << "Enter the (w,s,a,d) : to play: "; cin >> input;//input lega k pac man kahan move ho
	//Ab wapis main mein jakr dekho agla function konsa hai or kia krrha phr
}
void Game::Move() {
	
	//agr ismein eik bhi if smj lia na programm ki smj ajayegi main yehi hai
	if (input=='d' || input=='D')//agr d enter kia mtlb k ab packman neche move krega eik step arr mein or * kha kr wahan space chordega
	{
		if (pos_y == 14) {//iska mtlb hai k packman agr full right pr hua yani array k axis y 14 hue mtlb k column 14 
			//mein hua agr packman jo k last column hai to sb se pehle column mein ajayega agr dobaran right dubaya
			pos_y = 0;
			arr[pos_x][14] = ' ';//last column mein us row k space store hogi
			arr[pos_x][0] = 'P';//usi row k first colum mein Pack man jo k P hai ajayega store
			}
		else {//else ka mtlb hai k last column mein nhi hai packman
			tempx = pos_x;//abhi jo position packman ki wo store hogi uska x or us y
			tempy = pos_y;
			pos_y++;//phr new position update hogi yani eik agla..right wala column hojayega
			arr[pos_x][pos_y] = ch;//wahan pr P store hoga bec ch mein P hai
			arr[tempx][tempy] =' ';		//or purani position jo tempx and tempy mein store huiw ahan space ajayegi
		
		}
		//Sare if yehi krrha eik right se eik left se eik uper se eik neche se dekhta hai ab again main fucntion dekho
	}
	else if (input=='a')
	{
		if (pos_y == 0) {
			pos_y = 14;
			arr[pos_x][pos_y] = ' ';
			arr[pos_x][0] = 'P';
		}
		else {
			tempx = pos_x;
			tempy = pos_y;
			pos_y--;
			arr[pos_x][pos_y] = 'P';
			arr[tempx][tempy] = ' ';

		}
	}else	if (input=='w')
	{
		if (pos_x == 0) {
			pos_x = 14;
			arr[pos_x][pos_y] = ' ';
			arr[0][pos_y] = 'P';
		}
		else {
			tempx = pos_x;
			tempy = pos_y;
			pos_x--;
			arr[pos_x][pos_y] = 'P';
			arr[tempx][tempy] =' ';
		}
	}
	else	if (input='s')
			{
				if (pos_x == 14) {
					pos_x = 0;
					arr[14][pos_y] = ' ';
					arr[0][pos_y] = 'P';
				}
				else {
					tempx = pos_x;
					tempy = pos_y;
					pos_x++;
					cout << "ink done";
					cout << pos_x << " " << pos_y;

					arr[pos_x][pos_y] = 'P';
					cout << "issuehere";
					arr[tempx][tempy] =' ';
					cout << "emmpty";

				}

			}
		
	}
void Game::checkwin() {
	//array sare elements check kregi jitne packman khagya count ki value utni hojayega kiun k jonsa element packman khayega wahan
	//simple space ajayegi
	for (int i = 0; i < 15; i++)
		for (int j = 0; j < 15; j++)
		{
			if (arr[i][j] == ' ')
				count++;
			
		}
	//Agr sare ch arr mein " "(space hogaye) yani packman khagya to win hojaye array 15 15 ki 2d hai to 15*15 yani 225
	//dfa count++ hojayega jb tb ap jeeet jaogay
	if (count == (15*15)) {
		cout << "Congrats You have Eated All *" << endl;
		cout << "You won The game: ";
		check_win = true;//ye check win variable ko true krdega jis se loop ko true milega or wo false hojayegi
		//or false hogi to dobaran se nhi chelgi mtlv game khtm hai...then
		system("pause");//is lie take show krde ye sb or prh skte banda...k kia likha arha hai jb koi key ab press hogi
		exit(1);//to program game band krdega..bt still Count=0 wala dekho
	}
	else count = 0;//ye else pr hai mtlb k abhi agr game na jeeto ho gay to count mgr increment hoga jitni spaces hui array mein
	//mtlb k agr 25 spaces hui ton count =25 hojayega...jis se agli bar km hui to total jb bhi 225 hogayei ye jeet jayega
	//Ya hostka jb loop chle 224 hojaye ye..then agli bar chle to 224+225 hojayega..jis se loop false he rhegi

	//IMPORTANT::::::::::islie hr abr count ko 0 krdeingay take agli bar 0 se ++ hona shuru ho
}
