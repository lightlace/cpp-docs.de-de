---
title: "pair-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "utility/std::pair"
  - "pair"
  - "std::pair"
  - "std.pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair-Klasse"
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# pair-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Struktur, die die Möglichkeit bietet, zwei Objekte als ein einzelnes Objekt zu behandeln.  
  
## Syntax  
  
```  
template<class T1, class T2>  
   struct pair   
   {  
   typedef T1 first_type;  
   typedef T2 second_type;  
   T1 first;  
   T2 second;  
  
   constexpr pair( );  
   constexpr pair(  
      const T1& Val1,   
      const T2& Val2  
   );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         const pair<Other1, Other2>& Right  
      );  
  
template<class Other1, class Other2>  
      constexpr pair(  
        const pair <Other1 Val1, Other2 Val2>&& Right  
      );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         Other1&& Val1, Other2&& Val2  
      );  
   };  
```  
  
#### Parameter  
 `Val1`  
 Der Wert, der das erste Element von `pair` initialisiert.  
  
 `Val2`  
 Der Wert, der das zweite Element von `pair` initialisiert.  
  
 `Right`  
 Ein Paar, dessen Werte verwendet werden, um die Elemente eines anderen Paars zu initialisieren.  
  
## Rückgabewert  
 Der erste Konstruktor \(Standardkonstruktor\) initialisiert das erste Element des Paars auf den Standardwert des Typs **T1** und das zweite Element auf den Standardwert des Typs **T2**.  
  
 Der zweite Konstruktor initialisiert das erste Element des Paars auf `Val1` und das zweite auf *Val2*.  
  
 Der dritte Konstruktor \(Vorlagenkonstruktor\) initialisiert das erste Element des Paars auf `Right`.**first** und das zweite auf `Right`.**second**.  
  
 Der vierte Konstruktor initialisiert das erste Element des Paars auf `Val1` und das zweite auf *Val2*, wozu er [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md) verwendet.  
  
## Hinweise  
 Die Vorlagenstruktur speichert ein Paar von Objekten des Typs **T1** bzw. **T2**.  Der Typ **first\_type** ist mit dem Vorlagenparameter **T1** und der Typ **second\_type** ist mit dem Vorlagenparameter **T2** identisch.  **T1** und **T2** müssen jeweils nur einen Standardkonstruktor, einen Einzelargumentkonstruktor und einen Destruktor bereitstellen.  Alle Member des Typs `pair` sind öffentlich, da der Typ als `struct` statt als **Klasse** deklariert ist.  Die beiden häufigsten Einsatzfälle für ein Paar sind, es als Rückgabetyp für eine Funktion zu verwenden, die zwei Werte zurückgibt, oder es als Element für die assoziativen Containerklassen [map\-Klasse](../standard-library/map-class.md) und [multimap\-Klasse](../standard-library/multimap-class.md) zu verwenden, die beide einen Schlüssel und einen Werttyp haben, die jedem Element zugeordnet sind.  Die zweite Verwendung erfüllt die Anforderungen für einen paarweise assoziativen Container und hat einen Werttyp der Form `pair`\<**const**`key_type``mapped_type`\>.  
  
## Beispiel  
  
```  
// utility_pair.cpp  
// compile with: /EHsc  
#include <utility>  
#include <map>  
#include <iomanip>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Using the constructor to declare and initialize a pair  
   pair <int, double> p1 ( 10, 1.1e-2 );  
  
   // Compare using the helper function to declare and initialize a pair  
   pair <int, double> p2;  
   p2 = make_pair ( 10, 2.22e-1 );  
  
   // Making a copy of a pair  
   pair <int, double> p3 ( p1 );  
  
   cout.precision ( 3 );  
   cout << "The pair p1 is: ( " << p1.first << ", "   
        << p1.second << " )." << endl;  
   cout << "The pair p2 is: ( " << p2.first << ", "   
        << p2.second << " )." << endl;  
   cout << "The pair p3 is: ( " << p3.first << ", "   
        << p3.second << " )." << endl;  
  
   // Using a pair for a map element  
   map <int, int> m1;  
   map <int, int>::iterator m1_Iter;  
  
   typedef pair <int, int> Map_Int_Pair;  
  
   m1.insert ( Map_Int_Pair ( 1, 10 ) );  
   m1.insert ( Map_Int_Pair ( 2, 20 ) );  
   m1.insert ( Map_Int_Pair ( 3, 30 ) );  
  
   cout << "The element pairs of the map m1 are:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " ( " << m1_Iter -> first << ", "  
           << m1_Iter -> second << " )";  
   cout   << "." << endl;  
  
   // Using pair as a return type for a function  
   pair< map<int,int>::iterator, bool > pr1, pr2;  
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );  
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );  
  
   if( pr1.second == true )  
   {  
      cout << "The element (4,40) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
  
   if( pr2.second == true )  
   {  
      cout << "The element (1,10) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
}  
```  
  
  **The pair p1 is: \( 10, 0.011 \).  The pair p2 is: \( 10, 0.222 \).  The pair p3 is: \( 10, 0.011 \).  The element pairs of the map m1 are: \( 1, 10 \) \( 2, 20 \) \( 3, 30 \).  The element \(4,40\) was inserted successfully in m1.  The element with a key value of**  
 **\( \(pr2.first\) \-\> first \) \= 1 is already in m1,**  
 **so the insertion failed.**    
## Anforderungen  
 **Header:** \<utility\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Logischer Operator für Objektpaare](../misc/pair-logical-operator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)