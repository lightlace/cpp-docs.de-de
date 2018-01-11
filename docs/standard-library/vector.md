---
title: '&lt;vector&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <vector>
dev_langs: C++
helpviewer_keywords: vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ac628b660c37c4d281c1b889ccf5a3628240573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltvectorgt"></a>&lt;vector&gt;
Definiert den Containervorlagenklassenvektor und einige unterstützende Vorlagen.  
  
 Der `vector` ist ein Container, der Elemente eines bestimmten Typs in einer linearen Sequenz organisiert. Er ermöglicht schnellen zufälligen Zugriff auf alle Elemente sowie dynamische Hinzufügungen und Entfernungen zu und aus der Sequenz. Der `vector` ist der bevorzugte Container für eine Sequenz, wenn die Leistung mit wahlfreiem Zugriff ein wichtiger Faktor ist.  
  
 Weitere Informationen zur `vector`-Klasse finden Sie unter [vector-Klasse](../standard-library/vector-class.md). Weitere Informationen zu der Spezialisierung `vector<bool>` finden Sie unter [vector\<bool>-Klasse](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Parameter  
 Typ  
 Der Vorlagenparameter für den Typ der Daten, die im Vektor gespeichert sind.  
  
 Zuweisung  
 Der Vorlagenparameter für das gespeicherte Zuweisungsobjekt, das für die Speicherbelegung und -freigabe verantwortlich ist.  
  
 `left`  
 Der erste (linke) Vektor in einem Vergleichsvorgang.  
  
 `right`  
 Der zweite (rechte) Vektor in einem Vergleichsvorgang.  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator! =](../standard-library/vector-operators.md#op_neq)|Testet, ob das Vektorobjekt links vom Operator ungleich dem Vektorobjekt rechts vom Operator ist.|  
|[operator<](../standard-library/vector-operators.md#op_lt)|Testet, ob das Vektorobjekt links vom Operator kleiner als das Vektorobjekt auf der rechten Seite ist.|  
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|Testet, ob das Vektorobjekt links vom Operator kleiner als oder gleich dem Vektorobjekt rechts vom Operator ist.|  
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|Testet, ob das Vektorobjekt links vom Operator gleich dem Vektorobjekt rechts vom Operator ist.|  
|[operator>](../standard-library/vector-operators.md#op_gt)|Testet, ob das Vektorobjekt links vom Operator größer als das Vektorobjekt auf der rechten Seite ist.|  
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|Testet, ob das Vektorobjekt links vom Operator größer als oder gleich dem Vektorobjekt rechts vom Operator ist.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[vector-Klasse](../standard-library/vector-class.md)|Eine Vorlagenklasse von Sequenzcontainern, die Elemente eines bestimmten Typs in einer linearen Anordnung anordnen und schnellen zufälligen Zugriff auf ein Element ermöglichen.|  
  
### <a name="specializations"></a>Spezialisierungen  
  
|||  
|-|-|  
|[vector\<bool>-Klasse](../standard-library/vector-bool-class.md)|Eine vollständige Spezialisierung des Vorlagenklassenvektors für Elemente des Typs `bool` mit einer Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<vector>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)

