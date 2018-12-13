Laddningstid
=======================

Uppgiften går ut på att analysera laddningstiden på 3 webbplatser.

Urval
-----------------------

Tänk att undersöka dessa 3 webbplatser:

* [Aftonbladet](https://www.aftonbladet.se/)

* [Dagens Nyheter](https://www.dn.se/)

* [The New York Times](https://www.nytimes.com/)

Jag använder samma sidor som förra gången för att få en bredare analys på webbplatserna.

Metod
-----------------------

Använder mig av [Google Pagespeed](https://developers.google.com/speed/pagespeed/insights/) och devtools network(firefox) för att sedan anteckna ner resultaten i ett excelark på google docs.
Alla mätningar med devtools är gjorda med Regular 3G och inaktiverad cache.

Resultat
-----------------------

Aftonbladet

[FIGURE src="image/Rapport/Aftonbladet/aftonbladet1.png?w=300&h=600&area=0,33,0,33"]

Förminskade bilden med 50% för att få lite mer av sidan med.

[Länk till excelark, sida 1](https://docs.google.com/spreadsheets/d/1aeW66J2taztQSrAj2n054B8l92Lh771WfJ5yCgfPKsU/edit?usp=sharing).

Dagens Nyheter

[FIGURE src="image/Rapport/Dagens Nyheter/dn1.png?w=300&h=600&area=0,33,0,33"]

[Länk till excelark, sida 2](https://docs.google.com/spreadsheets/d/1aeW66J2taztQSrAj2n054B8l92Lh771WfJ5yCgfPKsU/edit?usp=sharing)

The New York Times:

[FIGURE src="image/Rapport/The New York Times/times1.png?w=300&h=600&area=0,33,0,33"]

[Länk till excelark, sida 3](https://docs.google.com/spreadsheets/d/1aeW66J2taztQSrAj2n054B8l92Lh771WfJ5yCgfPKsU/edit?usp=sharing)


Analys
-----------------------

######Aftonbladets analys:
Av resultaten ser man direkt att aftonbladet fokuserar mer på att optimera sin desktop webbplats jämfört med sin mobil.
Hastigheten är mycket bättre på desktop, men det finns fortfarande förbättringar de kan göra.
Google Pagespeed ger dessa förbättringsmöjligheter för att göra inläsningen snabbare på både desktop och mobil:

* Infoga nödvändig JS-/CSS-kod direkt på sidan och skjut upp inläsningen av JS-kod/formatmallar som är mindre viktiga.

* Låt bilder utanför skärmen och dolda bilder läsas in med lat inläsning efter att alla viktiga resurser är inlästa så att tiden till interaktivt tillstånd minskar.

* Ta bort regler som inte används från formatmallarna, så att färre byte skickas via nätverket i onödan.

Sen för att förbättra flödet på sidan genom att minska på data som läses in ger Google Pagespeed dessa förslag.

* Minska storleken på DOM-trädet, det är rekommenderat att ha 1500 noder.

* Minska nätverksbelastningen för att förbättra inläsningen.

* Minska storleken på JS-resurser som skickas.

Det aftonbladet är bra på är att använda sig av minifierad CSS och JS, använder modernt bildformat, använder rätt storlek på sina bilder.

Deras load är ganska dålig, genomsnittet jag fick var 30.006s, kan vara för all belastning och onödig kod som läses in, det finns en hel del
reklam på sidan.


######Dagens Nyheter analys:
Av resultaten ser man att dagens nyheter fokuserar på båda sina webbplatser, desktop är fortfarande bättre en den mobila men man ser
att de i alla fall försöker optimera sin mobila webbplats också.
Google Pagespeed ger dessa förbättringsmöjligheter för att göra inläsningen snabbare:

* Ta bort regler som inte används från formatmallarna, så att färre byte skickas via nätverket i onödan.

* Använd modernt bildformat på sin mobila webbplats.

Sen för att förbättra flödet på sidan genom att minska på data som läses in ger Google Pagespeed dessa förslag.

* Minska storleken på DOM-trädet, det är rekommenderat att ha 1500 noder.

* Lagra cache i en längre tid, upprepade besök kommer då att gå snabbare.

* Använd funktionen font-display i CSS så att texten är synlig för användaren medan webbteckensnitten läses in.

Det dagens nyheter är bra på är att använda sig av minifierad CSS och JS, mindre nätverksbelastning, optimera sin kod.
Deras load är riktigt bra, genomsnittet var 5.43s, vilket tyder på att sidan inte läser in en massa onödig kod utan prioriterar rätt.  


######The New York Times analys:
Resultaten visar att the new york times inte fokuserar på sin mobila webbplats alls och deras desktop är helt okej.
Google Pagespeed ger dessa förbättringsmöjligheter för att göra inläsningen snabbare:

* Infoga nödvändig JS-/CSS-kod direkt på sidan och skjut upp inläsningen av JS-kod/formatmallar som är mindre viktiga.

* Använda rätt storlek på sina bilder.

* Låt bilder utanför skärmen och dolda bilder läsas in med lat inläsning efter att alla viktiga resurser är inlästa så att tiden till interaktivt tillstånd minskar.

Sen för att förbättra flödet på sidan genom att minska på data som läses in ger Google Pagespeed dessa förslag.

* Minska storleken på DOM-trädet, det är rekommenderat att ha 1500 noder.

* Lagra cache i en längre tid, upprepade besök kommer då att gå snabbare.

* Minska nätverksbelastningen för att förbättra inläsningen.

* Minska storleken på JS-resurser som skickas.

* Minska orderkedjor vilket förbättrar sidinläsningstiden.

Det the new york times är bra på är att använda sig av minifierad CSS och JS, tar bort regler som inte används från formatmallarna, använder modernt bildformat.
Deras load är ganska dålig, genomsnittet jag fick var 29.186s, kan vara för all belastning och onödig kod som läses in, ovanligt långa orderkedjor.

######Sammanfattning:
Det här är min rangordning av sidorna baserat på mina resultat.

1. Dagens Nyheter

2. Aftonbladet

3. The New York Times

Dagens nyheter vinner helt klart, de optimera både sin desktop och mobila webbplats, deras load är riktigt snabb även fast jag
använde mig av Regular 3G. Mindre onödig kod som läses in, mindre reklam på sidan. De sparar på en hel del data genom att optimera
nätverksbelastning. Hade helt klart den bästa mobila webbplatsen, finns fortfarande en hel del saker som kan förbättras.
Man märker att dagens nyheter är en mer modernare sida än de andra både på design och optimerad kod.

Aftonbladet tar en andra plats, deras desktop sida var den snabbaste av alla 3, deras mobila webbplats är helt okej,
de använder bara 4 orderkedjor vilket är riktigt bra om man jämför med de andra webbplatserna.
De optimerar på ett konstigt sätt, verkar inte vara samma på både desktop och mobil t.ex. på sin mobila så optimerar de nätverksbelastning
medan på desktop gör de inte det.

The new york times får en tredje plats, de verkar inte optimera speciellt mycket, de fokuserar inte något på sin mobila webbplats.
Har väldigt långa orderkedjor, läser in en hel del onödig kod vilket leder till den slöa load time. Verkar som de endast använder väldigt
basic metoder för att optimera kod.

Min gräns för laddningstid ligger nog runt mellan 1-2 sekunder, men det är för jag är så van med en snabb uppkoppling. Jag kan acceptera
att det tar lite längre ifall jag använder min mobil när jag är ute, då ligger det runt 4-5 sekunder.
Både aftonbladet och the new york times snabbhet var väldigt seg, kan vara för att jag använde Regular 3G, men tycker man får ett bättre
resultat då, för alla har inte tillgång till ett snabbt nätverk.
Aftonbladet var den enda sidan som klarade min gräns, om jag var ute och använde ett fritt nät.

Referenser
-----------------------

-

Övrigt
-----------------------

Habib Achouri
