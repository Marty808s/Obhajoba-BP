Dobrý den,
## Prezentace

https://docs.google.com/presentation/d/108lD9QLEOLYTmkGzEE6CVeS0kzcP_7S8qDQNcDX0udY/edit?slide=id.g37ddd258d3e_0_65#slide=id.g37ddd258d3e_0_65

## Úvod
moje jméno je Martin Vlnas a rád bych Vám představil svojí bakalářskou práci, která nese název Návrh a implementace klientské části aplikace InternHub

## Motivace a cíl
Motivací této práce je společný výstup týmového projektu, kterou je aplikace InternHub.
Tato aplikace má za úkol modernizovat a digitalizovat administrativně náročný proces organizace studentských praxí.

Cílem má práce je návrh a implementace uživatelsky přívětivě klientské části společně s zajištěním její technické funkčnosti a optimalizování uživatelského zážitku

## Teoretická východiska

Mímy teoretickými východisky byly

1. Principy zvolencýh technologíí společně s jejich základními přístupy
 přesněji se jednalo o:
	Nástoj Figma, který slouží k návrhu a prototypování klientských částí systému a aplikaci
	diagrams.net - nástroj pro tvorbu diagramů a schémat, které jsem využil ve své práci
	knihovna React pro samotnou realizaci
	Framework Tailwind CSS, který jsem využil pro stylování
	A další knihovny - Axios - pro komunikaci s BE a React Icons a Material Icons (pro ikony v UI)
	
2. Druhým východiskem byly zpracované požadavky aplikace
	- ta byla důležitá pro návrh celé klientské části

3. a třetím východiskem pro mne byla architektira aplikace InternHub
	- která mi posloužila primárně pro komunikaci FE s BE (api dokumentace), přihlášení uživatele
		
## Metodika BP
1. Jako první jsem iterativně prováděl návrh klientské části pomocí jednotlivých druhů wireframe modelů, které jsem průběžně specifikoval a upravoval - po dokončení jsem následně navázal vytvořením interaktivního prototypu.
2. Po úspěšném návrhu jsem v React aplikaci vytvořil svoje stavební prvky, které jsem využíval v další části realizace
3. Následně jsem začal vytvářet komplexnější části UI, které jsem seskupoval do jednotlivých stránek webové aplikace.
4. Po realizaci jsem provedl testování použitelnosti na třech skupinách uživatelů z pohledu systému - jednalo se o  studenty, správce organizace a správce katedry. To byly z důvodu absence BE a všechn funkčních části systému prováděné pouze na prototypu návrhu.
	- celý průběh testování jsem připravil dle metodiky ISTQB
	- použil jsem metodiku think-aloud abych mohl zpracovat pocity a myšlenkové pochody testovaných subjektů
	- využil jsem moderovanou a nemoderovanou formu dle geologické polohy
	- z jednotlivých realací vznikaly záznamy obrazovky i s audio záznamem pro případné zpětné zpracování
	- následně jsem výstupy z testování analyzoval a kategorizoval
5. Po testování použitelnosti jsem jednotlivé poznatky s ohledem na jejich kategorii implementoval přímo v React aplikaci.

## Výsledky

## Diskuze
Z pohledu cílu byla většina splněna.
Z pohledu testování byla převážně pozitivní zpětná vazba (krom role správce katedry)
Získané připomínky jsou z většiny zpracovány
Frontend je napojen na dostupné Backendové části, ale zatím není aplikace určitě ve stavu, kdy by mohla být nasazena

Při vypracování praktické části jsem čelil spoustu překážkám, které byly jak neúplné požadavky, které omezily jak můj návrh, tak výslednou aplikaci z pohledu klientské části
Zároveň nemohla proběhnou úplná realizace, protože stále chybý části backend, bez kterých nelze vytvořit funkční klientskou část - proto jsem tedy ke konci přešel na statickou reprezentaci.

Systém obsahuje chybějící funkce:
	- které mají připravené UI prvky a handle funkce, které je potřeba dodefinovat
	- nějaké funkce z pohledu klientské části jsou realizovaný staticky pomocí slovníku, které se vrací pomocí vytvořených endpointů (zde bude potřeba napojit přímo na BE)
	- chybějící funkce jsou vyznačený v kódu formou komentářů a alert dialogu, který jsem dával tam, kde chybí jednotlivé API
	
# Odpovědi
## Vedoucí práce:

1. Na obrázku 3.8 je uveden tzv. User Flow diagram. Jaký je rozdíl mezi tímto
diagramem a diagramem aktivit v jazyce UML? V čem se liší jejich vyjadřovací schopnosti?

### User Flow diagram
Vyjadřuje cestu uživatele rozhraním aplikace/systému k dokončení nějakého tasku/úkolu. Nemá tak bohatou notaci. Jedná se o neformální nástroj, který se běžně používá v UX/UI návrhu. Popisuje interakce uživatele s rozhraním systému.

### Diagram aktivit
Diagram popisuje sled událostí buď z pohledu systému, nebo z pohledu uživatele - zaměřuje se na procesní logiku. Má rozsáhlejší notaci, takže umožňuje paralelní běh aktivit a jejich synchronizaci.

2. Jaké kroky bude nutné provést, aby mohl případný řešitel backendové části plynule
napojit svou backendovou část na Vámi vytvořený frontend? Popište technologický
postup.

Prvním krokem bude identifikace chybějících částí:  
- pomocí průchodu aktuální verzí systému, kde je buď popis přímo na klientské části (warning dialog/text na FE)  
- průchodem jednotlivých *pages* v projektové složce, kde jsou předpřipravené obslužné funkce se zakomentovaným nefunkčním/dummy API requestem z FE  

### Další kroky
- **Zkontrolovat jednotlivá API volání** v kódu a pročíst přiložené komentáře, kde je popsáno, která volání chybí nebo jsou pouze dummy.  
- **Doplnit API požadavky na backend** dle aktuálně realizované části a dostupné verze Swaggeru, která je v rámci projektu k dispozici.  
- **Ověřit správné volání** ve složce `api/` a zkontrolovat jejich využití v jednotlivých obslužných funkcích.  
- **Nastavit správné datové modely**, aby odpovídaly definicím ve Swaggeru a frontend dokázal s daty pracovat bez úprav.  
- **Provést integrační testy** – ověřit, že se frontendové komponenty správně napojují na backend, API vrací očekávané odpovědi.  
- **Zdokumentovat propojení** – aktualizovat Swagger dle nových endpointů a doplnit stručný návod pro vývojáře backendu.  

## Oponent

1. Jakou podporu aplikace poskytuje (resp. by měla poskytovat) pro podporu
dokumentů spojených s organizací a hodnocením praxí?

Aplikace by měla poskytovat:  
- **Automatické generování dokumentů** dle existující předlohy (např. pomocí knihovny *pydoc* nebo její obdoby). Dokumenty se vytvoří v okamžiku schválení přihlášky a uloží se do úložiště backendu pod cizím klíčem studenta a praxe.  
- **Evidenci cest k dokumentům** – odkaz (cesta) na každý vytvořený dokument se uloží do databáze, aby bylo možné dokumenty snadno zpětně dohledat.  
- **Zjednodušené verzování** – dokumenty se při změně přepisují v úložišti, není nutné držet vícero historických verzí.  
- **Řízení přístupu** – dokumenty jsou dostupné jen přihlášeným účastníkům, a to na základě jejich rolí a oprávnění definovaných ve workflow aplikace.  
- **Uživatelskou práci s dokumenty** – možnost dokumenty z frontendu stáhnout a v případě potřeby i znovu nahrát („přenahrát“).  



 