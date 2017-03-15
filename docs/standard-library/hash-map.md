---
title: '&lt;hash_map&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<hash_map>
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 3f9a4705d946831ddee15116676fde9e433288f7
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Dieser Header ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map.md).  
  
 Definiert die Containervorlagenklassen „hash_map“ und „hash_multimap“ und deren unterstützende Vorlagen.  
  
 In Visual C++ .NET 2003 sind Member der <hash_map> und <hash_set> Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Operatoren  
  
|Hash_map-Version|Hash_multimap-Version|Beschreibung|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#operator_neq__hash_map_)|[operator!= (hash_multimap)](../standard-library/hash-map-operators.md#operator_neq)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator ungleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|  
|[operator== (hash_map)](http://msdn.microsoft.com/en-us/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator== (hash_multimap)](http://msdn.microsoft.com/en-us/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Überprüft, ob das hash_map- oder hash_multimap-Objekt links vom Operator gleich dem hash_map- oder hash_multimap-Objekt rechts vom Operator ist.|  
  
### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen  
  
|Hash_map-Version|Hash_multimap-Version|Beschreibung|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#hash_map__swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#hash_multimap__swap)|Tauscht die Elemente zweier hash_map- oder hash_multimap-Objekte aus.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[hash_compare-Klasse](../standard-library/hash-compare-class.md)|Beschreibt ein Objekt, das von jedem hashassoziativen Container – hash_map, hash_multimap, hash_set oder hash_multiset – als standardmäßiges **Traits** -Parameterobjekt verwendet werden kann, um die darin enthaltenen Elemente zu sortieren und zu hashen.|  
|[value_compare-Klasse](../standard-library/value-compare-class.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer hash_map vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der hash_map zu bestimmen.|  
|[hash_map-Klasse](../standard-library/hash-map-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel mit eindeutigem Wert und einen zugeordneten Datenwert aufweist.|  
|[hash_multimap-Klasse](../standard-library/hash-multimap-class.md)|Speichert Daten und ruft sie schnell aus einer Auflistung ab, in der jedes Element ein Paar ist, das einen Sortierschlüssel, dessen Wert nicht eindeutig sein muss, und einen zugeordneten Datenwert aufweist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<hash_map>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




