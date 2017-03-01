---
title: Klasse CComMultiThreadModelNoCS | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComMultiThreadModelNoCS
- CComMultiThreadModelNoCS
- ATL.CComMultiThreadModelNoCS
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 718aac826916b977eec4fb8400da81b5e32d4afa
ms.lasthandoff: 02/24/2017

---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS-Klasse
`CComMultiThreadModelNoCS`stellt threadsichere Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen ohne kritischen Abschnitt sperren oder Entsperren Funktionalität.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Verweist auf die Klasse `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Verweist auf die Klasse `CComMultiThreadModelNoCS`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statisch) Dekrementiert den Wert der angegebenen Variablen in einem Thread-sicher.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statisch) Inkrementiert den Wert der angegebenen Variablen in einem Thread-sicher.|  
  
## <a name="remarks"></a>Hinweise  
 `CComMultiThreadModelNoCS`ähnelt dem [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) , dass sie threadsichere Methoden zum Inkrementieren und Dekrementieren eine Variable enthält. Wenn Sie jedoch eine kritischen Abschnittsklasse über verweisen `CComMultiThreadModelNoCS`, Methoden, z. B. `Lock` und `Unlock` keine Wirkung.  
  
 Normalerweise verwenden Sie `CComMultiThreadModelNoCS` über die `ThreadModelNoCS``typedef` Name. Diese `typedef` wird definiert, `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Die globale `typedef` Namen [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) und [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) verweisen nicht auf `CComMultiThreadModelNoCS`.  
  
 Zusätzlich zu `ThreadModelNoCS`, `CComMultiThreadModelNoCS` definiert `AutoCriticalSection` und `CriticalSection`. Diese beiden `typedef` Namen Verweis [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), stellt leere Methoden abrufen und Freigeben eines kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `AutoCriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) auch enthalten Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `AutoCriticalSection`, können Sie die `typedef` Namen [CriticalSection](#criticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `CriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts, dessen Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) auch enthalten Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `CriticalSection`, können Sie die `typedef` Namen `AutoCriticalSection`. Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 Diese statischen Funktion ruft die Win32-Funktion [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), die dekrementiert der Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable dekrementiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis der Decrement 0, dann ist `Decrement` gibt 0 zurück. Wenn das Ergebnis der Decrement ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch möglicherweise nicht das Ergebnis der Decrement gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedDecrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.  
  
##  <a name="a-nameincrementa--ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 Diese statischen Funktion ruft die Win32-Funktion [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), der inkrementiert den Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable erhöht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis des Inkrements 0, dann ist **Inkrement** gibt 0 zurück. Wenn das Ergebnis des Inkrements ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch das Ergebnis das Inkrement kann nicht gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedIncrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `ThreadModelNoCS` verweist einfach auf `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) auch enthalten Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und Klasse verweist, auf `ThreadModelNoCS`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Beachten Sie, dass die Definition der `ThreadModelNoCS` in `CComMultiThreadModelNoCS` bietet Symmetrie mit `CComMultiThreadModel` und `CComSingleThreadModel`. Nehmen wir beispielsweise an der Beispielcode im `CComMultiThreadModel::AutoCriticalSection` deklariert die folgenden `typedef`:  
  
 [!code-cpp[NVC_ATL_COM&#37;](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Unabhängig von der für die angegebene Klasse `ThreadModel` (z. B. `CComMultiThreadModelNoCS`), `_ThreadModel` entsprechend aufgelöst wird.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
