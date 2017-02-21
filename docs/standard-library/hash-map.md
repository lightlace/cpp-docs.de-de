---
title: "&lt;hash_map&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<hash_map>"
  - "<hash_map>"
  - "std::<hash_map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map-Header"
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;hash_map&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieser Header ist veraltet. Die Alternative ist [\<unordered\_map\>](../standard-library/unordered-map.md).  
  
 Definiert die Containervorlagenklassen „hash\_map“ und „hash\_multimap“ und deren unterstützende Vorlagen.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](#vclrfhash_map_header_file) und [\<hash\_set\>](../standard-library/hash-set.md)\-Headerdateien nicht mehr im std\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben. Weitere Informationen finden Sie unter [stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
## Syntax  
  
```  
  
#include <hash_map>  
  
```  
  
### Operatoren  
  
|Hash\_map\-Version|Hash\_multimap\-Version|Beschreibung|  
|------------------------|-----------------------------|------------------|  
|[operator\!\= \(hash\_map\)](../Topic/operator!=%20\(hash_map\).md)|[operator\!\= \(hash\_multimap\)](../Topic/operator!=%20\(hash_multimap\).md)|Überprüft, ob das hash\_map\- oder hash\_multimap\-Objekt links vom Operator ungleich dem hash\_map\- oder hash\_multimap\-Objekt rechts vom Operator ist.|  
|[operator\=\= \(hash\_map\)](assetId:///f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator\=\= \(hash\_multimap\)](assetId:///3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Überprüft, ob das hash\_map\- oder hash\_multimap\-Objekt links vom Operator gleich dem hash\_map\- oder hash\_multimap\-Objekt rechts vom Operator ist.|  
  
### Spezialisierte Vorlagenfunktionen  
  
|Hash\_map\-Version|Hash\_multimap\-Version|Beschreibung|  
|------------------------|-----------------------------|------------------|  
|[swap \(hash\_map\)](../Topic/hash_map::swap.md)|[swap \(hash\_multimap\)](../Topic/hash_multimap::swap.md)|Tauscht die Elemente zweier hash\_map\- oder hash\_multimap\-Objekte aus.|  
  
### Klassen  
  
|||  
|-|-|  
|[hash\_compare\-Klasse](../standard-library/hash-compare-class.md)|Beschreibt ein Objekt, das von jedem hashassoziativen Container – hash\_map, hash\_multimap, hash\_set oder hash\_multiset – als standardmäßiges **Traits**\-Parameterobjekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|  
|[value\_compare\-Klasse](../standard-library/value-compare-class.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer hash\_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash\_map zu bestimmen.|  
|[hash\_map\-Klasse](../standard-library/hash-map-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel mit eindeutigem Wert und einen zugeordneten Datenwert aufweist.|  
|[hash\_multimap\-Klasse](../standard-library/hash-multimap-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel, dessen Wert nicht eindeutig sein muss, und einen zugeordneten Datenwert aufweist.|  
  
## Anforderungen  
 **Header:** \<hash\_map\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)