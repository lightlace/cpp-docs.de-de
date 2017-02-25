---
title: "mask_array-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.mask_array"
  - "mask_array"
  - "std::mask_array"
  - "valarray/std::mask_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mask_array-Klasse"
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# mask_array-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine interne zusätzliche Vorlagenklasse, die Objekte, die Teilmengen von übergeordneten valarray\-Objekten und mit einem booleschen Ausdruck angegeben sind, dadurch unterstützt, dass sie Vorgänge zwischen den Teilmengenarrays bereitstellt.  
  
## Syntax  
  
```  
template<class Type>  
   class mask_array {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator=(  
      const Type& x  
   ) const;  
  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
  
// The rest is private or implementation defined  
}  
```  
  
## Hinweise  
 Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt **va** der Klasse [valarray](../standard-library/valarray-class.md)**\<Type\>** zusammen mit einem Objekt **ba** der Klasse [valarray\< bool\>](../standard-library/valarray-bool-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die im **valarray\<Type\>**\-Objekt ausgewählt werden sollen.  
  
 Sie erstellen ein **mask\_array\<Type\>**\-Objekt nur, indem Sie einen Ausdruck der Form [va&#91;ba&#93;](../Topic/valarray::operator.md) schreiben. Die Memberfunktionen der Klasse „mask\_array“ verhalten sich dann wie die entsprechenden Funktionssignaturen, die für **valarray\<Type\>** definiert sind, mit der Ausnahme, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.  
  
 Die Reihenfolge besteht aus höchstens **ba.size**\-Elementen. Ein Element *J* ist nur enthalten, wenn **ba**\[*J*\] gleich „true“ ist. Daher gibt es in der Reihenfolge so viele Elemente, wie es „true“\-Elemente in **ba** gibt. Wenn `I` der Index des kleinsten „true“\-Elements in **ba** ist, dann ist **va**\[`I`\] das Element 0 \(null\) in der ausgewählten Reihenfolge.  
  
## Beispiel:  
  
```  
// mask_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Use masked subsets to assign a value of 10  
   // to all elements grrater than 3 in value  
   va [va > 3 ] = 10;  
   cout << "The modified operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### Ausgabe  
  
```  
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The modified operand valarray is:  ( 0 -1 2 -1 10 -1 10 -1 10 -1 ).  
```  
  
## Anforderungen  
 **Header:** \<valarray\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)