---
title: Location-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::location
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1a404f44600addcbf332fabcfc19a7b48dab0c81
ms.lasthandoff: 02/24/2017

---
# <a name="location-class"></a>location-Klasse
Die Abstraktion eines physischen Speicherorts auf der Hardware.  
  
## <a name="syntax"></a>Syntax  
  
```
class location;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Speicherort-Konstruktor](#ctor)|Überladen. Erstellt ein `location`-Objekt.|  
|[~ Location-Destruktor](#dtor)|Zerstört ein `location`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[aktuelle Methode](#current)|Gibt ein `location` Objekt, das die spezifische Stelle den aufrufenden Thread ausgeführt wird, darstellt.|  
|[From_numa_node-Methode](#from_numa_node)|Gibt ein `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator! =-Operator](#operator_neq)|Bestimmt, ob zwei `location` Objekte unterschiedliche Position darstellt.|  
|[Operator =-Operator](#operator_eq)|Weist den Inhalt eines anderen `location` -Objekts diesem Objekt zu.|  
|[Operator ==-Operator](#operator_eq_eq)|Bestimmt, ob zwei `location` Objekte am gleichen Speicherort darstellen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `location`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namedtora-location"></a><a name="dtor"></a>~ Speicherort 

 Zerstört ein `location`-Objekt.  
  
```
~location();
```  
  
##  <a name="a-namecurrenta-current"></a><a name="current"></a>aktuelle 

 Gibt ein `location` Objekt, das die spezifische Stelle den aufrufenden Thread ausgeführt wird, darstellt.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Speicherort, der spezifischen Ort darstellt, wird der aufrufende Thread ausgeführt.  
  
##  <a name="a-namefromnumanodea-fromnumanode"></a><a name="from_numa_node"></a>from_numa_node 

 Gibt ein `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Parameter  
 `_NumaNodeNumber`  
 Die NUMA-Knotennummer um einen Speicherort für zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Position, die vom angegebenen NUMA-Knoten darstellt der `_NumaNodeNumber` Parameter.  
  
##  <a name="a-namectora-location"></a><a name="ctor"></a>Speicherort 

 Erstellt ein `location`-Objekt.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>Hinweise  
 Ein Standardspeicherort für erstellt stellt das System als Ganzes dar.  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>Operator! = 

 Bestimmt, ob zwei `location` Objekte unterschiedliche Position darstellt.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die beiden Speicherorten unterschiedlich sind, `false` andernfalls.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

 Weist den Inhalt eines anderen `location` -Objekts diesem Objekt zu.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Das `location`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>Operator == 

 Bestimmt, ob zwei `location` Objekte am gleichen Speicherort darstellen.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn es sich bei die beiden Speicherorten identisch sind und `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

