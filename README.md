#CalculatorV1.6
Vad beträffar design paterns så tyckte jag inte någon av dem var nödvändiga till min kalkylator då den är relativt enkel och ej innehåller några klasser som verkar vara designpatterns främsta syfte. Klasser och större projekt.

Jag har till en början använt mig av en using static System.Console för att göra koden renare.

Kalkylatorns meny består av 3 val, dvs:

Kalkylator
Kalkylator
Tidigare Resultat
Avsluta Programet
Användarens val deklareras i en string döpt category. Sedan har jag implementerat en enkel while loop vars syfte är att köra menyn tills ett val görs av användaren. Om användaren väljer Meny val 3 kommer programmet att avslutas.

I while loppen har jag placerat en switch case för att hantera användarens val. Case1 är Kalkylatorn.

När användaren tryckt 1 följt av Enter kommer man in i Kalkylatorn där användaren ombes att skriva in en uträkning. Det ser ut som följer:

Kalkylatorn
Skriv in en valfri beräkning, t.ex 4,6*3,2:

Case1 börjar med att deklarera bokstaven "y" till variabeln char more. Efter det kommer yterliggare en while loop som ska fråga användaren efter varje uträkning om hen vill göra en ny uträkning eller gå tillbaka till menyn.

Användarens input deklareras i en sträng som prövas i en if sats för att bestämma vad användaren valde för operatör. Om användaren valde till exempel operarören gånger ska följande hända:

Med hjälp av en indexOf deklareras gångeroperatören till int timesIndex, sedan kan vi med hjälp av en metod konvertera talet innan och efter gångeropertören till en sträng.

En try catch metod implementeras för att fånga upp eventuella felskrivningar av användaren, till exempel en bokstav istället för siffra. Metoden Exception e är implementerad

Strängarna konverteras om med hjälp av en Parse till doubles för att kunna hantera tal med kommatecken. Summan räknas ut av uträkningen och sparas till en double som representrerar resultatet. Efter det skrivs resultat med uträkningen ut till användaren.

Uträkningen och resultatet konverteras om med hjälp av metoden toString för att kunna sparas till listan som är sträng baserad. Det sista som händer innan nästa if satst är en Console.Clear som rensar tidigare information från terminalfönstret.

De andra beräkningarna fungerar på samma sätt med undantag för dividerat uträkningen där jag har implementerat en extra if metod för att fånga upp så användaren inte försökar dela siffran till höger om / med 0.

När användaren känner sig klar med sina uträkningar kan hen välja att skriva in 'n' följt av Enter för att komma tillbaka till menyn.

Kalkylator
Kalkylator
Tidigare Resultat
Avsluta Programet
Nu kan användaren välja alternativ nummer 2 för att se tidigare resultat och uträkningar. När användaren trycker 2 följt av Enter kommer hen in i case2 av switch casen.

Case2 inleder med en Console.Clear för att snygga till skärmen och skriver sedan ut följande med WriteLine:

Tidigare Resultat ---------------------.

Därefter kommer uträkningarna. Listan hämtas med en foreach loop för att på ett enkelt sätt skriva ut hela listan på en gång. Användaren uppmans därefter att Trycka Enter för att komma tillbaka till menyn. Case2 avslutas med en Console.Clear för att bara visa menyn igen.

Kalkylator
Kalkylator
Tidigare Resultat
Avsluta Programet
Nu kan användaren välja alernativ nummer 3 för att avsluta programet och det innebär att vi kommer in i case3 där följande händer: Användaren kommer att uppmanas om att Programmet kommer att avslutas, Tryck Enter för att bekräfta. Därefter inväntas användarens input med en Console.ReadKey. Programet avslutas med hjälp av en Enviroment.Exit och där case3 också breakar.

En Deafualt är också inlagd som ska meddela använadren om den gjort ett ogltigt val, till exempel skrivit en bokstav istället för en siffra mellan 1-3.
