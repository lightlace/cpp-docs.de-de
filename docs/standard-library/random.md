---
title: '&lt;random&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <random>
dev_langs: C++
helpviewer_keywords: random header
ms.assetid: 60afc25c-b162-4811-97c1-1b65398d4c57
caps.latest.revision: "58"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5bef9205fd583dd66a0f3cfe791ff95a861435c0
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="ltrandomgt"></a>&lt;random&gt;
Definiert Funktionen zum Generieren von Zufallszahlen und erlaubt die Erstellung gleichförmiger verteilter Zufallszahlen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <random>  
```  
  
## <a name="summary"></a>Zusammenfassung  
 Ein *Zufallszahlengenerator* ist ein Objekt, bei dem eine Sequenz von Pseudo-Zufallswerten erzeugt wird. Ein Generator, der Werte produziert, die in einem bestimmten Bereich gleichförmig verteilt sind, ist ein *Uniform Random Number Generator* (URNG, einheitlicher Zufallszahlengenerator). Auf eine Vorlagenklasse, die als URNG funktionieren soll, wird als *Modul* verwiesen, wenn die Klasse bestimmte gemeinsame Merkmale aufweist, die später in diesem Artikel diskutiert werden. Ein URNG kann mit einer *Verteilung* kombiniert werden – was im Normalfall auch geschieht –, indem der URNG als Argument an den `operator()` des Verteilers übergeben wird, um Werte zu produzieren, die in einer von der Verteilung definierten Art und Weise verteilt werden.  
  
 Diese Links führen zu den Hauptabschnitten dieses Artikels:  
  
- [Beispiele](#code)  
  
- [Kategorisierte Auflistung](#listing)  
  
- [Module und Verteilungen](#engdist)  
  
- [Hinweise](#comments)  
  
### <a name="quick-tips"></a>Einfache Tipps  
 Hier erhalten Sie einige Tipps, die Sie beachten sollten, wenn Sie `<random>` verwenden:  
  
-   Für die meisten Zwecke produzieren URNGs Rohbits, die durch Verteilungen geformt werden müssen. (Eine wichtige Ausnahme ist [std::shuffle()](../standard-library/algorithm-functions.md#shuffle), da es einen URNG direkt verwendet.)  
  
-   Eine einzelne Instanziierung eines URNG oder einer Verteilung kann nicht gleichzeitig sicher aufgerufen werden, da die Ausführung eines URNG oder einer Verteilung ein Änderungsvorgang ist. Weitere Informationen finden Sie unter [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md).  
  
- [Voreingestellte Typdefinitionen](#typedefs) einiger Module sind verfügbar. Dies ist der bevorzugte Weg zur Erstellung eines URNG, wenn ein Modul verwendet wird.  
  
-   Die hilfreichste Paarung für die meisten Anwendungen ist das `mt19937`-Modul mit `uniform_int_distribution`, wie später in diesem Artikel im [Codebeispiel](#code) gezeigt.  
  
 Der `<random>`-Header enthält mehrere Optionen zur Auswahl, von denen jede der veralteten C-Laufzeitfunktion `rand()` vorzuziehen ist. Informationen über die Nachteile von `rand()` und die Behebung dieser Schwachpunkte durch `<random>` erhalten Sie in [diesem Video](http://go.microsoft.com/fwlink/p/?linkid=397615).  
  
##  <a name="code"></a> Beispiele  
 Im folgenden Codebeispiel wird veranschaulicht, wie einige Zufallszahlen (in diesem Fall fünf) mit einem Generator erstellt werden, der mit einem nicht-deterministischen Startwert generiert wurde.  
  
```cpp  
#include <random>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    random_device rd;   // non-deterministic generator  
    mt19937 gen(rd());  // to seed mersenne twister.  
                        // replace the call to rd() with a  
                        // constant value to get repeatable  
                        // results.  
  
    for (int i = 0; i < 5; ++i) {  
        cout << gen() << " "; // print the raw output of the generator.  
    }  
    cout << endl;  
}  
```  
  
```Output  
2430338871 3531691818 2723770500 3252414483 3632920437  
```  
  
 Obwohl es sich dabei um hochwertige Zufallszahlen handelt und diese bei jeder einzelnen Ausführung dieses Programms unterschiedlich sind, liegen sie nicht unbedingt in einem nützlichen Bereich. Verwenden Sie zum Steuern des Bereichs eine gleichmäßige Verteilung, wie im folgenden Code dargestellt:  
  
```cpp  
#include <random>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    random_device rd;   // non-deterministic generator  
    mt19937 gen(rd());  // to seed mersenne twister.  
    uniform_int_distribution<> dist(1,6); // distribute results between 1 and 6 inclusive.  
  
    for (int i = 0; i < 5; ++i) {  
        cout << dist(gen) << " "; // pass the generator to the distribution.  
    }  
    cout << endl;  
}  
```  
  
```Output  
5 1 6 1 2  
```  
  
 Im nächsten Codebeispiel werden realistischere Anwendungsfälle mit gleichmäßig verteilten Zufallszahlengeneratoren dargestellt, die die Inhalte eines Vektors und eines Arrays mischen.  
  
```cpp  
// cl.exe /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <random>  
#include <string>  
#include <vector>  
#include <functional> // ref()  
  
using namespace std;  
  
template <typename C> void print(const C& c) {  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
template <class URNG>  
void test(URNG& urng) {  
  
    // Uniform distribution used with a vector  
    // Distribution is [-5, 5] inclusive  
    uniform_int_distribution<int> dist(-5, 5);  
    vector<int> v;  
  
    for (int i = 0; i < 20; ++i) {  
        v.push_back(dist(urng));  
    }  
  
    cout << "Randomized vector: ";  
    print(v);  
  
    // Shuffle an array   
    // (Notice that shuffle() takes a URNG, not a distribution)  
    array<string, 26> arr = { { "H", "He", "Li", "Be", "B", "C", "N", "O", "F",  
        "Ne", "Na", "Mg", "Al", "Si", "P", "S", "Cl", "Ar", "K", "Ca", "Sc",  
        "Ti", "V", "Cr", "Mn", "Fe" } };  
  
    shuffle(arr.begin(), arr.end(), urng);  
  
    cout << "Randomized array: ";  
    print(arr);  
    cout << "--" << endl;  
}  
  
int main()  
{  
    // First run: non-seedable, non-deterministic URNG random_device  
    // Slower but crypto-secure and non-repeatable.  
    random_device rd;  
    cout << "Using random_device URNG:" << endl;  
    test(rd);  
  
    // Second run: simple integer seed, repeatable results  
    cout << "Using constant-seed mersenne twister URNG:" << endl;  
    mt19937 engine1(12345);  
    test(engine1);  
  
    // Third run: random_device as a seed, different each run  
    // (Desirable for most purposes)  
    cout << "Using non-deterministic-seed mersenne twister URNG:" << endl;  
    mt19937 engine2(rd());  
    test(engine2);  
  
    // Fourth run: "warm-up" sequence as a seed, different each run  
    // (Advanced uses, allows more than 32 bits of randomness)  
    cout << "Using non-deterministic-seed \"warm-up\" sequence mersenne twister URNG:" << endl;  
    array<unsigned int, mt19937::state_size> seed_data;  
    generate_n(seed_data.begin(), seed_data.size(), ref(rd));  
    seed_seq seq(begin(seed_data), end(seed_data));  
    mt19937 engine3(seq);  
    test(engine3);  
}  
```  
  
```Output  
Using random_device URNG:  
Randomized vector: 5 -4 2 3 0 5 -2 0 4 2 -1 2 -4 -3 1 4 4 1 2 -2  
Randomized array: O Li V K C Ti N Mg Ne Sc Cl B Cr Mn Ca Al F P Na Be Si Ar Fe S He H  
--  
Using constant-seed mersenne twister URNG:  
Randomized vector: 3 -1 -5 0 0 5 3 -4 -3 -4 1 -3 0 -3 -2 -4 5 1 -1 -1  
Randomized array: Al O Ne Si Na Be C N Cr Mn H V F Sc Mg Fe K Ca S Ti B P Ar Cl Li He  
--  
Using non-deterministic-seed mersenne twister URNG:  
Randomized vector: 5 -4 0 2 1 -2 4 4 -4 0 0 4 -5 4 -5 -1 -3 0 0 3  
Randomized array: Si Fe Al Ar Na P B Sc H F Mg Li C Ti He N Mn Be O Ca Cr V K Ne Cl S  
--  
Using non-deterministic-seed "warm-up" sequence mersenne twister URNG:  
Randomized vector: -1 3 -2 4 1 3 0 -5 5 -5 0 0 5 0 -3 3 -4 2 5 0  
Randomized array: Si C Sc H Na O S Cr K Li Al Ti Cl B Mn He Fe Ne Be Ar V P Ca N Mg F  
--  
```  
  
Dieser Code zeigt zwei verschiedene Randomisierungen – Randomisierungen eines Vektors aus Ganzzahlen und Mischung eines Arrays indizierter Daten – mit einer Testvorlagenfunktion. Der erste Aufruf der Testfunktion verwendet den kryptografisch sicheren, nicht-deterministischen, nicht startwert fähigen, nicht wiederholbaren `random_device`-URNG. Für den zweiten Testlauf wird das `mersenne_twister_engine` als URNG mit einem deterministischen konstanten 32-Bit-Startwert verwendet, was bedeutet, dass die Ergebnisse wiederholbar sind. Der dritte Testlauf startet das `mersenne_twister_engine` mit einem nicht-deterministischen 32-Bit-Ergebnis aus `random_device`. Der vierte Testlauf baut darauf auf, indem er eine mit `random_device`-Ergebnissen gefüllte [Startwertsequenz](../standard-library/seed-seq-class.md) verwendet, die mehr als 32-Bit nicht-deterministische Zufallszahlen ausgibt ( die aber immer noch kryptografisch sicher sind). Weitere Informationen dazu erhalten Sie im Folgenden.  
  
##  <a name="listing"></a> Kategorisierte Auflistung  
  
###  <a name="urngs"></a> Einheitlicher Zufallszahlengenerator  
 URNGs werden oft anhand folgender Eigenschaften beschrieben:  
  
1. **Periodenlänge**: Anzahl von Iterationen, die für eine Wiederholung der generierten Zahlensequenz erforderlich sind. Je länger, desto besser.  
  
2. **Leistung**: Geschwindigkeit und Speicherplatzbedarf der Generierung von Zahlen. Je kürzer, desto besser.  
  
3. **Qualität**: Ähnlichkeit der generierten Sequenz mit wirklich zufälligen Zahlen. Dies wird häufig als „*Zufallscharakter*“ bezeichnet.  
  
 In den folgenden Abschnitten werden die Uniform Random Number-Generatoren (URNGs) im `<random>`-Header aufgelistet.  
  
####  <a name="rd"></a> Nicht-deterministischen Generator  
  
|||  
|-|-|  
|[random_device-Klasse](../standard-library/random-device-class.md)|Generiert eine nicht-deterministische und kryptografisch sichere Zufallssequenz mithilfe eines externen Geräts. Wird normalerweise zur Ausstattung eines Moduls mit einem Startwert verwendet. Geringe Leistung, sehr hohe Qualität. Weitere Informationen finden Sie in den [Hinweisen](#comments).|  
  
####  <a name="typedefs"></a> Modultypdefinitionen mit voreingestellten Parametern  
 Zur Instanzierung von Modulen und Moduladaptern. Weitere Informationen erhalten Sie im Abschnitt [Module und Verteilungen](#engdist).  
  
- `default_random_engine` Das Standardmodul.   
 `typedef mt19937 default_random_engine;`  
  
- `knuth_b` Knuth-Modul.   
 `typedef shuffle_order_engine<minstd_rand0, 256> knuth_b;`  
  
- `minstd_rand0` Minimal Standard Engine 1988 (Lewis, Goodman und Miller 1969).   
 `typedef linear_congruential_engine<unsigned int, 16807, 0, 2147483647> minstd_rand0;`  
  
- `minstd_rand` Aktualisierter Minimal Standard Engine `minstd_rand0` (Park, Miller und Stockmeyer 1993).   
 `typedef linear_congruential_engine<unsigned int, 48271, 0, 2147483647> minstd_rand;`  
  
- `mt19937` 32-Bit-Mersenne-Twistermodul (Matsumoto und Nishimura, 1998).   
 `typedef mersenne_twister_engine<unsigned int, 32, 624, 397,      31, 0x9908b0df,      11, 0xffffffff,      7, 0x9d2c5680,      15, 0xefc60000,      18, 1812433253> mt19937;`  
  
- `mt19937_64` 64-Bit-Mersenne-Twistermodul (Matsumoto und Nishimura, 2000).   
 `typedef mersenne_twister_engine<unsigned long long, 64, 312, 156,      31, 0xb5026f5aa96619e9ULL,      29, 0x5555555555555555ULL,      17, 0x71d67fffeda60000ULL,      37, 0xfff7eee000000000ULL,      43, 6364136223846793005ULL> mt19937_64;`  
  
- `ranlux24` 24-Bit-RANLUX-Modul (Martin Lüscher und Fred James, 1994).   
 `typedef discard_block_engine<ranlux24_base, 223, 23> ranlux24;`  
  
- `ranlux24_base` wird als Grundlage für `ranlux24` verwendet.   
 `typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
- `ranlux48` 48-Bit-RANLUX-Modul (Martin Lüscher und Fred James, 1994).   
 `typedef discard_block_engine<ranlux48_base, 389, 11> ranlux48;`  
  
- `ranlux48_base` wird als Grundlage für `ranlux48` verwendet.   
 `typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
####  <a name="eng"></a> Modulvorlagen  
 Modulvorlagen werden als eigenständige URNGs verwendet oder als Basismodule an [Moduladapter](#engadapt) übergeben. Diese werden normalerweise mit einer [vorangestellten Modultypdefinition](#typedefs) instanziert und an eine [Verteilung](#distributions) übergeben. Weitere Informationen erhalten Sie im Abschnitt [Module und Verteilungen](#engdist).  
  
|||  
|-|-|  
|[linear_congruential_engine-Klasse](../standard-library/linear-congruential-engine-class.md)|Generiert eine zufällige Sequenz mithilfe des linearen Kongruenzalgorithmus. Sehr stark vereinfacht und niedrigste Qualität.|  
|[mersenne_twister_engine-Klasse](../standard-library/mersenne-twister-engine-class.md)|Generiert mithilfe des Mersenne-Twisteralgorithmus eine Zufallssequenz. Am komplexesten und mit der höchsten Qualität, außer für die Klasse random_device. Sehr schnelle Leistung.|  
|[subtract_with_carry_engine-Klasse](../standard-library/subtract-with-carry-engine-class.md)|Generiert eine zufällige Sequenz mithilfe des Algorithmus "subtract with carry". Eine Verbesserung gegenüber `linear_congruential_engine`, aber von viel geringerer Qualität und Leistung als `mersenne_twister_engine`.|  
  
####  <a name="engadapt"></a>Moduladaptervorlagen  
 Moduladapter sind Vorlagen, die andere (Basis-)Module anpassen. Diese werden normalerweise mit einer [vorangestellten Modultypdefinition](#typedefs) instanziert und an eine [Verteilung](#distributions) übergeben. Weitere Informationen erhalten Sie im Abschnitt [Module und Verteilungen](#engdist).  
  
|||  
|-|-|  
|[discard_block_engine-Klasse](../standard-library/discard-block-engine-class.md)|Generiert eine zufällige Sequenz, indem die vom Basismodul zurückgegebenen Werte verworfen werden.|  
|[independent_bits_engine-Klasse](../standard-library/independent-bits-engine-class.md)|Generiert eine zufällige Sequenz mit einer angegebenen Anzahl von Bits, indem Bits aus vom Basismodul zurückgegebenen Werten erneut verpackt werden.|  
|[shuffle_order_engine-Klasse](../standard-library/shuffle-order-engine-class.md)|Generiert eine zufällige Sequenz durch Neupositionieren der Werte, die von ihrem Basismodul zurückgegeben werden.|  
  
 [[Modulvorlagen](#eng)]  
  
###  <a name="distributions"></a> Zufallszahlverteilungen  
 In den folgenden Abschnitten werden die Verteilungen im `<random>`-Header aufgelistet. Verteilungen sind ein Nachverarbeitungsmechanismus, der normalerweise URNS-Ausgaben als Eingaben verwendet und die Ausgabe mithilfe einer Funktion mit definierter statistischer Wahrscheinlichkeitsdichte verteilt. Weitere Informationen erhalten Sie im Abschnitt [Module und Verteilungen](#engdist).  
  
#### <a name="uniform-distributions"></a>Gleichförmige Verteilungen.  
  
|||  
|-|-|  
|[uniform_int_distribution-Klasse](../standard-library/uniform-int-distribution-class.md)|Produziert eine gleichförmige Ganzzahlwertverteilung über einen Bereich im geschlossenen Intervall \[a, b] (inklusiv-inklusiv).|  
|[uniform_real_distribution-Klasse](../standard-library/uniform-real-distribution-class.md)|Produziert eine gleichförmige (Gleitkomma-)Echtwerteverteilung über einen Bereich im halboffenen Intervall [a, b) (inklusiv-exklusiv).|  
|[generate_canonical](../standard-library/random-functions.md#generate_canonical)|Produziert eine gleiche (Gleitkomma-)Echtwerteverteilung mit vorgegebener Genauigkeit über [0, 1) (inklusiv-exklusiv).|  
  
 [[Zufallszahlverteilungen](#distributions)]  
  
#### <a name="bernoulli-distributions"></a>Bernoulli-Verteilungen  
  
|||  
|-|-|  
|[bernoulli_distribution-Klasse](../standard-library/bernoulli-distribution-class.md)|Produziert eine Bernoulli-Verteilung von `bool`-Werten.|  
|[binomial_distribution-Klasse](../standard-library/binomial-distribution-class.md)|Produziert eine binomiale Verteilung von Ganzzahlwerten.|  
|[geometric_distribution-Klasse](../standard-library/geometric-distribution-class.md)|Produziert eine geometrische Verteilung von Ganzzahlwerten.|  
|[negative_binomial_distribution-Klasse](../standard-library/negative-binomial-distribution-class.md)|Produziert eine negative binomiale Verteilung von Ganzzahlwerten.|  
  
 [[Zufallszahlverteilungen](#distributions)]  
  
#### <a name="normal-distributions"></a>Normalverteilungen  
  
|||  
|-|-|  
|[cauchy_distribution-Klasse](../standard-library/cauchy-distribution-class.md)|Produziert eine Couch-Verteilung von (Gleitkomma-)Echtwerten.|  
|[chi_squared_distribution-Klasse](../standard-library/chi-squared-distribution-class.md)|Produziert eine Chi-Quadrat-Verteilung von (Gleitkomma-)Echtwerten.|  
|[fisher_f_distribution-Klasse](../standard-library/fisher-f-distribution-class.md)|Produziert eine F-Verteilung (auch bekannt als Sender-F-Verteilung oder Fisher-Snedecor-Verteilung) von (Gleitkomma-) echtwerten.|  
|[lognormal_distribution-Klasse](../standard-library/lognormal-distribution-class.md)|Produziert eine Lognormalverteilung von (Gleitkomma-)Echtwerten.|  
|[normal_distribution-Klasse](../standard-library/normal-distribution-class.md)|Produziert eine (Gaußsche) Normalverteilung von (Gleitkomma-)Echtwerten.|  
|[student_t_distribution-Klasse](../standard-library/student-t-distribution-class.md)|Produziert die studentische *t*-Verteilung von (Gleitkomma-)Echtwerten.|  
  
 [[Zufallszahlverteilungen](#distributions)]  
  
#### <a name="poisson-distributions"></a>Poisson-Verteilungen  
  
|||  
|-|-|  
|[exponential_distribution-Klasse](../standard-library/exponential-distribution-class.md)|Produziert eine exponentielle Verteilung von (Gleitkomma-)Echtwerten.|  
|[extreme_value_distribution-Klasse](../standard-library/extreme-value-distribution-class.md)|Produziert eine Extremwertverteilung von (Gleitkomma-)Echtwerten.|  
|[gamma_distribution-Klasse](../standard-library/gamma-distribution-class.md)|Produziert eine Gammaverteilung von (Gleitkomma-)Echtwerten.|  
|[poisson_distribution-Klasse](../standard-library/poisson-distribution-class.md)|Produziert eine Poisson-Verteilung von Ganzzahlwerten.|  
|[weibull_distribution-Klasse](../standard-library/weibull-distribution-class.md)|Produziert eine Weibull-Verteilung von (Gleitkomma-)Echtwerten.|  
  
 [[Zufallszahlverteilungen](#distributions)]  
  
#### <a name="sampling-distributions"></a>Sampling-Verteilungen  
  
|||  
|-|-|  
|[discrete_distribution-Klasse](../standard-library/discrete-distribution-class.md)|Produziert eine diskrete Ganzzahlverteilung.|  
|[piecewise_constant_distribution-Klasse](../standard-library/piecewise-constant-distribution-class.md)|Produziert eine stückweise konstante Verteilung von (Gleitkomma-)Echtwerten.|  
|[piecewise_linear_distribution-Klasse](../standard-library/piecewise-linear-distribution-class.md)|Produziert eine stückweise lineare Verteilung von (Gleitkomma-)Echtwerten.|  
  
 [[Zufallszahlverteilungen](#distributions)]  
  
### <a name="utility-functions"></a>Hilfsfunktionen  
 In diesem Abschnitt werden die allgemeinen Hilfsfunktionen im `<random>`-Header aufgelistet.  
  
|||  
|-|-|  
|[seed_seq-Klasse](../standard-library/seed-seq-class.md)|Generiert eine nicht-gewichtete verschlüsselte Startwertsequenz. Wird verwendet, um Replikationen von Zufallsvariablenstreams zu vermeiden. Hilfreich, wenn viele URNGs durch Module instanziert werden.|  
  
### <a name="operators"></a>Operatoren  
 In diesem Abschnitt werden die Operation im `<random>`-Header aufgelistet.  
  
|||  
|-|-|  
|`operator==`|Testet, ob der URNG links vom Operator gleich dem Modul rechts vom Operator ist.|  
|`operator!=`|Testet, ob der URNG links vom Operator ungleich dem Modul rechts vom Operator ist.|  
|`operator<<`|Schreibt Zustandsinformationen in einen Stream.|  
|`operator>>`|Extrahiert Zustandsinformationen aus einem Stream.|  
  
##  <a name="engdist"></a> Module und Verteilungen  
 Informationen zu jeder dieser in `<random>` definierten Vorlagenklassenkategorien finden Sie in den folgenden Abschnitten: Beide dieser Vorlagenklassenkategorien akzeptieren einen Typ als Argument und verwenden allgemeine Namen eines Vorlagenparameters, um die Eigenschaften des Typs, die als tatsächlicher Argumenttyp zulässig sind, wie folgt zu beschreiben:  
  
- `IntType` zeigt `short`, `int`, `long`, `long long`, `unsigned short`, `unsigned int`, `unsigned long` oder `unsigned long long` an.  
  
- `UIntType` zeigt `unsigned short`, `unsigned int`, `unsigned long` oder `unsigned long long` an.  
  
- `RealType` zeigt `float`, `double` oder `long double` an.  
  
### <a name="engines"></a>Module  
 [Modulvorlagen](#eng) und [Moduladaptervorlagen](#engadapt) sind Vorlagen, mit deren Parametern der erstellte Generator angepasst wird.  
  
 Ein *Modul* ist eine Klasse oder Vorlagenklasse, deren Instanzen (Generatoren) als Quelle von Zufallszahlen fungieren, die gleichmäßig zwischen einem Mindest- und einen Höchstwert verteilt werden. Ein *Moduladapter* gibt eine Sequenz von Werten aus, die verschiedene Zufallscharaktereigenschaften haben, indem er von einem anderen Zufallswertemodul produzierte Werte übernimmt und einen bestimmtem Algorithmus für diese Werte anwendet.  
  
 Jedes Modul und jeder Moduladapter haben die folgenden Member:  
  
- `typedef` `numeric-type` `result_type` ist der vom `operator()` des Generators zurückgegebene Typ. Der `numeric-type` wird als Vorlagenparameter bei der Instanzierung übergeben.  
  
- `result_type operator()` gibt Werte zurück, die gleichmäßig zwischen `min()` und `max()` verteilt werden.  
  
- `result_type min()` gibt den vom `operator()` des Generators zurückgegeben Mindestwert zurück. Moduladapter verwenden das `min()`-Ergebnis des Basismoduls.  
  
- `result_type max()` gibt den vom `operator()` des Generators zurückgegeben Höchstwert zurück. Wenn `result_type` ein Integraltyp (Ganzzahlwerttyp) ist, ist `max()` der Höchstwert, der tatsächlich zurückgegeben werden kann (inklusiv). Wenn `result_type` ein Gleitkommatyp (Echtwerttyp) ist, ist `max()` der kleinste Wert, der größer als alle Werte ist, die zurückgegeben werden können (nicht-inklusiv). Moduladapter verwenden das `max()`-Ergebnis des Basismoduls.  
  
- `void seed(result_type s)` startet den Generator mit dem Startwert `s`. Für Module lautet die Signatur zur Unterstützung von Standardparametern `void seed(result_type s = default_seed)` (Moduladapter definieren einen separaten `void seed()`, siehe nächsten Unterabschnitt).  
  
- `template <class Seq> void seed(Seq& q)` startet den Generator mithilfe von [seed_seq](../standard-library/seed-seq-class.md)`Seq`.  
  
-   Ein expliziter Konstruktor mit dem Argument `result_type x`, mit dem ein Generator erstellt wird, der mit Startwerten versehen ist, als wäre `seed(x)` aufgerufen worden.  
  
-   Ein expliziter Konstruktor mit dem Argument `seed_seq& seq`, mit dem ein Generator erstellt wird, der mit Startwerten versehen ist, als wäre `seed(seq)` aufgerufen worden.  
  
- `void discard(unsigned long long count)` ruft `operator()` effektiv mit der Häufigkeit `count` auf und bewertet jeden Wert.  
  
 **Moduladapter** unterstützen zusätzlich diese Member (`Engine` ist der erste Vorlagenparameter eines Moduladapters, der den Typ des Basismoduls bezeichnet):  
  
-   Ein Standardkonstruktor zur Initialisierung des Generators genau wie durch den Standardkonstruktor des Basismoduls.  
  
-   Ein expliziter Konstruktor mit dem Argument `const Engine& eng`. Dieser dient zur Unterstützung einer Kopienkonstruktion mithilfe des Basismoduls.  
  
-   Ein expliziter Konstruktor mit dem Argument `Engine&& eng`. Dieser dient zur Unterstützung einer Verschiebungskonstruktion mithilfe des Basismoduls.  
  
- `void seed()`, der den Generator mit dem Standardstartwert des Basismoduls initialisiert.  
  
- `const Engine& base()`-Eigenschaftsfunktion, die das Basismodul zurückgibt, das zur Konstruktion des Generators verwendet wurde.  
  
 Jedes Modul besitzt einen *Zustand*, mit dem die Sequenz der Werte bestimmt wird, die durch nachfolgende Aufrufe von `operator()` generiert werden. Die Zustände von zwei Generatoren, die von Modulen desselben Typs instanziert wurden, können mithilfe von `operator==` und `operator!=` verglichen werden. Wenn die beiden Zustände als gleich verglichen werden, generieren Sie dieselbe Sequenz von Werten. Der Zustand eines Objekts kann als Sequenz von 32-Bit-Werten ohne Vorzeichen zu einem Stream gespeichert werden, indem die `operator<<` des Generators verwendet werden. Der Zustand wird durch das Speichern nicht geändert. Ein gespeicherter Zustand kann mithilfe von `operator>>` in den Generator eingelesen werden, der von einem Modul desselben Typs instanziert wurde.  
  
### <a name="distributions"></a>Verteilungen  
 Die [Zufallszahlenverteilung](#distributions) ist eine Klasse oder eine Vorlagenklasse, deren Instanzen einen Stream gleichmäßig verteilter Zufallszahlen transformieren, die aus einem Modul in einen Stream von Zufallszahlen mit einer bestimmten Verteilung bezogen werden. Jede Verteilung verfügt über die folgenden Member:  
  
- `typedef` `numeric-type` `result_type` ist der vom `operator()` der Verteilung zurückgegebene Typ. Der `numeric-type` wird als Vorlagenparameter bei der Instanzierung übergeben.  
  
- `template <class URNG> result_type operator()(URNG& gen)` gibt Werte zurück, die entsprechend der Definition der Verteilung verteilt werden, indem `gen` als Quelle für gleichmäßig verteilte Zufallswerte und die gespeicherten *Parameter der Verteilung* verwendet wird.  
  
- `template <class URNG> result_type operator()(URNG& gen, param_type p)` gibt die Werte zurück, die in Übereinstimmung mit der Definition der Verteilung mithilfe von `gen` als Quelle für gleichmäßig verteilte Zufallswerte und die Parameterstruktur `p` verteilt werden.  
  
- `typedef` `unspecified-type` `param_type` ist das Paket von Parametern, die optional an `operator()` übergeben werden, und wird anstelle der gespeicherten Parameter verwendet, um den Rückgabewert zu generieren.  
  
-   Ein `const param&`-Konstruktor initialisiert die gespeicherten Parameter aus dem Argument.  
  
- `param_type param() const` ruft die gespeicherten Parameter ab.  
  
- `void param(const param_type&)` legt die gespeicherten Parameter aus dem Argument fest.  
  
- `result_type min()` gibt den vom `operator()` der Verteilung zurückgegeben Mindestwert zurück.  
  
- `result_type max()` gibt den vom `operator()` der Verteilung zurückgegebenen Höchstwert zurück. Wenn `result_type` ein Integraltyp (Ganzzahlwerttyp) ist, ist `max()` der Höchstwert, der tatsächlich zurückgegeben werden kann (inklusiv). Wenn `result_type` ein Gleitkommatyp (Echtwerttyp) ist, ist `max()` der kleinste Wert, der größer als alle Werte ist, die zurückgegeben werden können (nicht-inklusiv).  
  
- `void reset()` verwirft alle zwischengespeicherten Werte, damit das Ergebnis des folgenden Aufrufs von `operator()` nicht von Werten abhängig ist, die vor dem Aufruf aus dem Modul bezogen wurden.  
  
 Eine Parameterstruktur ist ein Objekt, in dem alle für eine Verteilung erforderlichen Parameter gespeichert werden. Sie enthält folgende Informationen:  
  
- `typedef` `distribution-type` `distribution_type` ist der Typ der Verteilung.  
  
-   Mindestens ein Konstruktor, der die gleichen Parameterlisten akzeptiert, wie von den Verteilungskonstruktoren akzeptiert werden.  
  
-   Die gleichen Parameterzugriffsfunktionen wie bei der Verteilung.  
  
-   Gleichheits- und Ungleichheitsvergleichsoperatoren.  
  
 Weitere Informationen erhalten Sie in den entsprechenden Unterthemen unter diesem Thema, auf die zuvor in diesem Artikel verlinkt wurde.  
  
##  <a name="comments"></a> Hinweise  
 Dies sind zwei höchst hilfereiche URNGs in Visual Studio – `mt19937` und `random_device` – wie in der Vergleichstabelle gezeigt:  
  
|URNG|Fast|Kryptografisch sicher|Startwertfähig|Deterministic|  
|----------|-----------|---------------------|---------------|--------------------|  
|`mt19937`|Ja|Nein|Ja|Ja<sup>*</sup>|  
|`random_device`|Nein|Ja|Nein|Nein|  
  
 <sup>* Wenn mit einem bekannten Startwert ausgestattet.</sup>  
  
 Obwohl der ISO C++-Standard nicht erfordert, dass `random_device` kryptografisch sicher ist, wird es in Visual Studio implementiert, um kryptografische Sicherheit herzustellen. (Der Begriff „kryptografisch sicher“ drückt keine Garantie aus, sondern bezeichnet ein Mindest-Entropieniveau – und damit ein Vorhersagbarkeitsniveau –, das ein bestimmter Randomisierungsalgorithmus aufweist. Weitere Informationen finden Sie im Wikipedia-Artikel [Cryptographically secure pseudorandom number generator (Kryptographisch sicherer Zufallszahlengenerator, in englischer Sprache)](http://go.microsoft.com/fwlink/p/?linkid=398017).) Da der ISO C++-Standard dies nicht erfordert, können andere Plattformen `random_device` als einfachen Zufallszahlengenerator (kryptografisch nicht sicher) implementieren, der nur als Stammwertequelle für einen anderen Generator geeignet ist. Lesen Sie die Dokumentation für diese Plattformen, wenn Sie `random_device` plattformübergreifend verwenden.  
  
 `random_device`-Ergebnisse sind per Definition nicht reproduzierbar, und ein Nebeneffekt ist, dass er eventuell deutlich langsamer läuft als andere URNGs. Die meisten Anwendungen, für die keine kryptografische Sicherheit erforderlich sind, verwenden `mt19937` oder ein ähnliches Modul, obwohl Sie es vielleicht mit einem Aufruf von `random_device` starten möchten, wie im [Codebeispiel](#code) gezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)

