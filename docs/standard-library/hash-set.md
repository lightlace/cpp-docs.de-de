---
title: "&lt;hash_set&gt;"
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
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set-Header"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dieser Header ist veraltet. Die Alternative ist [\<unordered\_set\>](../standard-library/unordered-set.md).  
  
 Definiert die Containervorlagenklassen „hash\_set“ und „hash\_multiset“ und deren unterstützende Vorlagen.  
  
## Syntax  
  
```  
  
#include <hash_set>  
  
```  
  
## Hinweise  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](#vclrfhash_set_header_file) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
### Operatoren  
  
|Hash\_set\-Version|Hash\_multiset\-Version|Beschreibung|  
|------------------------|-----------------------------|------------------|  
|[operator\!\= \(hash\_set\)](../Topic/operator!=%20\(hash_set\).md)|[operator\!\= \(hash\_multiset\)](../Topic/operator!=%20\(hash_multiset\).md)|Überprüft, ob das hash\_set\- oder hash\_multiset\-Objekt links vom Operator ungleich dem hash\_set\- oder hash\_multiset\-Objekt rechts vom Operator ist.|  
|[operator\=\= \(hash\_set\)](assetId:///791b95bd-f917-4716-aea6-add50badbfac)|[operator\=\= \(hash\_multiset\)](assetId:///cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|Überprüft, ob das hash\_set\- oder hash\_multiset\-Objekt links vom Operator gleich dem hash\_set\- oder hash\_multiset\-Objekt rechts vom Operator ist.|  
  
### Spezialisierte Vorlagenfunktionen  
  
|Hash\_set\-Version|Hash\_multiset\-Version|Beschreibung|  
|------------------------|-----------------------------|------------------|  
|[swap \(hash\_set\)](../Topic/swap%20\(hash_set\).md)|[swap \(hash\_multiset\)](../Topic/swap%20\(hash_multiset\).md)|Tauscht die Elemente zweier hash\_sets oder hash\_multisets aus.|  
  
### Klassen  
  
|||  
|-|-|  
|[hash\_compare\-Klasse](../standard-library/hash-compare-class.md)|Beschreibt ein Objekt, das von jedem hashassoziativen Container – hash\_map, hash\_multimap, hash\_set oder hash\_multiset – als standardmäßiges **Traits**\-Parameterobjekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|  
|[hash\_set\-Klasse](../standard-library/hash-set-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|  
|[hash\_multiset\-Klasse](../standard-library/hash-multiset-class.md)|Wird zum Speichern und schnellen Abrufen von Daten aus einer Auflistung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)