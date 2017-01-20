---
title: "&lt; Vektor &gt;"
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
  - "<vector>"
  - "std.<vector>"
  - "std::<vector>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector-Header"
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
caps.handback.revision: "25"
ms.author: "corob"
manager: "ghogen"
---
# &lt; Vektor &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert den Containervorlagenklassenvektor und einige unterstützende Vorlagen.  
  
 Der `vector` ist ein Container, der Elemente eines bestimmten Typs in einer linearen Sequenz organisiert. Er ermöglicht schnellen zufälligen Zugriff auf alle Elemente sowie dynamische Hinzufügungen und Entfernungen zu und aus der Sequenz. Der `vector` ist der bevorzugte Container für eine Sequenz, wenn die Leistung mit wahlfreiem Zugriff ein wichtiger Faktor ist.  
  
 Weitere Informationen über die Klasse `vector`, finden Sie unter [Vektorklasse](vector%20Class.md). Informationen zu der Spezialisierung `vector<bool>`, finden Sie unter [Vector \< Bool> Klasse](../standard-library/vector-bool-class.md).  
  
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
  
 ` left`  
 Der erste (linke) Vektor in einem Vergleichsvorgang.  
  
 ` right`  
 Der zweite (rechte) Vektor in einem Vergleichsvorgang.  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator! =](../Topic/%3Cvector%3E%20operators.md#operator_neq)|Testet, ob das Vektorobjekt links vom Operator ungleich dem Vektorobjekt rechts vom Operator ist.|  
|[Operator <](../Topic/%3Cvector%3E%20operators.md#operator_lt_)|Testet, ob das Vektorobjekt links vom Operator kleiner als das Vektorobjekt auf der rechten Seite ist.|  
|[Operator \< =](../Topic/%3Cvector%3E%20operators.md#operator_lt__eq)|Testet, ob das Vektorobjekt links vom Operator kleiner als oder gleich dem Vektorobjekt rechts vom Operator ist.|  
|[Operator ==](../Topic/%3Cvector%3E%20operators.md#operator_eq_eq)|Testet, ob das Vektorobjekt links vom Operator gleich dem Vektorobjekt rechts vom Operator ist.|  
|[Operator >](../Topic/%3Cvector%3E%20operators.md#operator_gt_)|Testet, ob das Vektorobjekt links vom Operator größer als das Vektorobjekt auf der rechten Seite ist.|  
|[Operator > =](../Topic/%3Cvector%3E%20operators.md#operator_gt__eq)|Testet, ob das Vektorobjekt links vom Operator größer als oder gleich dem Vektorobjekt rechts vom Operator ist.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[Vector-Klasse](vector%20Class.md)|Eine Vorlagenklasse von Sequenzcontainern, die Elemente eines bestimmten Typs in einer linearen Anordnung anordnen und schnellen zufälligen Zugriff auf ein Element ermöglichen.|  
  
### <a name="specializations"></a>Spezialisierungen  
  
|||  
|-|-|  
|[Vector \< Bool> Klasse](../standard-library/vector-bool-class.md)|Eine vollständige Spezialisierung des Vorlagenklassenvektors für Elemente des Typs `bool` mit einer Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Vektor>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

