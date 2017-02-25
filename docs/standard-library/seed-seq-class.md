---
title: "seed_seq-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::seed_seq"
  - "std::tr1::seed_seq"
  - "tr1.seed_seq"
  - "seed_seq"
  - "std.tr1.seed_seq"
  - "random/std::tr1::seed_seq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "seed_seq-Klasse"
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# seed_seq-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Speichert einen Vektor ganzzahliger Werte ohne Vorzeichen, die einen zufällig festgelegten Startwert für ein Zufallszahlenmodul angeben können.  
  
## Syntax  
  
```  
class seed_seq  
{  
public:  
    // types  
    typedef unsigned int result_type;  
  
    // constructors  
    seed_seq();  
  
    template<class T>  
    seed_seq(initializer_list<T> initlist);  
  
    template<class InputIterator>  
    seed_seq(InputIterator begin, InputIterator end);  
  
    // generating functions  
    template<class RandomAccessIterator>  
    void generate(RandomAccessIterator begin, RandomAccessIterator end);  
  
    // property functions  
    size_t size() const;  
  
    template<class OutputIterator>  
    void param(OutputIterator dest) const;  
  
    // no copy functions  
    seed_seq(const seed_seq&) = delete;  
    void operator=(const seed_seq&) = delete;  
};  
```  
  
## Typen  
 `typedef unsigned int result_type;`   
Der Typ der Elemente der Sequenz Ausgangswert. Ein 32\-Bit\-Ganzzahl ohne Vorzeichen.  
  
## Konstruktoren  
 `seed_seq();`   
Standardkonstruktor, initialisiert auf eine leere interne Sequenz haben.  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
Verwendet `initlist` um die interne Sequenz festzulegen.  
`T` ein Ganzzahltyp muss sein.  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
Initialisiert die interne Sequenz mithilfe aller Elemente im bereitgestellten eingabeiteratorbereich.  
`iterator_traits<InputIterator>::value_type` muss ein Ganzzahltyp sein.  
  
## Mitglieder  
  
### Erstellen von Funktionen  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin, RandomAccessIterator end);`   
Füllt die Elemente der bereitgestellten Sequenz mithilfe eines internen Algorithmus. Dieser Algorithmus wird von der internen Sequenz mit dem beeinflusst `seed_seq` wurde initialisiert.  
Bewirkt nichts, wenn `begin == end`.  
  
### Eigenschaftenfunktionen  
 `size_t size() const;`   
Gibt die Anzahl der Elemente in der `seed_seq`.  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
Kopiert die interne Sequenz in der Output\-Iterator `dest`.  
  
## Beispiel  
 Das folgende Codebeispiel führt die drei Konstruktoren aus und erzeugt eine Ausgabe aus den resultierenden `seed_seq`\-Instanzen, wenn sie einem Array zugeordnet sind. Ein Beispiel für die `seed_seq` mit einem Zufallszahlengenerator finden Sie unter [\<random\>](../standard-library/random.md).  
  
```cpp  
#include <iostream>  
#include <random>  
#include <string>  
#include <array>  
  
using namespace std;  
  
void test(const seed_seq& sseq) {  
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;  
  
    cout << "seed_seq::param(): ";  
    ostream_iterator<unsigned int> out(cout, " ");  
    sseq.param(out);  
    cout << endl;  
  
    cout << "Generating a sequence of 5 elements into an array: " << endl;  
    array<unsigned int, 5> seq;  
    sseq.generate(seq.begin(), seq.end());  
    for (unsigned x : seq) { cout << x << endl; }  
}  
  
int main()  
{  
    seed_seq seed1;  
    test(seed1);  
  
    seed_seq seed2 = { 1701, 1729, 1791 };  
    test(seed2);  
  
    string sstr = "A B C D"; // seed string  
    seed_seq seed3(sstr.begin(), sstr.end());  
    test(seed3);  
}  
```  
  
## Ausgabe  
  
```Output  
  
seed_seq::Size(): 0 seed_seq::param(): generiert eine Sequenz von 5 Elementen in einem Array: 505382999 163489202 3932644188 763126080 73937346 seed_seq::size(): 3 seed_seq::param(): 1701 1729 1791 generiert eine Sequenz von 5 Elementen in einem Array: 1730669648 1954224479 2809786021 1172893117 2393473414 seed_seq::size(): 7 seed_seq::param(): 65 32 66 32 67 32 68 generiert eine Sequenz von 5 Elementen in einem Array : 3139879222 3775111734 1084804564 2485037668 1985355432  
```  
  
## Hinweise  
 Memberfunktionen dieser Klasse lösen keine Ausnahmen.  
  
## Anforderungen  
 **Header:** \<random\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<random\>](../standard-library/random.md)