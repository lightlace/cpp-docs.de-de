---
title: CComMultiThreadModelNoCS Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
dev_langs: C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1f0b531942e281236c65ef9a2e1ad3d3f669bbe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS-Klasse
`CComMultiThreadModelNoCS`Stellt Thread-sichere Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen ohne kritischen Abschnitt sperren oder Entsperren Funktionalität bereit  
  
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
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statisch) Dekrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statisch) Inkrementiert den Wert der angegebenen Variablen auf threadsichere Weise.|  
  
## <a name="remarks"></a>Hinweise  
 `CComMultiThreadModelNoCS`ähnelt dem [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) insofern, dass sie threadsichere Methoden für Inkrementieren und Dekrementieren eine Variable bietet. Wenn Sie jedoch eine kritischen Abschnittsklasse über verweisen `CComMultiThreadModelNoCS`, Methoden, z. B. `Lock` und `Unlock` kein Ergebnis.  
  
 Verwenden Sie in der Regel `CComMultiThreadModelNoCS` über die `ThreadModelNoCS` `typedef` Name. Dies `typedef` ist definiert `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Die globale `typedef` Namen [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) und [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) keinen Verweis auf die `CComMultiThreadModelNoCS`.  
  
 Zusätzlich zu `ThreadModelNoCS`, `CComMultiThreadModelNoCS` definiert `AutoCriticalSection` und `CriticalSection`. Diese beiden `typedef` benennt Verweis [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), stellt leere Methoden zugeordneten abrufen und Freigeben eines kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `AutoCriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts seine Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `AutoCriticalSection`, können Sie die `typedef` Namen [CriticalSection](#criticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode ausschließen möchten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `CriticalSection` verweist auf die Klasse [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 Da `CComFakeCriticalSection` bietet kein kritischen Abschnitts seine Methoden werden keine Aktionen ausgeführt.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `CriticalSection`, können Sie die `typedef` Namen `AutoCriticalSection`. Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode ausschließen möchten.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 Diese statische Funktion ruft die Win32-Funktion [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), welche dekrementiert der Wert der Variablen verweist `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die zu verringernde Variable.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis dem Dekrementieren 0, klicken Sie dann ist `Decrement` gibt 0 zurück. Wenn das Ergebnis dem Dekrementieren ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch möglicherweise nicht das Ergebnis dem Dekrementieren gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedDecrement** verhindert, dass mehrere Threads gleichzeitig mit dieser Variable.  
  
##  <a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 Diese statische Funktion ruft die Win32-Funktion [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), der inkrementiert des Wert der Variablen, die durch `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable vorwärts verschoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis des Inkrements 0, klicken Sie dann ist **Inkrement** gibt 0 zurück. Wenn das Ergebnis des Inkrements ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch möglicherweise nicht das Ergebnis des Inkrements gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedIncrement** verhindert, dass mehrere Threads gleichzeitig mit dieser Variable.  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 Bei Verwendung `CComMultiThreadModelNoCS`, `typedef` Namen `ThreadModelNoCS` einfach verweist auf `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) und [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) enthalten auch die Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen der threading Modellklasse und Klasse verweist, auf `ThreadModelNoCS`:  
  
|Klasse, die definiert werden.|Klasse, die auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Beachten Sie, dass die Definition der `ThreadModelNoCS` in `CComMultiThreadModelNoCS` bietet die Einheitlichkeit mit `CComMultiThreadModel` und `CComSingleThreadModel`. Nehmen wir beispielsweise an der Beispielcode im `CComMultiThreadModel::AutoCriticalSection` deklariert die folgenden `typedef`:  
  
 [!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Unabhängig von der für die angegebene Klasse `ThreadModel` (z. B. `CComMultiThreadModelNoCS`), `_ThreadModel` entsprechend auflöst.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)