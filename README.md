```c#
//random
Random random = new Random();
int sz1 = random.Next(10); // [0,9]
int sz2 = random.Next(9) + 1; // [1,9]
//  [2,10]
int sz3 = random.Next(9) + 2;
// [5,10]
int sz4 = random.Next(6)+5;
// [-3,3]
int sz5 = random.Next(7) - 3;
// [-10,2]
int sz6 = random.Next(13)-10;
// [-20, -10]
int sz7 = random.Next(11) - 20;
// [-30,-15]
int sz8 = random.Next(16) - 30;

// generáljunk 3 random számot [-100, 50], írjuk ki az eredményüket
Random random1 = new Random();
int sz9 = random1.Next(151)-100;
int sz10 = random1.Next(151) - 100;
int sz11 = random1.Next(151) - 100;
Console.WriteLine($"{sz9} {sz10} {sz11}");

// hány páros szám van
int paros = 0;
if(sz9 % 2 == 0) paros = paros + 1;
if (sz10 % 2 == 0) paros = paros + 1;
if (sz11 % 2 == 0) paros = paros + 1;
Console.WriteLine($"páros: {paros}");

//páratlanokat számolja:
//Console.WriteLine(((sz9%2)<0?(sz9%2)*-1:(sz9%2))+((sz10%2)<0?(sz10%2)*-1:(sz10%2))+((sz11%2)<0?(sz11%2)*-1:(sz11%2)));

// hány darab páratlan szám van
int paratlan = 0;
if (sz9  %  2  != 0 ) paratlan = paratlan + 1;
if (sz10 %  2 != 0)  paratlan = paratlan + 1;
if (sz11 %  2 != 0) paratlan = paratlan + 1;
Console.WriteLine($"paratlan:: {paratlan}");

// mennyi a pozitív és a negatív
int pozitiv = 0;
int negativ = 0;
if (sz9 < 0) negativ = negativ + 1;
else pozitiv = pozitiv + 1;
if (sz10 < 0) negativ = negativ + 1;
else pozitiv = pozitiv + 1;
if (sz11 < 0) negativ = negativ + 1;
else pozitiv = pozitiv + 1;
Console.WriteLine($"negatív: {negativ} pozitív: {pozitiv}");

// mennyi a számok átlaga
double atlag = Convert.ToDouble(sz9 + sz10 + sz11) / 3.0;
Console.WriteLine($"Átlag: {Math.Round(atlag,3)}");

//sz10 értékét cseréld meg sz11-el
Console.WriteLine($"{sz10} {sz11}");
int temp = sz10;
sz10 = sz11;
sz11 = temp;
Console.WriteLine($"{sz10} {sz11}");

// növekvő sorrendbe a 3 változót cserélgetsd át
Console.WriteLine($"{sz9} {sz10} {sz11}");

if (sz9 > sz10)
{
	int temp2 = sz9;
	sz9 = sz10;
	sz10 = temp2;
}
if (sz9 > sz11)
{
	int temp2 = sz9;
	sz9 = sz11;
	sz11 = temp2;
}
if (sz10 > sz11)
{
	int temp2 = sz10;
	sz10 = sz11;
	sz11 = temp2;
}
Console.WriteLine($"A számok sorrendbe: {sz9} {sz10} {sz11}");



// while,
// ??? elöl tesztelős ciklus
// csak akkor fog lefutni, ha a feltététel igaz, és addig futni AMÍG a felétel igaz
int szam = 6;
if (szam < 20)
{
	Console.WriteLine("lefutott a kód");
}

while (szam < 20)
{
	Console.WriteLine("lefutott a kód");
}

// hátul tesztelős ciklus
// 1x mindenképpen lefut! Amikor lefutott 1x akkor nézi meg a feltételt hogy mi is az

do
{
	Console.WriteLine("lefutott a kód");
} while (szam<5);

Console.ReadKey();
```