---
title: CComSingleThreadModel Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSingleThreadModel
- CComSingleThreadModel
- ATL::CComSingleThreadModel
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: ff5d8d2ced1d6fe0196888d8c746844ace8307f8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel-Klasse
Diese Klasse stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen zu.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CComSingleThreadModel::Increment](#increment)|Inkrementiert den Wert der angegebenen Variablen. Diese Implementierung ist nicht threadsicher.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSingleThreadModel`Stellt Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen bereit. Im Gegensatz zu [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), diese Methoden sind nicht threadsicher.  

 Normalerweise verwenden Sie `CComSingleThreadModel` über eine von zwei `typedef` benennt, entweder [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Die Klasse verwiesen, die von den einzelnen `typedef` hängt von der threading-Modell verwendet, wie in der folgenden Tabelle dargestellt:  

  
|typedef|Einzelne threading-Modell|Apartment-threading-Modell|Free threading-Modell|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`selbst definiert drei `typedef` Namen. `ThreadModelNoCS`Verweise `CComSingleThreadModel`. `AutoCriticalSection`und `CriticalSection` -Verweisklasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), stellt leere Methoden abrufen und Freigeben des Besitzes eines kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 Bei Verwendung `CComSingleThreadModel`der `typedef` Namen `AutoCriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `AutoCriticalSection`, können Sie die `typedef` Namen [CriticalSection](#criticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 Bei Verwendung `CComSingleThreadModel`der `typedef` Namen `CriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `CriticalSection`, können Sie die `typedef` Namen [AutoCriticalSection](#autocriticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::Decrement  
 Diese statischen Funktion dekrementiert der Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable dekrementiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der dekrementieren.  
  
##  <a name="a-nameincrementa--ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel::Increment  
 Diese statischen Funktion dekrementiert der Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable erhöht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des Inkrements.  
  
##  <a name="a-namethreadmodelnocsa--ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 Bei Verwendung `CComSingleThreadModel`, `typedef` Namen `ThreadModelNoCS` verweist einfach auf `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) enthalten Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und Klasse verweist, auf `ThreadModelNoCS`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

