---
title: '&lt;set&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<set>
- std::<set>
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 1295a8c71464b7cc9d204c807c3492000b73ffa1
ms.lasthandoff: 02/24/2017

---
# <a name="ltsetgt"></a>&lt;set&gt;
Definiert die Containervorlagenklassen "set" und "multiset" und deren unterstützende Vorlagen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="operators"></a>Operatoren  
  
|set-Version|multiset-Version|Beschreibung|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#operator_neq)|[operator!= (multiset)](../standard-library/set-operators.md#operator_neq)|Überprüft, ob das set- oder multiset-Objekt links vom Operator ungleich dem set- oder multiset-Objekt rechts vom Operator ist.|  
|[operator< (set)](../standard-library/set-operators.md#operator_lt_)|[operator< (multiset)](../standard-library/set-operators.md#operator_lt_)|Überprüft, ob das set- oder multiset-Objekt links vom Operator kleiner als das set- oder multiset-Objekt rechts vom Operator ist.|  
|[operator<= (set)](../standard-library/set-operators.md#operator_lt__eq)|[operator\<= (multiset)](../standard-library/set-operators.md#operator_lt__eq)|Überprüft, ob das set- oder multiset-Objekt links vom Operator kleiner gleich dem set- oder multiset-Objekt rechts vom Operator ist.|  
|[operator== (set)](../standard-library/set-operators.md#operator_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#operator_eq_eq)|Überprüft, ob das set- oder multiset-Objekt links vom Operator gleich dem set- oder multiset-Objekt rechts vom Operator ist.|  
|[operator> (set)](../standard-library/set-operators.md#operator_gt_)|[operator> (multiset)](../standard-library/set-operators.md#operator_gt_)|Überprüft, ob das set- oder multiset-Objekt links vom Operator größer als das set- oder multiset-Objekt rechts vom Operator ist.|  
|[operator>= (set)](../standard-library/set-operators.md#operator_gt__eq)|[operator>= (multiset)](../standard-library/set-operators.md#operator_gt__eq)|Überprüft, ob das set- oder multiset-Objekt links vom Operator größer gleich dem set- oder multiset-Objekt rechts vom Operator ist.|  
  
### <a name="specialized-template-functions"></a>Spezialisierte Vorlagenfunktionen  
  
|set-Version|multiset-Version|Beschreibung|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap](../standard-library/set-functions.md#swap)|Tauscht die Elemente von zwei set- oder multiset-Objekten aus.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[set-Klasse](../standard-library/set-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|  
|[multiset-Klasse](../standard-library/multiset-class.md)|Wird zum Speichern von Daten in und zum Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente nicht eindeutig sein müssen und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




