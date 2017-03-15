---
title: '&lt;map&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<map>
- std.<map>
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: fad398e9f18c2f45de7e071be464e3eff2e9243e
ms.lasthandoff: 02/24/2017

---
# <a name="ltmapgt"></a>&lt;map&gt;
Definiert die Containervorlagenklassen "map" und "multimap" und deren unterstützende Vorlagen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <map>  
  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="operators"></a>Operatoren  
  
|map-Version|multimap-Version|Beschreibung|  
|-----------------|----------------------|-----------------|  
|[operator!= (map)](../standard-library/map-operators.md#operator_neq)|[operator!= (multimap)](../standard-library/map-operators.md#operator_neq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator ungleich dem map- oder multimap-Objekt rechts vom Operator ist.|  
|[operator< (map)](../standard-library/map-operators.md#operator_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#operator_eq_eq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator kleiner als das map- oder multimap-Objekt rechts vom Operator ist.|  
|[operator<= (map)](../standard-library/map-operators.md#operator_lt_)|[operator\<= (multimap)](../standard-library/map-operators.md#operator_lt_)|Überprüft, ob das map- oder multimap-Objekt links vom Operator kleiner gleich dem map- oder multimap-Objekt rechts vom Operator ist.|  
|[operator== (map)](../standard-library/map-operators.md#operator_lt__eq)|[operator== (multimap)](../standard-library/map-operators.md#operator_lt__eq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator gleich dem map- oder multimap-Objekt rechts vom Operator ist.|  
|[operator> (map)](../standard-library/map-operators.md#operator_gt_)|[operator> (multimap)](../standard-library/map-operators.md#operator_gt_)|Überprüft, ob das map- oder multimap-Objekt links vom Operator größer als das map- oder multimap-Objekt rechts vom Operator ist.|  
|[operator>= (map)](../standard-library/map-operators.md#operator_gt__eq)|[operator>= (multimap)](../standard-library/map-operators.md#operator_gt__eq)|Überprüft, ob das map- oder multimap-Objekt links vom Operator größer gleich dem map- oder multimap-Objekt rechts vom Operator ist.|  
  
### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen  
  
|map-Version|multimap-Version|Beschreibung|  
|-----------------|----------------------|-----------------|  
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap)|Tauscht die Elemente zweier map- oder multimap-Objekte aus.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[value_compare-Klasse](../standard-library/value-compare-class-map.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der Zuordnung zu bestimmen.|  
|[map-Klasse](../standard-library/map-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen eindeutigen Schlüssel hat, mit dem die Daten automatisch geordnet werden.|  
|[multimap-Klasse](../standard-library/multimap-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen Schlüssel hat, mit dem die Daten automatisch geordnet werden. Die Schlüssel müssen keine eindeutigen Werte haben.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




