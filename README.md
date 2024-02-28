```c#
static void Main(string[] args)
{
	feladat1();
	feladat2();
	Console.ReadKey();
}

private static void feladat2()
{
	// MÁTRIX ISMÉTLÉS
	int[,] matrix = new int[2, 4]
	{
		{2, 3, 4, 5 },
		{2, 4, 5, 6 }
	};
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)//2
	{
		for (int j = 0; j < matrix.GetLength(1); j++) //4
		{
			// értékadás
			matrix[i, j] = r.Next(10) + 1; //[1,10]
			// értékkiíratás
			Console.Write($"{matrix[i,j]}");
		}
	}
	// -----------------------------------------------------------

	/*
	 egy 14 fős csoportban AAF-ból a tanár minden hónapban egy röpdolgozatot írat
	eltelt 4 hónap. Mindenki kapott egy-egy jegyet [1,5]-ban minden dogára.
	- mennyi az osztályátlag
	- mennyi tanulónak van 3egésznél kisebb átlaga
	- mennyi tanuló áll 5-re (4.6-tól)
	- melyik tanulónak menniy az átlaga
	- mennyi tanuló van az osztályátlag alatt
	 */

	int[,] osztaly = new int[14 , 4];
	Random rand = new Random();
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osztaly[i, j] = rand.Next(5)+1;
		}
	}
	// melyik tanulónak menniy az átlaga
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int osszJegy = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszJegy += osztaly[i, j];
		}
		double atlag = (double)osszJegy / osztaly.GetLength(1);
		Console.WriteLine($"{i+1}. tanuló átlaga: {atlag:0.00}");
	}


}

private static void feladat1()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a " +
		"vasutipar rekordjait. Keszul az 1000 km/h-s vonat.";

	// mennyi db szám van benne
	int darab = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= '0' && szoveg[i] <= '9')
		{
			darab++;
		}
	}
	Console.WriteLine(darab);

	// hány %-a szám a teljes szövegnek, 2 tizedesre kerekítve
	int osszKarakter = szoveg.Length;
	int osszSzamKarakter = darab;
	double szazalek = (Convert.ToDouble(osszSzamKarakter) / (double)osszKarakter) * 100;
	Console.WriteLine(Math.Round(szazalek, 2));

	// van-e benne kisbetű
	bool vanE = false;
	int index = 0;
	while (vanE == false && index < szoveg.Length)
	{
		if (szoveg[index] >= 'a' && szoveg[index] <= 'z')
		{
			vanE = true;
		}
		index++;
	}
	Console.WriteLine((vanE ? "Van" : "Nincs") + " benne");

	// van-e benne /-jel
	vanE = false;
	index = 0;
	while (vanE == false && index < szoveg.Length)
	{
		if (szoveg[index] == '/') vanE = true;
		index++;
	}
	//for (int i = 0; vanE == false && i < szoveg.Length; i++) if (szoveg[i] == '/') vanE = true;
	Console.WriteLine((vanE ? "Van" : "Nincs") + " benne");


	// írassa ki a szöveget. Viszont, ha van benne nagybetű azt írja kisbetűssé
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= 'A' && szoveg[i] <= 'Z')
		{
			int aKisbetusAsciiKodja = szoveg[i] + 32;
			Console.Write((char)aKisbetusAsciiKodja);
		}
		else
		{
			Console.Write(szoveg[i]);
		}
	}
}
```