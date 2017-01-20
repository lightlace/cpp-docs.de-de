---
title: "Unterst&#252;tzung f&#252;r C++11/14/17-Funktionen (Modern C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd2d5cbc-caf5-4a11-a057-8c365decba4e
caps.latest.revision: 59
caps.handback.revision: "56"
ms.author: "mblome"
manager: "ghogen"
---
# Unterst&#252;tzung f&#252;r C++11/14/17-Funktionen (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt C\+\+11\/14\/17\-Features in Visual C\+\+.  
  
##  <a name="top"></a> In diesem Artikel  
  
-   [Liste der C ++ 11-Features](#featurelist)  
  
    -   [Funktionstabelle der C++11-Kernsprache](#corelanguagetable)  
  
    -   [Funktionstabelle für C++11-Kernsprachfunktionen: Nebenläufigkeit](#concurrencytable)  
  
    -   [Features der C++11-Kernsprache: C99](#c99table)  
  
-   [Features der C++14-Kernsprache](#cpp14table)  
  
-   [Vorgeschlagene C++17-Kernsprachenfunktionen](#cpp17table)  
  
-   [Leitfaden zu den Funktionstabellen](#tableguide)  
  
    -   [rvalue-Referenzen](#rvref)  
  
    -   [Lambdas](#lambdas)  
  
    -   [decltype](#decltype)  
  
    -   [Stark typisierte und vorwärts deklarierte Enumerationen](#stronglytyped)  
  
    -   [Ausrichtung](#alignment)  
  
    -   [Standardlayout- und einfache Typen](#standardlayout)  
  
    -   [Defaulted- und Deleted-Funktionen](#defaultedanddeleted)  
  
    -   [override und final](#overrideandfinal)  
  
    -   [Atomics und mehr](#atomics)  
  
    -   [C99 __func__ und Präprozessorregeln](#c99)  
  
-   [Standardbibliotheksfeatures](#stl)  
  
##  <a name="featurelist"></a> Liste der C \+\+ 11\-Features  
 Visual C\+\+ implementiert den Großteil der Features in der [C\+\+11\-Kernsprachenspezifikation](http://go.microsoft.com/fwlink/p/?LinkID=235092) sowie zahlreiche C\+\+17\-Bibliotheksfeatures und einige für C\+\+17 vorgeschlagene Features. In der folgenden Tabelle sind die C\+\+11\/14\/17\-Kernsprachenfunktionen und deren Implementierungsstatus in Visual C\+\+ in Visual Studio 2010, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] und [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] aufgelistet.  
  
###  <a name="corelanguagetable"></a> Funktionstabelle der C\+\+11\-Kernsprache  
  
|[Features der C\+\+11\-Kernsprache](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2869.html)|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|-------------------------------------------------------------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|rvalue\-Referenzen [v0.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1610.html), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n2118.html), [v2.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2844.html), [v2.1](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html), [v3.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3053.html)|v2.0|v2.1\*|v2.1\*|v3.0|  
|[ref\-Qualifizierer](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2439.htm)|Nein|Nein|Nein|Ja|  
|[Nicht statische Datenmemberinitialisierer](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2756.htm)|Nein|Nein|[Ja](../cpp/uniform-initialization-and-delegating-constructors.md)|Ja|  
|variadic\-Vorlagen [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2242.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2555.pdf)|Nein|Nein|[Ja](../cpp/ellipses-and-variadic-templates.md)|Ja|  
|[Initialisiererlisten](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2672.htm)|Nein|Nein|[Ja](../cpp/uniform-initialization-and-delegating-constructors.md)|Ja|  
|[static\_assert](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1720.html)|Ja|Ja|Ja|Ja|  
|auto [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1984.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2546.htm)|v1.0|v1.0|v1.0|Ja|  
|[Nachstehende Rückgabetypen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2541.htm)|Ja|Ja|Ja|Ja|  
|Lambdas [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2550.pdf), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2658.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2927.pdf)|v1.0|v1.1|v1.1|Ja|  
|decltype [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2343.pdf), [v1.1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3276.pdf)|v1.0|v1.1\*\*|v1.1|Ja|  
|[Öffnende spitze Klammer](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1757.html)|Ja|Ja|Ja|Ja|  
|[Standardvorlagenargumente für Funktionsvorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html)|Nein|Nein|Ja|Ja|  
|[SFINAE für Ausdrücke](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2634.html)|Nein|Nein|Nein|Nein|  
|[Alias\-Vorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2258.pdf)|Nein|Nein|[Ja](../cpp/aliases-and-typedefs-cpp.md)|Ja|  
|[Extern\-Vorlagen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1987.htm)|Ja|Ja|Ja|Ja|  
|[nullptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2431.pdf)|Ja|Ja|Ja|Ja|  
|[Stark typisierte Enumerationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2347.pdf)|Partial|Ja|Ja|Ja|  
|[Vorwärts deklarierte Enumerationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2764.pdf)|Nein|Ja|Ja|Ja|  
|[Attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2761.pdf)|Nein|Nein|Nein|Ja|  
|[constexpr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2235.pdf)|Nein|Nein|Nein|Ja|  
|[Ausrichtung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2341.pdf)|TR1|Partial|Partial|Ja|  
|[Delegierende Konstruktoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1986.pdf)|Nein|Nein|[Ja](../cpp/uniform-initialization-and-delegating-constructors.md)|Ja|  
|[Konstruktorvererbung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2540.htm)|Nein|Nein|Nein|Ja|  
|[Explizite Konvertierungsoperatoren](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2437.pdf)|Nein|Nein|Ja|Ja|  
|[char16\_t\/char32\_t](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2249.html)|Nein|Nein|Nein|Ja|  
|[Unicode\-Zeichenfolgenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|Nein|Nein|Nein|Ja|  
|[Unformatierte Zeichenfolgenliterale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2442.htm)|Nein|Nein|[Ja](../cpp/string-and-character-literals-cpp.md)|Ja|  
|[Universelle Zeichennamen in Literalen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2170.html)|Nein|Nein|Nein|Ja|  
|[Benutzerdefinierte Literale](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2765.pdf)|Nein|Nein|Nein|Ja|  
|[Standardlayout\- und einfache Typen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2342.htm)|Nein|Ja|Ja|Ja|  
|[Defaulted\- und Deleted\-Funktionen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2346.htm)|Nein|Nein|[Ja\*](../cpp/explicitly-defaulted-and-deleted-functions.md)|Ja|  
|[Erweiterte Friend\-Deklarationen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1791.pdf)|Ja|Ja|Ja|Ja|  
|[Erweitertes sizeof](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2253.html)|Nein|Nein|Nein|Ja|  
|[Inlinenamespaces](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2535.htm)|Nein|Nein|Nein|Ja|  
|[Uneingeschränkte Unions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2544.pdf)|Nein|Nein|Nein|Ja|  
|[Lokale und unbenannte Typen als Vorlagenargumente](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2657.htm)|Ja|Ja|Ja|Ja|  
|[Bereichsbasierte For\-Loop\-Schleife](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2930.html)|Nein|Ja|Ja|Ja|  
|override und final [v0.8](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2009/n2928.htm), [v0.9](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3206.htm), [v1.0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2011/n3272.htm)|Partial|Ja|Ja|Ja|  
|[Minimale GC\-Unterstützung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2670.htm)|Ja|Ja|Ja|Ja|  
|[noexcept](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2010/n3050.html)|Nein|Nein|Nein|Ja|  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="concurrencytable"></a> Funktionstabelle für C\+\+11\-Kernsprachfunktionen: Nebenläufigkeit  
  
|Features der C\+\+11\-Kernsprache: Nebenläufigkeit|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|--------------------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[Neu formulierte Sequenzpunkte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2239.html)|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Ja|  
|[Atomics](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2427.html)|Nein|Ja|Ja|Ja|  
|[Starke compare\_exchange\-Operation](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2748.html)|Nein|Ja|Ja|Ja|  
|[Bidirektionale Fences](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2752.htm)|Nein|Ja|Ja|Ja|  
|[Speichermodell](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2429.htm)|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Ja|  
|[Datenabhängigkeits\-Reihenfolge](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2664.htm)|Nein|Ja|Ja|Ja|  
|[Datenabhängigkeits\-Reihenfolge: Funktionsanmerkung](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2782.htm)|Nein|Nein|Nein|Ja|  
|[exception\_ptr](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2179.html)|Ja|Ja|Ja|Ja|  
|[quick\_exit](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2440.htm)|Nein|Nein|Nein|Ja|  
|[Atomics in Signalhandlern](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2547.htm)|Nein|Nein|Nein|Nein|  
|[Lokaler Threadspeicher](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2659.htm)|Partial|Partial|Partial|Ja|  
|[„Magische“ static\-Objekte](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2008/n2660.htm)|Nein|Nein|Nein|Ja|  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="c99table"></a> Features der C\+\+11\-Kernsprache: C99  
  
|Features der C\+\+11\-Kernsprache: C99|Visual Studio 2010|Visual Studio 2012|[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]|Visual Studio 2015|  
|--------------------------------------------|------------------------|------------------------|--------------------------------------------------------------|------------------------|  
|[\_\_func\_\_](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2340.htm)|Partial|Partial|Partial|Ja|  
|[C99\-Präprozessor](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2004/n1653.htm)|Partial|Partial|Partial|Partial|  
|[long long](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1811.pdf)|Ja|Ja|Ja|Ja|  
|[Erweiterte Integer\-Typen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2006/n1988.pdf)|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|Nicht zutreffend|  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="cpp14table"></a> Features der C\+\+14\-Kernsprache  
  
||||  
|-|-|-|  
|Funktion|Visual Studio 2013|Visual Studio 2015|  
|Optimierte Formulierungen für kontextbezogene Konvertierungen|Ja|Ja|  
|Binäre Literale|Nein|Ja|  
|Rückagebetypen „auto“ und „decltype\(auto\)“|Nein|Ja|  
|init\-captures|Nein|Ja|  
|Generische Lambda\-Ausdrücke|Nein|Ja|  
|Variablenvorlagen|Nein|Nein|  
|Erweiterte constexpr|Nein|Nein|  
|NSDMIs für Aggregate|Nein|Nein|  
|Zuordnungen vermeiden\/zusammenführen|Nein|Nein|  
|\[\[veraltet\]\]\-Attribute|Nein|Nein|  
|Zuordnung nach Größe|Nein|Ja|  
|Zahlentrennzeichen|Nein|Ja|  
  
###  <a name="cpp17table"></a> Vorgeschlagene C\+\+17\-Kernsprachenfunktionen  
  
||||  
|-|-|-|  
|Funktion|Visual Studio 2013|Visual Studio 2015|  
|Neue Regeln für „auto“ mit „braced\-init\-lists“|Nein|Nein|  
|Knappes statisches „assert“|Nein|Nein|  
|typename in Vorlagen\-Vorlagenparameter|Nein|Nein|  
|Entfernen von Trigraphen|Ja|Ja|  
|Geschachtelte Namespacedefinitionen|Nein|Nein|  
|N4259 std::uncaught\_exceptions\(\)|Nein|Nein|  
|N4261 Qualifikationskonvertierungen beheben|Nein|Nein|  
|N4266 Attribute für Namespaces und Enumeratoren|Nein|Nein|  
|N4267 u8\-Zeichenliterale|Nein|Nein|  
|N4268 Mehr Nicht\-Typen\-Vorlagenargumente zulässig|Nein|Nein|  
|N4295 Fold\-Ausdrücke|Nein|Nein|  
|await\/resume|Nein|Ja|  
  
##  <a name="tableguide"></a> Leitfaden zu den Funktionstabellen  
  
###  <a name="rvref"></a> rvalue\-Referenzen  
  
> [!NOTE]
>  Die Versionsbezeichnungen in den folgenden Beschreibungen \(v0.1, v1.0, v2.0, v2.1 und v3.0\) wurden aus Gründen der Übersichtlichkeit eingeführt und zeigen die Entwicklung von C\+\+11. Der Standard selbst verwendet sie nicht.  
  
 [N1610 „Clarification of Initialization of Class Objects by rvalues“](http://go.microsoft.com/fwlink/p/?LinkID=235093) war ein früher Versuch, Verschiebesemantik ohne rvalue\-Referenzen zu ermöglichen.  In dieser Diskussion soll sie "rvalue\-Referenz v0.1" genannt werden. Sie wurde ersetzt durch „rvalue\-Referenzen [v1.0](http://go.microsoft.com/fwlink/p/?LinkID=235094)“. „rvalue\-Referenzen [v2.0](http://go.microsoft.com/fwlink/p/?LinkID=235095)“, auf dem die Arbeit in Visual C\+\+ in Visual Studio 2010 basiert, verhindert die Bindung von rvalue\-Referenzen an „lvalues“ und behebt damit ein schwerwiegendes Sicherheitsproblem.  „rvalue\-Referenzen [v2.1](http://go.microsoft.com/fwlink/p/?LinkID=235096)“ entwickelt diese Regel weiter.  Betrachten Sie `vector<string>::push_back()` mit den Überladungen `push_back(const string&)` und `push_back(string&&)`, dazu den Aufruf `v.push_back("strval")`.  Der Ausdruck `"strval"` ist ein Zeichenfolgenliteral, und er ist ein lvalue.  \(Andere Literale, beispielsweise die Ganzzahl 1729, sind rvalues, aber Zeichenfolgenliterale sind speziell, da sie Arrays sind.\)  Die Regeln aus "rvalue\-Referenzen v2.0" besagen, dass `string&&` nicht an `"strval"` gebunden werden kann, da `"strval"` ein lvalue ist, und daher `push_back(const string&)` die einzige realisierbare Überladung ist.  Dies würde einen temporären `std::string` erstellen, ihn in den Vektor kopieren und `std::string` anschließend zerstören, was nicht effizient wäre. Die "rvalue\-Referenzen v2.1"\-Regeln erkennen, dass die Bindung von `string&&` an `"strval"` einen temporären `std::string` erstellen würde, und dass dieser ein rvalue ist.  Daher sind `push_back(const string&)` und `push_back(string&&)` realisierbar, und `push_back(string&&)` wird bevorzugt.  Ein temporärer `std::string` wird erstellt und dann in den Vektor verschoben.  Dies ist effizienter.  
  
 „rvalue\-Referenzen [v3.0](http://go.microsoft.com/fwlink/p/?LinkID=235097)“ fügt neue Regeln hinzu, um Verschiebungskonstruktoren und Verschiebungszuweisungsoperatoren unter bestimmten Bedingungen automatisch zu generieren. Dies ist in Visual Studio 2015 implementiert.  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="lambdas"></a> Lambdas  
 Nachdem [Lambda\-Funktionen](../cpp/lambda-expressions-in-cpp.md) in das Arbeitspapier \([Version „0.9“](http://go.microsoft.com/fwlink/p/?LinkID=235098)\) gewählt und änderbare Lambdas hinzugefügt wurden \([Version „1.0“](http://go.microsoft.com/fwlink/p/?LinkID=235099)\), hat der Standardisierungsausschuss die Formulierung überarbeitet. Dies erzeugt Lambdas [Version „1.1“](http://go.microsoft.com/fwlink/p/?LinkID=235100), die jetzt vollständig unterstützt wird.  Die Formulierung "Lambdas v1.1" erläutert, wie in Sonderfällen \(Verweis auf statische Member oder geschachtelte Lambdas\) verfahren werden sollte.  Hierdurch werden Probleme behoben, die durch komplexe Lambdas ausgelöst werden.  Darüber hinaus können zustandslose Lambdas nun in Funktionszeiger konvertiert werden.  Dies ist nicht die Formulierung N2927, wird jedoch als Teil von "Lambdas v1.1" angesehen.[C\+\+11](http://go.microsoft.com/fwlink/p/?LinkID=235092) **5.1.2 \[expr.prim.lambda\]\/6** enthält folgende Beschreibung: „Der closure\-Typ für einen `lambda-expression` ohne `lambda-capture` besitzt eine öffentliche, nicht virtuelle, nicht explizite Umwandlungsfunktion für „const“ in Zeiger und kann dadurch dieselben Parameter und Rückgabetypen verwenden wie der Funktionsaufrufoperator des closure\-Typs. Der von dieser Umwandlungsfunktion zurückgegebene Wert soll die Adresse einer Funktion sein, deren Aufruf denselben Effekt hat wie der Aufruf des Funktionsaufrufoperators des closure\-Typs.“  \(Die [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]\-Implementierung ist sogar noch besser, weil damit jetzt zustandslose Lambdas in Funktionszeiger konvertiert werden können, die beliebige Aufrufkonventionen besitzen.  Dies ist wichtig, wenn Sie APIs verwenden, die Elemente wie `__stdcall`\-Funktionszeiger erwarten.\)  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="decltype"></a> decltype  
 Nachdem „decltype“ in das Arbeitspapier \([Version 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235101)\) gewählt wurde, gab es dafür in letzter Minute eine kleine, jedoch wichtige Fehlerkorrektur \([Version 1.1](http://go.microsoft.com/fwlink/p/?LinkID=235102)\).  Dies ist vom großen Interesse für Programmierer, die mit STL und Boots arbeiten.  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="stronglytyped"></a> Stark typisierte und vorwärts deklarierte Enumerationen  
 [Stark typisierte Enumerationen](http://go.microsoft.com/fwlink/p/?LinkID=235103) wurden teilweise in Visual C\+\+ in Visual Studio 2010 unterstützt \(dort speziell im Teil über explizit angegebene zugrunde liegende Typen\). Diese werden jetzt vollständig in Visual Studio implementiert, und die C\+\+11\-Semantik für [vorwärts deklarierte Enumerationen](http://go.microsoft.com/fwlink/p/?LinkID=235104) ist ebenfalls vollständig implementiert.  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="alignment"></a> Ausrichtung  
 Die Kernsprachenschlüsselwörter `alignas`\/`alignof` aus dem [alignment\-Vorschlag](http://go.microsoft.com/fwlink/p/?LinkID=235105), der in das Arbeitspapier gewählt wurde, sind in Visual Studio 2015 implementiert.  Visual C\+\+ in Visual Studio 2010 verfügte über `aligned_storage` aus TR1. In [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] wurden `aligned_union` und `std::align()` zur Standardbibliothek hinzugefügt und in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] wurden wichtige Fehler behoben.  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="standardlayout"></a> Standardlayout\- und einfache Typen  
 Die verfügbar gemachten Änderungen aus [N2342 „POD's Revisited; Resolving Core Issue 568 \(Revision 5\)“](http://go.microsoft.com/fwlink/p/?LinkID=235106) sind die Ergänzungen von `is_trivial` und `is_standard_layout` zur Bibliothek der Standardvorlage `<type_traits>`.  \(In N2342 wurden viele Benennungen der Kernsprache überarbeitet, Compileränderungen waren jedoch nicht erforderlich.\)  Diese Typmerkmale waren in Visual C\+\+ in Visual Studio 2010 verfügbar, aber sie duplizierten einfach `is_pod`. Daher ist in der oben dargestellten Tabelle bezüglich der Unterstützung "Nein" angegeben.  Sie werden nun durch Compilerhooks unterstützt, die entwickelt wurden, um genaue Antworten zu geben.  
  
 Der [common\_type\<\>](../standard-library/common-type-class.md) von STL erhielt eine dringend erforderliche Korrektur in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)].  Die C\+\+11\-Spezifizierung für `common_type<>` hatte unerwarteten und unerwünschten Folgen. Insbesondere führte es dazu, dass `common_type<int, int>::type``int&&` zurückgab. Daher implementiert [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] die [Vorgeschlagene Lösung für das Bibliotheks\-Arbeitsgruppenproblem 2141](http://go.microsoft.com/fwlink/p/?LinkId=320075), bei dem von `common_type<int, int>::type``int` zurückgegeben wird.  
  
 Als Nebeneffekt dieser Änderung funktioniert der Identitätsfall nicht mehr \(`common_type<T>` ergibt nicht immer den Typ `T`\). Dies entspricht der vorgeschlagenen Lösung, beeinträchtigt jedoch den Code, der auf dem vorherigen Verhalten beruhte.  
  
 Wenn ein Identitätstypmerkmal erforderlich ist, verwenden Sie nicht `std::identity`, das kein Standard ist und in `<type_traits>` definiert ist, da es nicht bei `<void>` funktioniert. Implementieren Sie stattdessen Ihr eigenes Identitätstypmerkmal, um Ihre Anforderungen zu erfüllen. Im Folgenden ein Beispiel:  
  
```cpp  
template <typename T> struct Identity { typedef T type; };  
  
```  
  
> [!NOTE]
>  Weitere wichtige Änderungen finden Sie unter [Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md).  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="defaultedanddeleted"></a> Defaulted\- und Deleted\-Funktionen  
 Diese werden jetzt unterstützt, allerdings mit folgender Ausnahme: Für Defaulted\-Funktionen wird die Verwendung von `=default` zur Anforderung von Bewegungskonstruktoren und Bewegungszuweisungsoperatoren für jeden Member nicht unterstützt. Die Kopien und die Verschiebungen interagieren nicht präzise, wie im Standard vorgegeben. Durch Löschen von Verschiebungen sollen auch Kopien unterdrückt werden, was bei [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] jedoch nicht der Fall ist.  
  
 Weitere Informationen zur Verwendung von Defaulted\- und Deleted\-Funktionen finden Sie unter [Funktionen](../cpp/functions-cpp.md).  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="overrideandfinal"></a> override und final  
 Hierzu gab es eine kurze, jedoch schwierige Entwicklung. In [Version 0.8](http://go.microsoft.com/fwlink/p/?LinkID=235108) gab es ursprünglich \[\[`override`\]\], \[\[`hiding`\]\] und \[\[`base_check`\]\]\-Attribute.  Anschließend wurden in [Version 0.9](http://go.microsoft.com/fwlink/p/?LinkID=235109) die Attribute entfernt und durch kontextbedingte Schlüsselwörter ersetzt.  In [Version 1.0](http://go.microsoft.com/fwlink/p/?LinkID=235110) wurden sie schließlich für Klassen auf „`final`“ und für Funktionen auf „`override`“ und „`final`“ reduziert.  Dadurch ergab sich eine aufsteigende Erweiterung, da Visual C\+\+ in Visual Studio 2010 diese „`override`“\-Syntax für Funktionen bereits unterstützte und sich die Semantik eng an die in C\+\+11 anlehnte.  „`final`“ wurde ebenfalls unterstützt, jedoch mit der abweichenden Bezeichnung „sealed“.  Die Standardschreibweise und die Semantik von "`override`" und "`final`" werden nun vollständig unterstützt. Weitere Informationen finden Sie unter [override\-Bezeichner](../cpp/override-specifier.md) und [final\-Bezeichner](../cpp/final-specifier.md).  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="atomics"></a> Atomics und mehr  
 [Atomics](http://go.microsoft.com/fwlink/p/?LinkID=235111), [starke compare\_exchange\-Operation](http://go.microsoft.com/fwlink/p/?LinkID=235112), [bidirektionale Fences](http://go.microsoft.com/fwlink/p/?LinkID=235113) und [Datenabhängigkeits\-Reihenfolge](http://go.microsoft.com/fwlink/p/?LinkID=235114) sind Elemente der Standardbibliothek, die nun implementiert sind.  
  
 **Verwandte STL\-Header:** [\<atomic\>](../standard-library/atomic.md), [\<chrono\>](../standard-library/chrono.md), [\<condition\_variable\>](../standard-library/condition-variable.md), [\<future\>](../standard-library/future.md), [\<mutex\>](../standard-library/mutex.md), [\<ratio\>](../standard-library/ratio.md), [\<scoped\_allocator\>](../standard-library/scoped-allocator.md) und [\<thread\>](../standard-library/thread.md).  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="c99"></a> C99 \_\_func\_\_ und Präprozessorregeln  
 In der Tabelle [Features der C++11-Kernsprache: C99](#c99table) ist eine „partielle“ Implementierung für zwei Elemente aufgelistet. Für den vordefinierten Bezeichner `__func__` ist "partiell" aufgeführt, da die Unterstützung für die Nicht\-Standarderweiterungen `__FUNCDNAME__`, `__FUNCSIG__` und `__FUNCTION__` bereitgestellt wird. Weitere Informationen finden Sie unter [Vordefinierte Makros](../preprocessor/predefined-macros.md). Für C99\-Präprozessorregeln ist "partiell" aufgeführt, weil *variadic\-Makros* unterstützt werden. Weitere Informationen finden Sie unter [Variadic\-Makros](../preprocessor/variadic-macros.md).  
  
 \[[In diesem Artikel](#top)\]  
  
###  <a name="stl"></a> Standardbibliotheksfeatures  
 Dies betrifft die Kernsprache. Für die C\+\+11\-Standardbibliothek existiert keine Funktionsvergleichstabelle, aber [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] implementiert sie, mit zwei Ausnahmen.  Wenn eine Bibliotheksfunktion von Funktionen abhing, die im Compiler fehlten, wurde sie zunächst entweder simuliert – z. B. simulierte variadic\-Vorlagen für `make_shared<T>()` – oder sie wurde nicht implementiert. \(Es gab nur einige Fälle, vor allem `<initializer_list>`, die jetzt vollständig in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] implementiert sind\).  Mit sehr wenigen Ausnahmen ist C99 in [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] implementiert, und C\+\+\-Wrapperheader werden bereitgestellt. Weitere Informationen finden Sie im Abschnitt zur [Unterstützung der C99\-Bibliothek in Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkId=321308).  
  
 Hier ist eine partielle Liste der Änderungen in [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] und [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)]:  
  
 **Emplacement:** Wie von C\+\+11 gefordert, wurden `emplace()`\/`emplace_front()`\/`emplace_back()`\/`emplace_hint()`\/`emplace_after()` in allen Containern für eine "beliebige" Anzahl von Argumenten implementiert \(siehe Abschnitt "Simulierte variadics"\).  Beispielsweise wird durch `vector<T>` mit "`template <typename... Args> void emplace_back(Args&&... args)`" direkt ein Element vom Typ T an den Vektor angefügt, mit einer beliebigen Anzahl von beliebigen Argumenten.  Dies kann effizienter sein als `push_back(T&&)`, weil hierbei eine zusätzliche Verschiebungskonstruktion und deren Zerstörung beteiligt sind.  
  
 **Variadics:** [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] verfügte über ein Schema zum Simulieren von variadic\-Vorlagen. In [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] sind keine Simulationen mehr vorhanden und **variadics sind vollständig implementiert**. Wenn der Code auf dem alten simulierten variadics\-Verhalten basiert, müssen Sie ihn korrigieren. Der Wechsel zu realen variadic\-Vorlagen bringt **verbesserte Kompilierzeiten** und **reduzierten Compilerspeicherverbrauch** mit sich.  
  
 **Explizite Konvertierungsoperatoren:** In der Kernsprache stellen explizite Konvertierungsoperatoren eine allgemeine Funktion dar – z. B. ist `explicit operator MyClass()` möglich. Allerdings verwendet die Standardbibliothek derzeit nur ein Formular: `explicit operator bool()`, sodass Klassen sicher auf den Booleschen Wert getestet werden können. \(Einfaches "`operator bool()`" ist offenkundig risikoreich.\) Zuvor simulierte Visual C\+\+ `explicit operator bool()` mit `operator pointer-to-member()`, die zu einigen Problemen und Ineffizienz führten. Jetzt wird diese unzulängliche Problemumgehung vollständig entfernt.  
  
 **Zufallszahlen:** `uniform_int_distribution` ist jetzt perfekt zufällig, und `shuffle()` wurde in `<algorithm>` implementiert, das direkt Uniform Random Number\-Generatoren wie `mersenne_twister` akzeptiert.  
  
 **Verhinderung überladener address\-of\-Operatoren:** C\+\+98\/03 verbietet, dass ein Element eines STL\-Containers seinen address\-of\-Operator überlädt.  Dies erfolgt aber in Klassen wie `CComPtr`, sodass Hilfsklassen wie `CAdapt` erforderlich sind, um STL gegen solche Überladungen abzuschirmen.  Während der Entwicklung von Visual C\+\+ in Visual Studio 2010 haben STL\-Änderungen bewirkt, dass überladene address\-of\-Operatoren in weiteren Situationen abgelehnt wurden. C\+\+11 ändert die Anforderungen, damit überladene address\-of\-Operator möglich werden. C\+\+11 und Visual C\+\+ in Visual Studio 2010 stellen die Hilfsfunktion `std::addressof()` bereit, welche die tatsächliche Adresse eines Objekts auch bei einer Operatorüberladung abrufen kann.  Bevor Visual C\+\+ in Visual Studio 2010 freigegeben wurde, haben wir versucht, Vorkommen von "`&elem`" durch "`std::addressof(elem)`" zu ersetzen, was weiterhin geeignet ist.[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] ging noch weiter, sodass Klassen, die ihren address\-of\-Operator überladen, innerhalb der STL verwendbar sein sollten.  
  
 **[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] ging in verschiedener Hinsicht über C\+\+11 hinaus:**  
  
 **SCARY\-Iteratoren:** Obwohl vom C\+\+11\-Standard nicht gefordert, aber erlaubt, wurden SCARY\-Iteratoren implementiert, wie in [N2911 „Minimizing Dependencies within Generic Classes for Faster and Smaller Programs“](http://go.microsoft.com/fwlink/p/?LinkID=235115) und [N2980 „SCARY Iterator Assignment and Initialization, Revision 1“](http://go.microsoft.com/fwlink/p/?LinkID=235116) beschrieben.  
  
 **Dateisystem:** Der `<filesystem>`\-Header aus [dem TR2\-Antrag](http://go.microsoft.com/fwlink/p/?LinkID=235117) wurde hinzugefügt. Er bietet `recursive_directory_iterator` und weitere interessante Features.  Bevor die Arbeit an TR2 eingestellt wurde, da C\+\+0x sehr spät kam und sich zu C\+\+11 entwickelt hat, wurde der Antrag aus 2006 von [Boost.Filesystem V2](http://go.microsoft.com/fwlink/p/?LinkID=235118) abgeleitet. Dies hat sich später zu Boost.Filesystem V3 entwickelt, das in Visual Studio 2015 implementiert ist.  
  
 Und eine wichtige Optimierung\!  Alle unsere Container sind jetzt entsprechend ihren aktuellen Darstellungen optimal klein.  Dies bezieht sich auf die Containerobjekte selbst, nicht auf die darin referenzierten Inhalte.  Beispielsweise enthält `std::vector` drei unformatierte Zeiger.  In Visual C\+\+ in Visual Studio 2010, im x86\-Releasemodus, umfasste `std::vector` 16 Bytes.  In [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] sind es 12 Bytes, eine optimale Größe.  Dies ist schon beachtlich. Wenn ein Programm 100.000 Vektoren enthält, benötigt [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] 400.000 Bytes weniger.  Verringerte Speicherauslastung spart Platz und Zeit.  
  
 Dies wurde erreicht, weil leere Allokatoren und Komparatoren nicht mehr gespeichert werden, da `std::allocator` und `std::less` zustandslos sind.  \(Diese Optimierungen sind auch für benutzerdefinierte Allokatoren\/Komparatoren aktiviert, solange sie zustandslos sind.  Selbstverständlich kann die Speicherung von zustandsbehafteten Allokatoren\/Komparatoren nicht vermieden werden; diese sind jedoch sehr selten\).  
  
 **[!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] implementiert einige wichtige C \+\+ 14\-Bibliotheksfunktionen:**  
  
-   Transparente "Operatorfunktionselemente" `less<>`, `greater<>`, `plus<>`, `multiplies<>` usw.  
  
-   `make_unique<T>(args...)` und `make_unique<T[]>(n)`  
  
-   `cbegin()`\/`cend()`, `rbegin()`\/`rend()` und `crbegin()`\/`crend()`\-nicht\-Memberfunktionen.  
  
 \[[In diesem Artikel](#top)\]  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)   
 [Bereichsbasiert für Anweisung \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)   
 [Visual C\+\+\-Team\-Blog](http://blogs.msdn.com/b/vcblog/)   
 [Neues bei Visual C\+\+](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)   
 [Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)