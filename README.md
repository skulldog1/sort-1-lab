// Косачев Эдуард ИУ8-24 . Лабораторная работа номер 1 (GitHub)

#include "stdafx.h"
#include <iostream>
using namespace std;

int main()
{
	setlocale(LC_CTYPE, "rus");
	int N;
	cout << "Введите размер массива: ";
	cin >> N; //размер массива
	int* array = new int[N];
	
	cout << "Неотсортированный массив:";

	for (int i = 0; i < N; i++)
	{
		array[i] = rand()%1000;
		cout << array[i] << " ";
	}
	cout << endl;
	// собственно сам алгоритм сортировки пузырьком

	for (int i = N - 1; i >= 1; i--)
		for (int j = 0; j<i; j++)
		{
		if (array[j]>array[j + 1])
		{// меняем местами элементы
			int temp(0);
			temp = array[j];
			array[j] = array[j + 1];
			array[j + 1] = temp;

		}
		}
	// выводим отсортированный с помощью пузырька массив

	cout << "Пузырьковая сортировка:";
	for (int i = 0; i<N; i++)cout << array[i] << " ";
	cout << endl;
	system("pause");
	return 0;
}
