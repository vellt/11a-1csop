```c#
/*
	Hozzunk létre egy N elemű tömböt
	Az N-t konzolból kérjük be
	N>3 !!
	elemei [-12,50]-ból legyenek
	Kérdés: Minden eleme különböző?
 */
while (true)
{
	Console.WriteLine("Adj meg egy 3nál nagyobb értéket");
	int N = Convert.ToInt32(Console.ReadLine());
	Random r = new Random();
	if (N > 3)
	{
		int[] tomb = new int[N];
		for (int i = 0; i < tomb.Length; i++)
		{
			tomb[i] = r.Next(63)-12; // [-12,50]
			Console.Write($"{tomb[i],-5}");
		}
		// döntsük el hogy minden elem egyedi-e?
		bool igaz = false;
		for (int i = 0; igaz==false && i < tomb.Length; i++)
		{
			int keresedoErtek = tomb[i];
			int szamlalo = 0;
			for (int j = 0; igaz==false && j < tomb.Length; j++)
			{
				if (tomb[j] == keresedoErtek)
				{
					szamlalo++;
					if (szamlalo == 2) igaz = true;
				}
			}
		}
		Console.WriteLine(igaz? "A tömb nem egyedi":"A tömb minden értéke egyedi");
		// döntsük el hogy minden elem egyedi-e? (2. próbálkozás)
		int[] temp = new int[N];
		for (int i = 0; i < temp.Length; i++)
		{
			temp[i] = 51;
		}
		int index = 0;
		for (int i = 0; i < tomb.Length; i++)
		{
			int ertek = tomb[i];
			bool van = false;
			for (int j = 0; van==false && j < temp.Length; j++)
			{
				if (temp[j] == ertek)
				{
					van = true;
				}
			}
			if (van==false)
			{
				temp[index++] = ertek;
			}
		}
		if (index == tomb.Length)
		{
			Console.WriteLine("minden érték egyedi");
		}
		else
		{
			Console.WriteLine("van benne ismétlődés");
		}
		Console.ReadKey();
	}
	else
	{
		Console.WriteLine("Nem jó értéket adtál meg!");
	}
}
```