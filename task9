#include <iostream>
#include <fstream>
#include <string>
#include <sstream>

using namespace std;


int main(int argc, char** argv) {
	
	//Вывод информации из файла
	ifstream town_file("towns.txt");
	string temp_t;
	int m = 4;
	int n = 0;
	
	//Вычисление количества строк
	while (getline(town_file, temp_t)) {                                                                                                                                                
        n++;                                                                                                                                                                                                                                                                                               
    }
    
    town_file.clear();                                                                                                                                        
    town_file.seekg(0);
    
    //объявление двумерного массива
    string **town_mas = new string*[n];
    for(int i=0; i<n; ++i) {
    	town_mas[i] = new string[m];
	}
	
	//Запись в массив
	int k = 0;
	while (getline(town_file, temp_t)) {
		istringstream ist(temp_t);
		int j = 0;
		for (string word; ist >> word;) {
			switch(j) {
				case 0:
					town_mas[k][j] = word;
					j++;
					break;
				case 1:
					town_mas[k][j] = word;
					j++;
					break;
				case 2:
					town_mas[k][j] = word;
					j++;
					break;
				case 3:
					town_mas[k][j] = word;
					j = 0;
					k++;
					break;
			}
		}                                                                                                                                                                                                                                                                                                                                                                                                                                             
    }
    
    cout << "Введите страну, чтобы узнать самый населённый город (С большой буквы): " << endl;
    string country_big = "";
    getline(cin, country_big);
    float fl_big = false;
    int max_country_big = 0;
    string biggest_town = "";
    
	int max_town_s = 0;
	string s_town_name = "";
	
	string more_big_town = "";
	    
    cout << "Введите страну, чтобы узнать количество городов: " << endl;
    string country_amount_name = "";
    getline(cin, country_amount_name);
    int country_amount = 0;
    
    for (int i=0; i<n; i++) {
		if (town_mas[i][1] == country_big) {
			fl_big = true;
			if (max_country_big < stoi(town_mas[i][2]))	{
				max_country_big = stoi(town_mas[i][2]);
				biggest_town = town_mas[i][0];
			}
		}
		
		int town_s = stoi(town_mas[i][2]) / stoi(town_mas[i][3]);
		if (town_s > max_town_s) {
			max_town_s = town_s;
			s_town_name = town_mas[i][0];
		}
		
		if (stoi(town_mas[i][2]) > 1000000) {
			bool found = more_big_town.find(town_mas[i][1]) != string::npos;
			if (!found){
				more_big_town += town_mas[i][1] + " ";
			}
		}
		
		if (country_amount_name == town_mas[i][1]) {
			country_amount++;
		}
			 
	}
	
	if (fl_big == true){
    	cout << "В стране " << country_big << " самый большой город - " << biggest_town << endl;
	} else {
		cout << "Страны " << country_big << " нет в списке!" << endl;
	}
	
	cout << "Город с самой большой плотностью населения: " << s_town_name << endl;
	
	cout << "Страны с городами больше 1000000 населения: " << more_big_town << endl;
	

	cout << "В стране " << country_amount_name << " " << country_amount << " городов" << endl;
	
	
	return 0;
}
