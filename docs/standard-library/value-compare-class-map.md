---
title: "value_compare-Klasse (&lt;map&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::value_compare"
  - "std.value_compare"
  - "map/std::value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare-Klasse"
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# value_compare-Klasse (&lt;map&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen, um ihre relative Position in der Zuordnung zu bestimmen.  
  
## Syntax  
  
```  
class value_compare : public binary_function<value_type, value_type, bool>  
{  
public:  
   bool operator()(const value_type& _Left, const value_type& _Right) const;  
   value_compare(key_compare _Pred) : comp(_Pred);  
   protected:  
      key_compare comp;  
};  
```  
  
## Hinweise  
 Das Vergleichskriterium, das von `value_compare` zwischen **value\_types** aus ganzen Elementen enthalten werden durch eine Zuordnung bereitgestellt wird, wird ein Vergleich zwischen den Schlüsseln der jeweiligen Elemente durch die Erweiterungsklassenkonstruktion verursacht.  Der Memberfunktionsoperator verwendet das Objekt **Komp.** vom Typ `key_compare` gespeichert im Funktionsobjekt, das von `value_compare` bereitgestellt wird, um die Sortierschlüsselkomponenten von zwei Elementen zu vergleichen.  
  
 Für Sätze und Multisets die einfache Container sind, in die die Schlüsselwerte zu Elementwerten identisch sind, ist `value_compare` gleich bedeutend mit `key_compare`; für Zuordnungen und Multimaps sind sie nicht, da der Wert der `pair`\-Typ keine Elemente auf den Wert des Schlüssels des Elements identisch ist.  
  
## Beispiel  
 Siehe Beispiels für [value\_comp](../Topic/map::value_comp.md) als Beispiel dafür, wie ein `value_compare` deklariert und verwendet.  
  
## Anforderungen  
 **Header:** \<map\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [binary\_function\-Struktur](../standard-library/binary-function-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)