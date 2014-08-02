Prerekvizity
-------------
- operacni system Linux
- prekladac g++
- nainstalovana nejnovejsi verze knihovny OpenCV

Instalace
---------
- preklad pomoci Makefile v adresari src

Spusteni
--------

SYNOPSE
    dis -i jmeno -o jmeno [volby]

VOLBY
    -i jmeno
        jmeno vstupniho videa

    -o jmeno
        jmeno vystupniho videa

    -s stabilizator
        nastavi metodu stabilizace. Dostupne metody jsou:

        gcbpm (vychozi)
        svd

    -m metoda
        nastavi typ vystupniho videa. Dostupne metody jsou:

        raw (vychozi)
            velikost snimku vstupniho a vystupniho videa je stejna
        intersection
            velikost snimku vystupniho videa odpovida pruniku vsech snimku
        union
            zobrazeny jsou vsechny snimky, tudiz je velikost snimku
            vystupniho videa vetsi

    -l
        pokud byla zvolena metoda 'union' (viz volbu -m), kazdy snimek 
        je ponechan ve vystupnim videu, tedy nove snimky jsou zobrazeny 
        na stare.

VOLBY relevantni pro stabilizator 'gcbpm'
    -b bit
        nastavi n-ty bit pro pouziti pri vypoctu bitovych ploch. Povolene 
        hodnoty: 0-8 (vychozi hodnota: 5).

	-N velikost
        nastavi velikost okna pro porovnani (ctvercove okno velikost 
        x velikost) v pixelech. Vyssi hodnota zapricini vyssi kvalitu 
        stabilizace ale delsi beh. Pokud je nastavena hodnota prilis 
        vysoka, bude automaticky dopocitana nejvyssi mozna vyssi.

    -f offset
        nastavi offset (v x i y souradnici), v jehoz ramci se bude 
        pohybovat okno pro vyhledavani. Vyssi hodnota zapricini vyssi 
        kvalitu stabilizace ale delsi beh. Pokud je nastavena hodnota 
        prilis vysoka, bude automaticky dopocitana nejvyssi mozna vyssi.

    -x podoblasti
        nastavi pocet podoblasti v ose x pro hledani vektoru lokalniho 
        posunu (vychozi hodnota: 2).

    -y podoblasti
        nastavi pocet podoblasti v ose y pro hledani vektoru lokalniho 
        posunu (vychozi hodnota: 2).

    -d utlum
        nastavi utlumeni predchoziho vektoru globalniho posunu. Vyssi 
        hodnota zajisti lepsi stabilizaci, ale vysledny snimek s vyssi 
        pravdepodobnosti kvuli akumulaci chyb 'opusti' okno. Povolene 
        hodnoty (float): 0-1 (vychozi hodnota: 0,95)
        
VOLBY relevantni pro stabilizator 'svd'
	-c body
		nastavi pocet vyznamnych bodu pro sledovani.
