```c#
static void Main(string[] args)
{
	folytatas();
	folyamatabra();
	Console.ReadKey();
}

private static void folyamatabra()
{
	string[] tomb = { "sapka", "kalap", "kabat" };
	// van-e benne 'k' betűvel kezdődő?
	bool van = false;
	for (int i = 0; van==false && i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		if (szoveg[0] == 'k') van = true;
	}
	Console.WriteLine((van ? "van" : "nincs") + " benne k kezdőbetűs szöveg");
}

private static void folytatas()
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
			switch (csapatok[i, j])
			{
				case 0: eredmeny = "vesztett"; break;
				case 1: eredmeny = "döntetlen"; break;
				case 2: eredmeny = "nyert"; break;
			}
			Console.Write($"{eredmeny,12}");
		}
		Console.WriteLine();
	}

	// melyik csapatnak mennyi pontja van?
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		int osszpont = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			osszpont += csapatok[i, j];
			if (csapatok[i, j] == 2) osszpont++;
		}
		Console.WriteLine($"{csapat[i]} {osszpont}");
	}

	// hányszor játszott döntetlent a FRADI
	int fradiIndex = -1;
	for (int i = 0; i < csapat.Length; i++)
	{
		if (csapat[i] == "FRADI") fradiIndex = i;
	}

	if (fradiIndex == -1)
	{
		Console.WriteLine("Nincs FRADI csapat!");
	}
	else
	{
		int dontetlenSzamlalo = 0;
		for (int i = 0; i < csapatok.GetLength(1); i++)
		{
			if(csapatok[fradiIndex, i] == 1)
			{
				dontetlenSzamlalo++;
			}
		}
		Console.WriteLine($"A FRADI {dontetlenSzamlalo}x játszott döntetlent");
	}

	// VOLT-e olyan csapat aki legalább 3 győzelme volt
	bool van = false;
	for (int i = 0; van==false && i < csapatok.GetLength(0); i++)
	{
		int gyozelemSzamlalo = 0;
		for (int j = 0; van==false && j < csapatok.GetLength(1); j++)
		{
			if (csapatok[i, j] == 2) gyozelemSzamlalo++;
			if (gyozelemSzamlalo == 3) van = true;
		}
	}
	Console.WriteLine(van ? "van" : "nincs");

	// mennyi csoportkör átlag pontszáma:
	int csoportpont = 0;
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		int osszpont = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			osszpont += csapatok[i, j];
			if (csapatok[i, j] == 2) osszpont++;
		}
		csoportpont += osszpont;
	}
	double atlag = csoportpont / (double)csapatok.GetLength(0);
	Console.WriteLine(Math.Round(atlag,2));
}
```