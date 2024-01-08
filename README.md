```c#
// printeljük ki, mit látunk?
int sz1 = 65;
int sz2 = 76;
int sz3 = 77;
int sz4 = 65;
Console.WriteLine($"{sz1} {sz2} {sz3} {sz4}");

// és most?
Console.WriteLine($"{(char)sz1} {(char)sz2} {(char)sz3} {(char)sz4}");

// az 'A' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
char karakter = 'A';
Console.WriteLine((int)karakter); // 65
// az 'a' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
Console.WriteLine((int)'a'); // 97
// az 'B' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
Console.WriteLine((int)'B'); // 66
// az 'b' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
Console.WriteLine((int)'b'); // 98

// x, y, z alakítsuk nagybetűssé
Console.WriteLine($"(x, y, z)=>({(char)('x'-32)}, {(char)('y'-32)}, {(char)('z'-32)})");

// nem mindegy a konstanst hogyan írjuk, meglehet nézni, hogy mi van akkor ha a szám körül
// "" van vagy '' vagy pedig nincs semmi vagy pedig a szám után egy .0 van, ezek mind mást típust eredményeznek
Console.WriteLine(6.GetType()); // int
Console.WriteLine(6.0.GetType()); // double
Console.WriteLine('6'.GetType()); // char
Console.WriteLine("6".GetType()); // string

// A nagybetűs angolszász abc kiíratása (NAGYBETŰS)
for (int i = 65; i <= 90; i++)
{
	Console.Write($"{(char)i} ");
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott szöveg után tesz egy sortörést


// string, mint tömb----------------------------------------------------
string szoveg = "alma";
Console.WriteLine(szoveg[0]); //'a'
Console.WriteLine(szoveg.Length); //4
//Console.WriteLine(szoveg[4]); //-->error, túl hivatkozunk!
Console.WriteLine((int)szoveg[szoveg.Length-1]); //97

// kisbetűs-->nagybetűs
string beka = "beka";
for (int i = 0; i < beka.Length; i++)
{
	Console.Write((char)(beka[i]-32));
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott szöveg után tesz egy sortörést

// minden második karaktert írassunk ki
for (int i = 0; i < beka.Length; i+=2)
{
	Console.Write(beka[i]);
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott szöveg után tesz egy sortörést


// írjuk ki az 5. elemtől a beka szót, (persze hosszú szónak kell lennie)
for (int i = 5; i < beka.Length; i++)
{
	Console.Write(beka[i]);
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott szöveg után tesz egy sortörést


// forditott sorrend
Console.Write("szoveg: ");
string szov = Console.ReadLine();
for (int i = szov.Length-1; i >= 0; i--)
{
	Console.Write(szov[i]);
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott szöveg után tesz egy sortörést

// nézzük meg, hogy a bekért szöveg tartalmaz-e t betűt, ha igen mondjuk meg h mennyit
int szamlalo = 0;
for (int i = 0; i < szov.Length; i++)
{
	if (szov[i] == 't')
	{
		//szamlalo= szamlalo+1;
		//szamlalo+= 1;
		szamlalo++;
	}
}
Console.WriteLine($"Ennyi db t betű van a(z) {szov} szövegben: {szamlalo}");

// számoljuk meg, hogy a bekért szövegben mennyi magánhangzó van
int maganhangzo = 0;
for (int i = 0; i < szov.Length; i++)
{
	if(
		szov[i]=='a' || 
		szov[i]=='e' ||
		szov[i]=='i' ||
		szov[i]=='u' ||
		szov[i]=='o'
		)
	{
		// maganhangzo
		maganhangzo++;
	}
}
Console.WriteLine($"{maganhangzo} db maganhanzo van a(z) {szov} szoban");

// Az összes magánhangzót cseréljük i betűre
// pl kerekpar-->kirikpir
for (int i = 0; i < szov.Length; i++)
{
	if (
		szov[i] == 'a' ||
		szov[i] == 'e' ||
		szov[i] == 'u' ||
		szov[i] == 'o'
		)
	{
		// maganhangzo
		Console.Write("i");
	}
	else
	{
		Console.Write(szov[i]);
	}
}
Console.WriteLine();

// alakítsd át a neved nagybetűssé
string keresztnev = "benjamin";
for (int i = 0; i < keresztnev.Length; i = i + 1)
{
	Console.Write((char)(keresztnev[i] - 32)); // -32-el eltolva nagybetűset kapunk
}
Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést


Console.ReadKey();
```