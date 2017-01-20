---
title: "gslice_array-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std::gslice_array"
  - "gslice_array"
  - "valarray/std::gslice_array"
  - "std.gslice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice_array-Klasse"
ms.assetid: ad1b4514-b14a-4baf-a293-d5a8e8674c75
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# gslice_array-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine interne, zusätzliche Vorlagenklasse, die allgemeine Segment unterstützt, \- Objekt, indem diese Vorgänge zwischen den Teilmengenarrays bereitstellt, die von den allgemeinen Segment eines Wertarrays definiert werden.  
  
## Syntax  
  
```  
template<class Type>  
   class gslice_array : public gsplice {  
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
 Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt **va** der Klasse [Array von Werten](../standard-library/valarray-class.md)**\<Typ\>** speichert, zusammen mit einem Objekt **gs** der [gslice](../standard-library/gslice-class.md), die die Sequenz der Elemente beschrieben, die dem **valarray \<Type\>**\-Objekt auszuwählen.  
  
 Sie erstellen ein **gslice\_array \<Type\>**\-Objekt, indem Sie nur einen Ausdruck des Formulars [VA &#91;gs&#93;](../Topic/valarray::operator.md) schreiben.  Die Memberfunktionen der Klasse gslice\_array dann verhalten sich wie die entsprechenden Funktionssignaturen, für die **valarray \<Type\>** definiert werden, dass nur die Reihenfolge der ausgewählten Elemente wird beeinflusst.  
  
 Die Vorlagenklasse wird indirekt durch bestimmte Wertarrayvorgänge erstellt und kann nicht direkt im Programm verwendet werden.  Eine interne zusätzliche Vorlagenklasse stattdessen wird vom tiefgestellten Operator des Slices verwendet:  
  
 ::`operator[]` \(**const**\)**gslice &**`gslice_array`\<**Typ**\>`valarray`\<**Typ**\>.  
  
 Sie erstellen ein **gslice\_array \<Type\>**\-Objekt, indem Sie nur einen Ausdruck des Formulars **va\[gsl\]**, **gsl** für ein Segment des Wertarrays **va** schreiben.  Die Memberfunktionen der Klasse gslice\_array dann verhalten sich wie die entsprechenden Funktionssignaturen, für die **valarray \<Type\>** definiert werden, dass nur die Reihenfolge der ausgewählten Elemente wird beeinflusst.  Die Sequenz, die vom gslice\_array gesteuert wird, wird durch die drei Parameter des Slicekonstruktors, Index des ersten Elements im Anschnitt, der Anzahl der Elemente in jedem Segment und des Abstands zwischen Elementen in einem Segment definiert.  
  
 Beispiel:  
  
```  
const size_t lv[] = {2, 3};  
const size_t dv[] = {7, 2};  
const valarray<size_t> len(lv, 2), str(dv, 2);  
// va[gslice(3, len, str)] selects elements with  
//   indices 3, 5, 7, 10, 12, 14  
```  
  
 Die Indizes müssen gültig werden, dass die Prozedur gültig ist.  
  
## Beispiel  
 Im Beispiel für [gslice::gslice](../Topic/gslice::gslice.md) als Beispiel, wie ein slice\_array deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<valarray\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)