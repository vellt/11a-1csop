```c#
static void Main(string[] args)
{
	matrixIsm();
	feladat1();
	feladat2();
	Console.ReadKey();
}

private static void feladat2()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a vasutipar rekordjait. Keszul az 1000 km/h-s vonat.";
	// mennyi db betű van benne (kis/nagybetű)
	// mennyi db magánhangzó van benne
	// mennyi db mondatból áll
	// mennyi db szám van benne
	// hány %-a szám a teljes szövegnek, 2 tizedesre kerekítve
	// van-e benne kisbetű
	// van-e benne /-jel
	// írassa ki a szöveget. Viszont, ha van benne nagybetű azt írja kisbetűssé

	// mennyi db betű van benne (kis/nagybetű)
	int betuDarab = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if((szoveg[i]>='A' && szoveg[i]<='Z') || (szoveg[i]>='a' && szoveg[i] <= 'z'))
		{
			betuDarab++;
		}
	}
	Console.WriteLine(betuDarab);

	// mennyi db magánhangzó van benne
	int maganhangzoDb = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if(
			szoveg[i]=='a' || szoveg[i]=='e' || szoveg[i]=='i' || szoveg[i]=='o' || szoveg[i] == 'u' ||
		   szoveg[i] == 'A' || szoveg[i] == 'E' || szoveg[i] == 'I' || szoveg[i] == 'O' || szoveg[i] == 'U'
		)
		{
			maganhangzoDb++;
		}
	}
	Console.WriteLine(maganhangzoDb);

	// mennyi db mondatból áll
	int pontSzamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == '.') pontSzamlalo++;
	}
	Console.WriteLine(pontSzamlalo);
}

private static void feladat1()
{
	// 2 csoport vett részt a tanulói versenyen. mindegyik csoport 10 főből áll
	// mindegyik tanunló [1,10]-ban kapott pontot.
	Random r = new Random();
	int[,] csapatok = new int[2, 10];
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			csapatok[i, j] = r.Next(10)+1; // i. csoport j. tanulója kapott pontot
		}
	}
	// minden tanuló kapott valamilyen pontot
	// feladatrészek:

	// melyik csoport szerzett több pontot (összegzés)
	int elsoSorOsszeg = 0;
	int masodikSorOsszeg = 0;
	for (int i = 0; i < csapatok.GetLength(1); i++)
	{
		elsoSorOsszeg += csapatok[0, i];
		masodikSorOsszeg += csapatok[1, i];
	}
	if (elsoSorOsszeg > masodikSorOsszeg)
	{
		Console.WriteLine("elso nyert");
	}
	else if(masodikSorOsszeg > elsoSorOsszeg)
	{
		Console.WriteLine("a második nyert");
	}
	else
	{
		Console.WriteLine("döntetlen");
	}

	// mennyi tanuló szerzett az 1. csoportból 1 pontot (megszámlálás)
	int szamlalo = 0;
	for (int i = 0; i < csapatok.GetLength(1); i++)
	{
		if (csapatok[0, i] == 1) szamlalo++;
	}
	Console.WriteLine(szamlalo);

	// VAN-e a kettes csoportban aki 10 pontot szerzett (eldöntés tétele)
	bool vanE = false;
	int index = 0;
	while (vanE==false && index<csapatok.GetLength(1))
	{
		if(csapatok[1,index]==10)
		{
			vanE = true;
		}
		index++;
	}
	for(int i = 0; vanE == false && index < csapatok.GetLength(1); i++) if (csapatok[1, index] == 10) vanE = true;
	Console.WriteLine(vanE ? "van" : "nincs" + " benne");
}

private static void matrixIsm()
{
	int[,] matrix = new int[3, 4];
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10); // [0,9]
		}
	}
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.Write($"{matrix[i, j]} ");
		}
		Console.WriteLine();
	}
}
```