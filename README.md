```c#
static void Main(string[] args)
{
	/*
	 Kiválasztás tétele: Eldöntés tételére épül, azaz egy feltételnek megfelelő elem találata esetén, ki kell lépnie a ciklusból, viszont vissza kell adnia a találat indexét

	 Min/Max kiv. tétele: Rendezetlen elemek (szám, karakter, szöveg) közül kiváűlasztjuk a legnagyobbat vagy a legkisebbet.
	 */

	// Állítson elő 10 egész számot tartalmazó vektort.
	// Elemeit [-50, 50] -ban töltse fel.
	int[] tomb = new int[10];
	Random r = new Random();
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50;
	}
	// Írjuk ki az első pozitív szám értékét és indexét, ha van ilyen! 
	int index = -1;
	for (int i = 0; index==-1 && i < tomb.Length; i++)
	{
		if (tomb[i] >= 0)
		{
			index = i;
		}
	}
	if (index == -1)
	{
		Console.WriteLine("nincs benne pozitív szám");
	}
	else
	{
		Console.WriteLine($"van benne pozitív szám. {index+1}.");
		Console.WriteLine($"tömb indexeditk eleme: {tomb[index]}");
	}

	// Az előző feladatban elkészített vektorban keresse meg a legnagyobb értéket.
	int maxErtekIndexe = 0;
	for (int i = 1; i < tomb.Length; i++)
	{
		if (tomb[i] > tomb[maxErtekIndexe])
		{
			maxErtekIndexe = i;
		}
	}
	Console.WriteLine($"maximum értéke a tömbnek {tomb[maxErtekIndexe]}");
	Console.WriteLine($"maximum értéke a tömbnek {maxErtekIndexe+1}. eleme");

	//Állítson elő N elemű vektort. Elemeit [-10, 10] -ban töltse fel majd írja ki a képernyőre egy sorban! Az N értékét a felhasználótól kérje be!
	Console.WriteLine("ad meg milyen hosszú legyen ");
	int[] n = new int[Convert.ToInt32(Console.ReadLine())];
	for (int i = 0; i < n.Length; i++)
	{
		n[i] = r.Next(21) - 10;
		Console.Write($"{n[i],-5}");
	}
	// a.) Páros vagy páratlan számból van több?
	int paros = 0;
	int paratlan = 0;
	for (int i = 0; i < n.Length; i++)
	{
		if (n[i]%2==0)
		{
			paros++;
		}
		else
		{
			paratlan++;
		}
	}
	if (paros > paratlan) Console.WriteLine("a parosbol tobb van");
	else if (paros < paratlan) Console.WriteLine("a paratlanbol van tobb");
	else Console.WriteLine("a két szam egyenlo");

	Console.ReadKey();

}
```