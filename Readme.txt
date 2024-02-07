Prediktivní model se skládá z následujících kroků:
1. generator2 má za úkol sestavení trénovacích/testovacích dat v podobě csv souboru časové řady (test_data.csv)

2. data_analysis2 analyzuje vygenerované csv a provádí základí analýzy souboru a časové řady, 
zda je vhodná pro použití k trénování. Kroků analýzy jde samozřejmě provést mnohem víc, 
ale je to aspoň výběr těch nejzákladnějších, které by se měly provést nad vstupními daty, 
než je pustíme do neuronové sítě - pokud nejsou vstupní data OK tak bychom trénovali síť zbytečně.

3. LSTM4 je samotný prediktivní model. Jedná se o rekurentní neuronovou síť typu LSTM 
(Long Short Term Memory) která by měla být vhodná pro predikce časových řad. 
Typů co se dá pro tento druh predikce vyzkoušet je více, 
já začal tímto a její principy mi dávají největší teoretický smysl, 
ale stálo by za porovnání vyzkoušet typů NN více a zjistit na jaký typ predikce se který hodí více.

4. LSTM4_optimization je optimalizační model, který má za úkol pomoct vybrat 
nejvhodnější hyperparametry prediktivního modelu. Zjednodušeně obsahuje prediktivní model a pak 
pomocí X set iterací testuje různá nastavení parametrů sítě a zaznamenává jaký byl výsledek. 
Výstupem pak jsou hyperparametry nejúspěšnější iterace kterou za celý běh provedl. 
Tyto parametry je pak vhodné použít v samotném modelu. 
Nevýhodou je, že tato optimalizace na běžném notebooku běží několik hodin.
