---
title: CComSingleThreadModel Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65af9492f3721fd642def72a3049552cdff75ce6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel-Klasse
Diese Klasse stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Verweist auf die Klasse `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Verweise `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Dekrementiert den Wert der angegebenen Variablen. Diese Implementierung ist nicht threadsicher.|  
|[CComSingleThreadModel::Increment](#increment)|Erhöht den Wert der angegebenen Variablen. Diese Implementierung ist nicht threadsicher.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSingleThreadModel`Stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen bereit. Im Gegensatz zu [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), diese Methoden sind nicht threadsicher.  

 Verwenden Sie in der Regel `CComSingleThreadModel` über eine von zwei `typedef` benennt, entweder [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Die Klasse verwiesen, die von jedem `typedef` hängt von der Threadingmodell verwendet, wie in der folgenden Tabelle dargestellt:  

  
|Typedef|Einzelne Threadingmodell|Apartment Threadingmodell|Kostenlose Threadingmodell|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`selbst definiert drei `typedef` Namen. `ThreadModelNoCS`Verweise `CComSingleThreadModel`. `AutoCriticalSection`und `CriticalSection` Klasse verweisen [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), stellt leere Methoden zugeordneten abrufen und Freigeben des Besitzes eines kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 Bei Verwendung `CComSingleThreadModel`, `typedef` Namen `AutoCriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts seine Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `AutoCriticalSection`, können Sie die `typedef` Namen [CriticalSection](#criticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode ausschließen möchten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 Bei Verwendung `CComSingleThreadModel`, `typedef` Namen `CriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts seine Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `CriticalSection`, können Sie die `typedef` Namen [AutoCriticalSection](#autocriticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode ausschließen möchten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>CComSingleThreadModel::Decrement  
 Diese statische Funktion dekrementiert der Wert der Variable verweist, zu `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die zu verringernde Variable.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis dem dekrementieren.  
  
##  <a name="increment"></a>CComSingleThreadModel::Increment  
 Diese statische Funktion dekrementiert der Wert der Variable verweist, zu `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable vorwärts verschoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Inkrements.  
  
##  <a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 Bei Verwendung `CComSingleThreadModel`, `typedef` Namen `ThreadModelNoCS` einfach verweist auf `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und Klasse verweist, auf `ThreadModelNoCS`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
