---
title: "time_put-Klasse"
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
  - "std::time_put"
  - "time_put"
  - "xloctime/std::time_put"
  - "std.time_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put-Klasse"
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# time_put-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Zeitwerten in Sequenzen vom Typ `CharType` zu steuern.  
  
## Syntax  
  
```  
template <  
   class CharType,  
   class OutputIterator = ostreambuf_iterator<CharType>  
> class time_put : public locale::facet;  
```  
  
#### Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `OutputIterator`  
 Der Typ des Iterators, in den die Time\-Put\-Funktionen ihre Ausgabe schreiben.  
  
## Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt\-ID einen anfänglichen gespeicherten Wert von NULL.  Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in **ID** gespeichert.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[time\_put](../Topic/time_put::time_put.md)|Der Konstruktor für Objekte des Typs `time_put`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/time_put::char_type.md)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter\_type](../Topic/time_put::iter_type.md)|Ein Typ, der einen Ausgabeiterator beschreibt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[do\_put](../Topic/time_put::do_put.md)|Eine virtuelle Funktion, die Zeit\- und Datumsinformationen als Sequenz von `CharType`\-Objekten ausgibt.|  
|[put](../Topic/time_put::put.md)|Gibt Zeit\- und Datumsinformationen als Sequenz von `CharType`\-Objekten aus.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base\-Klasse](../standard-library/time-base-class.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)