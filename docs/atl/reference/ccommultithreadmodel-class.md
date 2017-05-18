---
title: CComMultiThreadModel Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6dbfb33a717b23e8252c9bcb2fc11b4a6e420280
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel-Klasse
`CComMultiThreadModel`stellt threadsichere Methoden zum Inkrementieren und Dekrementieren den Wert einer Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Verweist auf die Klasse [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Verweist auf die Klasse ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md).|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Verweist auf die Klasse [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(Statisch) Dekrementiert den Wert der angegebenen Variablen in einem Thread-sicher.|  
|[CComMultiThreadModel::Increment](#increment)|(Statisch) Inkrementiert den Wert der angegebenen Variablen in einem Thread-sicher.|  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise verwenden Sie `CComMultiThreadModel` über eine von zwei `typedef` benennt, entweder [CComObjectThreadModel] (Atl-typedefs.md #ccomobjectthreadmodel oder [CComGlobalsThreadModel] (Atl-typedefs.md #ccomglobalsthreadmodel. Die Klasse verwiesen, die von den einzelnen `typedef` hängt von der threading-Modell verwendet, wie in der folgenden Tabelle dargestellt:  
  
|typedef|Single-threading|Apartmentthreading|Freies threading|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`selbst definiert drei `typedef` Namen. `AutoCriticalSection`und `CriticalSection` referenzieren von Klassen, die Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts bereitstellen. `ThreadModelNoCS`Verweise-Klasse [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 Bei Verwendung `CComMultiThreadModel`, `typedef` Namen `AutoCriticalSection` verweist auf die Klasse [CComAutoCriticalSection](ccomautocriticalsection-class.md), stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt.  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) und [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) auch enthalten Definitionen für `AutoCriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `AutoCriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `AutoCriticalSection`, können Sie die `typedef` Namen [CriticalSection](#criticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code nachgebildet [CComObjectRootEx](ccomobjectrootex-class.md), und zeigt `AutoCriticalSection` in einer Umgebung mit threading verwendet wird.  
  

```cpp  
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);   
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```  
  
 Die folgenden Tabellen zeigen die Ergebnisse der `InternalAddRef` und `Lock` Methoden, abhängig von der **ThreadModel** Vorlagenparameter und das Threadingmodell der Anwendung verwendet:  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel  
  
|Methode|Einzelne oder Apartmentthreading|Freies Threading|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|Die Schrittweite ist nicht threadsicher.|Die Schrittweite ist threadsicher.|  
|`Lock`|Wird keine Aktion ausgeführt werden soll; Es gibt keine kritischen Abschnitt gesperrt.|Der kritische Abschnitt gesperrt ist.|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS  
  
|Methode|Einzelne oder Apartmentthreading|Freies Threading|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|Die Schrittweite ist nicht threadsicher.|Die Schrittweite ist threadsicher.|  
|`Lock`|Wird keine Aktion ausgeführt werden soll; Es gibt keine kritischen Abschnitt gesperrt.|Wird keine Aktion ausgeführt werden soll; Es gibt keine kritischen Abschnitt gesperrt.|  
  
##  <a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 Bei Verwendung `CComMultiThreadModel`, `typedef` Namen `CriticalSection` verweist auf die Klasse ["CComCriticalSection"](ccomcriticalsection-class.md), stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt.  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Hinweise  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) und [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) auch enthalten Definitionen für `CriticalSection`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und kritischen Abschnittsklasse verweist, auf `CriticalSection`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Zusätzlich zu `CriticalSection`, können Sie die `typedef` Namen [AutoCriticalSection](#autocriticalsection). Sie sollten keinen `AutoCriticalSection` in globale Objekte oder statische Klassenmember, wenn Sie die CRT-Startcode entfernt werden soll.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).  
  
##  <a name="decrement"></a>CComMultiThreadModel::Decrement  
 Diese statischen Funktion ruft die Win32-Funktion [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), die dekrementiert der Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable dekrementiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis der Decrement 0, dann ist `Decrement` gibt 0 zurück. Wenn das Ergebnis der Decrement ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch möglicherweise nicht das Ergebnis der Decrement gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedDecrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.  
  
##  <a name="increment"></a>CComMultiThreadModel::Increment  
 Diese statischen Funktion ruft die Win32-Funktion [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), der inkrementiert den Wert der Variablen auf den `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Zeiger auf die Variable erhöht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn das Ergebnis des Inkrements 0, dann ist **Inkrement** gibt 0 zurück. Wenn das Ergebnis des Inkrements ungleich NULL ist, wird der Rückgabewert ist ebenfalls ungleich NULL jedoch das Ergebnis das Inkrement kann nicht gleich.  
  
### <a name="remarks"></a>Hinweise  
 **InterlockedIncrement** verhindert, dass mehrere Threads gleichzeitig verwenden diese Variable.  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 Bei Verwendung `CComMultiThreadModel`, `typedef` Namen `ThreadModelNoCS` verweist auf die Klasse [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Hinweise  
 `CComMultiThreadModelNoCS`bietet threadsichere Methoden zum Inkrementieren und Dekrementieren eine Variable. Es bietet jedoch kein kritischen Abschnitts.  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) und `CComMultiThreadModelNoCS` auch enthalten Definitionen für `ThreadModelNoCS`. Die folgende Tabelle zeigt die Beziehung zwischen threading Modellklasse und Klasse verweist, auf `ThreadModelNoCS`:  
  
|Klasse, definiert in|Klasse, auf die verwiesen wird|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).  
  
## <a name="see-also"></a>Siehe auch  
 [CComSingleThreadModel-Klasse](ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection-Klasse](ccomautocriticalsection-class.md)   
 ["CComCriticalSection"-Klasse](ccomcriticalsection-class.md)   
 [Übersicht über die Klasse](../atl-class-overview.md)

