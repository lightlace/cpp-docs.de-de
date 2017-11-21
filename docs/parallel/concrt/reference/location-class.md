---
title: Location-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
dev_langs: C++
helpviewer_keywords: location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aafe0500568cd9d4c9419345560272e18008df83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[Speicherort](#ctor)|Überladen. Erstellt ein `location`-Objekt.|  
|[~ Location-Destruktor](#dtor)|Zerstört ein `location`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[aktuelle](#current)|Gibt eine `location` Objekt, das die spezifischste Stelle den aufrufende Thread ausgeführt wird, darstellt.|  
|[from_numa_node](#from_numa_node)|Gibt eine `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Bestimmt, ob zwei `location` Objekte darstellen anderen Speicherort.|  
|[operator=](#operator_eq)|Weist den Inhalt eines anderen `location` -Objekts in dieses Objekt.|  
|[operator==](#operator_eq_eq)|Bestimmt, ob zwei `location` Objekte darstellen, den gleichen Speicherort.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `location`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a>~ Speicherort 

 Zerstört ein `location`-Objekt.  
  
```
~location();
```  
  
##  <a name="current"></a>aktuelle 

 Gibt eine `location` Objekt, das die spezifischste Stelle den aufrufende Thread ausgeführt wird, darstellt.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Speicherort, der die spezifischste Stelle darstellt, an der aufrufende Thread ausgeführt wird.  
  
##  <a name="from_numa_node"></a>from_numa_node 

 Gibt eine `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Parameter  
 `_NumaNodeNumber`  
 Die NUMA-Knotennummer um einen Speicherort für zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Position, die gemäß den NUMA-Knoten darstellt. die `_NumaNodeNumber` Parameter.  
  
##  <a name="ctor"></a>Speicherort 

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
 Ein standardmäßig erstelltes Speicherort stellt das System als Ganzes dar.  
  
##  <a name="operator_neq"></a>Operator! = 

 Bestimmt, ob zwei `location` Objekte darstellen anderen Speicherort.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn es sich bei die beiden Speicherorten unterscheiden, `false` andernfalls.  
  
##  <a name="operator_eq"></a>Operator = 

 Weist den Inhalt eines anderen `location` -Objekts in dieses Objekt.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
 Das `location`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq_eq"></a>Operator == 

 Bestimmt, ob zwei `location` Objekte darstellen, den gleichen Speicherort.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn es sich bei die beiden Speicherorten identisch sind und `false` andernfalls.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
