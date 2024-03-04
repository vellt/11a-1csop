```c#
static void Main(string[] args)
{
	feladatBefejezese();
	programozasiTetelek();
	matrixFeladat();
	Console.ReadKey();
}

private static void matrixFeladat()
{
	string[] csapat = new string[]
	{
		"Real Madrid",
		"FC Barca",
		"Manchester City",
		"Manchester United",
		"FRADI"
	};
	// 5 csapat, 10 meccs
	// 0-->vesztett, 1-->döntetlen, 2-->nyert
	// vesztett-->0pont
	// döntetlen-->1pont
	// nyert-->3pont
	Random r = new Random();
	int[,] csapatok = new int[5, 10];
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			csapatok[i, j] = r.Next(3);
			string eredmeny = "";
			switch (csapatok[i,j])
			{
				case 0: eredmeny = "vesztett"; break;
				case 1: eredmeny = "döntetlen"; break;
				case 2: eredmeny = "nyert"; break;
			}
			Console.Write($"{eredmeny,12}");
		}
		Console.WriteLine();
	}
}

private static void programozasiTetelek()
{
	int[] tomb = new int[] { 1, 2, 3 };

	// összegzes
	int osszesen = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszesen += tomb[i];
	}
	Console.WriteLine(osszesen);

	// megszámlálás tétele
	int db = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] == 1) db++;
	}
	Console.WriteLine(db);

	// eldöntés tétele
	bool van = false;
	for (int i = 0; van==false  && i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");
}

private static void feladatBefejezese()
{
	/*
	 egy 14 fős csoportban AAF-ból a tanár minden hónapban egy röpdolgozatot írat
	eltelt 4 hónap. Mindenki kapott egy-egy jegyet [1,5]-ban minden dogára.
	 */

	int[,] osztaly = new int[14, 4];
	Random rand = new Random();
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osztaly[i, j] = rand.Next(5) + 1;
		}
	}
	string[] nevek = new string[]
	{
		"Bela", "Geza", "Kuba", "Beci", "Jeck", "Rezső", "Borat",
		"Zozo", "Huba", "Guba", "Emil", "csoki", "Dodó", "Gabi", 
	};
	// melyik tanulónak mennyi az átlaga
	double osszAtlag = 0;
	int haromEgesznelKisebb = 0;
	int jeles = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int osszJegyeEgyTanulonak = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszJegyeEgyTanulonak += osztaly[i, j];
		}
		double atlag = osszJegyeEgyTanulonak / (double)osztaly.GetLength(1); // 4 jegye van
		osszAtlag += atlag;
		if (atlag < 3) haromEgesznelKisebb++;
		if (atlag >= 4.6) jeles++;
		Console.WriteLine($"{nevek[i]} átlaga: {atlag:0.00}");
	}
	// mennyi az osztályátlag
	double osztalyatlag = osszAtlag / osztaly.GetLength(0);
	Console.WriteLine(Math.Round(osztalyatlag,2));

	// mennyi tanulónak van 3egésznél kisebb átlaga
	Console.WriteLine(haromEgesznelKisebb);

	// mennyi tanuló áll 5 - re(4.6 - tól)
	Console.WriteLine(jeles);

	// mennyi tanuló van az osztályátlag alatt
	int alat = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int osszJegyeEgyTanulonak = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszJegyeEgyTanulonak += osztaly[i, j];
		}
		double atlag = osszJegyeEgyTanulonak / (double)osztaly.GetLength(1); // 4 jegye van
		if (atlag<osztalyatlag)
		{
			alat++;
		}
	}
	Console.WriteLine($"A tanulok akik az osztályátlag allat van:{alat}");

	// Eldöntés tételeire épülő feladatok:
	// VAN-e olyan tanuló aki bukásra áll? (1.6 alatt)
	//double[] atlagok = new double[14];
	bool van = false;
	for (int i = 0; van==false && i < osztaly.GetLength(0); i++)
	{
		int osszJegyPerTanulo = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszJegyPerTanulo += osztaly[i, j];
		}
		double atlag = osszJegyPerTanulo / (double)osztaly.GetLength(1);
		if (atlag < 1.6)van= true;
		//atlagok[i] = atlag;
	}
	Console.WriteLine((van ? "van" : "nincs") + " benne bukott diák");

	// VAN-e olyan tanuló aki csak egyest szerzett a 4 hónap alatt
	van = false;
	for (int i = 0; van==false && i < osztaly.GetLength(0) ; i++)
	{
		int osszJegy = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszJegy += osztaly[i, j];
		}
		if (osszJegy == osztaly.GetLength(1)) van = true;
	}
	Console.WriteLine((van ? "van" : "nincs") + " benne olyan diák, aki csak 1-est szerzett");

	// VAN-e olyan tanuló akinek az első és az utolsó jegye ugyan az
	van = false;
	for (int i = 0; van==false && i < osztaly.GetLength(0); i++)
	{
		int elso = osztaly[i, 0];
		int utolso = osztaly[i, osztaly.GetLength(1)-1];
		if (elso == utolso) van = true;
	}
	Console.WriteLine((van?"van":"nincs")+ " benne olyan tanuló akinek az első és az utolsó jegye ugyan az");
}
```