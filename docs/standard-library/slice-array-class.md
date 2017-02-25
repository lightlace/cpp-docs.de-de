---
title: "slice_array-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "slice_array"
  - "valarray/std::slice_array"
  - "std.slice_array"
  - "std::slice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice_array-Klasse"
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# slice_array-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine interne, zusätzliche Vorlagenklasse, die Sliceobjekte unterstützt, indem Vorgänge zwischen Teilmengenarrays bereitstellt, definierte durch den Segment eines Wertarrays.  
  
## Syntax  
  
```  
template<class Type>  
   class slice_array : public slice {  
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
 Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt der Klasse [Array von Werten](../standard-library/valarray-class.md)**\<Typ\>**, zusammen mit einem Objekt der Klasse [Segment](../standard-library/slice-class.md) speichert, die die Sequenz der Elemente beschrieben, die dem **valarray \<Type\>**\-Objekt auszuwählen.  
  
 Die Vorlagenklasse wird indirekt durch bestimmte Wertarrayvorgänge erstellt und kann nicht direkt im Programm verwendet werden.  Eine interne, zusätzliche Vorlagenklasse, die vom tiefgestellten Operator des Slices verwendet wird:  
  
 ::\<`operator[]` \> \(\<`slice`\)`slice_array`**Typ**`valarray`**Typ**.  
  
 Sie erstellen ein **slice\_array \<Type\>**\-Objekt, indem Sie nur einen Ausdruck des Formulars [VA &#91;SL&#93;](../Topic/valarray::operator.md), für ein Segment **sl** des Wertarrays **va** schreiben.  Die Memberfunktionen der Klasse slice\_array dann verhalten sich wie die entsprechenden Funktionssignaturen, für die **valarray \<Type\>** definiert werden, dass nur die Reihenfolge der ausgewählten Elemente wird beeinflusst.  Die Sequenz, die vom slice\_array gesteuert wird, wird durch die drei Parameter des Slicekonstruktors, Index des ersten Elements im Segment, der Anzahl von Elementen und des Abstands zwischen Elementen definiert.  Ein slice\_array Ausschneiden vom Wertarray **va** deklariert durch **va**\[`slice`\(2, 5, 3\)\] wählt Elemente mit den Indizes 2, 5, 8, 11 und 14 von **va**.  Die Indizes müssen gültig werden, dass die Prozedur gültig ist.  
  
## Beispiel  
 Im Beispiel für [slice::slice](../Topic/slice::slice.md) als Beispiel, wie ein slice\_array deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<valarray\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)