---
title: CComObjectRootEx Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f3a6d26ddb4f612824f959ca3046531dc3bbf2a9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx-Klasse
Diese Klasse stellt Methoden zur Verwaltung von Objekten Verweis Anzahl für aggregierte und aggregierten Objekte Behandlung.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadModel`  
 Die Klasse, deren Methoden das gewünschte Threadingmodell implementieren. Sie können das Threadingmodell explizit auswählen, indem `ThreadModel` auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Sie können die Thread-Standardmodell des Servers übernehmen, durch Festlegen `ThreadModel` auf [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Konstruktor.|  
|[InternalAddRef](#internaladdref)|Inkrementiert den Verweiszähler für ein nicht zusammengesetztes Objekt.|  
|[InternalRelease](#internalrelease)|Dekrementiert den Verweiszähler für ein nicht zusammengesetztes Objekt.|  
|[Sperren](#lock)|Wenn das Threadmodell multithreaded ist, erhält an einem kritischen Abschnittsobjekt.|  
|[Entsperren](#unlock)|Wenn das Threadmodell multithreaded ist, gibt Besitz ein kritisches Abschnittsobjekt frei.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase-Methoden  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|In der Klasse des Objekts erforderlichen Initialisierungen überschreiben.|  
|[FinalRelease](#finalrelease)|Überschreiben Sie in der Klasse, um alle vom Objekt erforderliche Bereinigung durchzuführen.|  
|[OuterAddRef](#outeraddref)|Inkrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
|[OuterQueryInterface](#outerqueryinterface)|Delegaten des äußeren **IUnknown** eines zusammengesetzten Objekts.|  
|[OuterRelease](#outerrelease)|Dekrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Delegiert an die **IUnknown** eines zusammengesetzten Objekts.|  
|[ObjectMain](#objectmain)|Während der Initialisierung des Moduls und Beendigung für die abgeleiteten Klassen aufgeführt, die in der objektzuordnung bezeichnet.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|Mit `m_pOuterUnknown`, Teil einer Union. Verwendet, wenn das Objekt nicht aggregiert werden, um den Verweiszähler des halten `AddRef` und **Version**.|  
|[m_pOuterUnknown](#m_pouterunknown)|Mit `m_dwRef`, Teil einer Union. Wird verwendet, wenn das Objekt aggregiert wird, um einen Zeiger auf die äußere unbekannte aufzunehmen.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectRootEx`Objekt Verweis Anzahl Management für aggregierte und aggregierten Objekte verarbeitet werden. Sie enthält den Verweiszähler des Objekts, wenn das Objekt wird nicht aggregiert, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt gerade zusammengesetzt wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können zum Behandeln des Fehlers des inneren Objekts zu erstellen und zu schützen, das äußere Objekt löschen Wenn innere Schnittstellen freigegeben werden oder das innere Objekt werden gelöscht.  
  
 Eine Klasse, die einen COM-Server implementiert Vererben muss `CComObjectRootEx` oder [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Wenn in die Klassendefinition angegeben der [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3) -Makro, ATL erstellt eine Instanz des **CComPolyObject\<CYourClass >** bei **IClassFactory:: CreateInstance** aufgerufen wird. Während der Erstellung wird der Wert der äußeren unbekannten überprüft. Ist dies **NULL**, **IUnknown** ist für ein nicht zusammengesetztes Objekt implementiert. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Wenn die Klasse keine der `DECLARE_POLY_AGGREGATABLE` -Makro, ATL erstellt eine Instanz des **CAggComObject\<CYourClass >** für aggregierte Objekte oder eine Instanz von **CComObject\<CYourClass >** für zusammengesetzten Objekte.  
  
 Der Vorteil der Verwendung `CComPolyObject` besteht darin, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` in Ihrem Modul zusammengefasste und aggregierte behandelt. Ein einzelnes `CComPolyObject` -Objekt verarbeitet beide Fälle. Aus diesem Grund nur eine Kopie der Vtable und eine Kopie der Funktionen im Modul vorhanden sein. Wenn die Vtable umfangreich ist, kann dies Modulgröße erheblich beeinträchtigen. Wenn die Vtable klein ist, jedoch mithilfe `CComPolyObject` kann in einem etwas größeren Modul führen, da er nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Wenn das Objekt aggregiert wird, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird implementiert, indem `CComAggObject` oder `CComPolyObject`. Diese Klassen delegieren `QueryInterface`, `AddRef`, und **Version** Aufrufe von `CComObjectRootEx`des `OuterQueryInterface`, `OuterAddRef`, und `OuterRelease` an die äußere unbekannte weiterleiten. Überschreiben Sie in der Regel `CComObjectRootEx::FinalConstruct` in Ihrer Klasse keine aggregierten Objekte erstellen, und überschreiben Sie `CComObjectRootEx::FinalRelease` zusammengefasst Objekte freizugeben.  
  
 Wenn das Objekt nicht zusammengesetzt ist, **IUnknown** wird implementiert, indem `CComObject` oder `CComPolyObject`. In diesem Fall die Aufrufe von `QueryInterface`, `AddRef`, und **Version** an delegiert werden `CComObjectRootEx`des `InternalQueryInterface`, `InternalAddRef`, und `InternalRelease` die tatsächlichen Vorgänge aus.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 Der Konstruktor initialisiert den Verweiszähler auf 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse ggf. für Ihr Objekt erforderliche Initialisierung ausführen.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zurückgeben `S_OK` auf Erfolg oder ein Standard-Fehler `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CComObjectRootEx::FinalConstruct` gibt einfach `S_OK`.  
  
 Es gibt Vorteile bei der Initialisierung in `FinalConstruct` statt der Konstruktor der Klasse:  
  
-   Sie können nicht von einem Konstruktor gibt einen Statuscode zurück, jedoch kann man eine `HRESULT` von `FinalConstruct`Rückgabewert. Wenn Objekte der Klasse mithilfe der standardmäßigen Klassenfactory von ATL bereitgestellten erstellt werden, wird dieser Rückgabewert zurück an den COM-Client können Sie detaillierte Fehlerinformationen geben weitergegeben.  
  
-   Sie können nicht über den Mechanismus der virtuellen Funktion vom Konstruktor der Klasse virtuelle Funktionen aufrufen. Aufruf einer virtuellen Funktion vom Konstruktor einer Klasse führt einen statisch aufgelösten Aufruf der Funktion, wie sie an diesem Punkt in der Vererbungshierarchie definiert ist. Aufrufe von reinen virtuellen Funktionen Linkerfehler auftreten.  
  
     Die Klasse ist nicht am stärksten abgeleitete Klasse in der Vererbungshierarchie – beruht auf einer abgeleiteten Klasse, die vom ATL, einen Teil der Funktionen bereitzustellen. Besteht eine hohe Wahrscheinlichkeit, die die Initialisierung mithilfe der Funktionen von dieser Klasse (Dies trifft sicherlich Objekte der Klasse müssen zum Aggregieren von anderen Objekten) muss, aber der Konstruktor der Klasse hat keine Möglichkeit, diese Funktionen zugreifen. Der Code zur Erstellung für die Klasse wird ausgeführt, bevor vollständig am stärksten abgeleitete Klasse erstellt wird.  
  
     Allerdings `FinalConstruct` wird aufgerufen, unmittelbar nach dem am meisten abgeleitete Klasse vollständig und Sie erstellt wird können virtuelle Funktionen aufrufen und die verweiszählung Implementierung ATL  
  
### <a name="example"></a>Beispiel  
 Überschreiben Sie diese Methode in der abgeleiteten Klasse in der Regel `CComObjectRootEx` erstellen Objekte zusammengefasst. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#40;](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 Wenn es sich bei die Erstellung ein Fehler auftritt, können Sie einen Fehler zurück. Sie können auch das Makro [DECLARE_PROTECT_FINAL_CONSTRUCT](http://msdn.microsoft.com/library/2d2e5ddc-057a-43ca-87c8-d3477a8193a0) zu verhindern, dass das äußere Objekt wird gelöscht, wenn während der Erstellung der internen aggregierte-Objekt den Verweiszähler und verringert die Anzahl auf 0 erhöht.  
  
 Hier ist üblicherweise ein Aggregat zu erstellen:  
  
-   Hinzufügen einer **IUnknown** Zeiger auf die Klasse Objekt, und initialisieren Sie es mit **NULL** im Konstruktor.  
  
-   Überschreiben Sie `FinalConstruct` das Aggregat zu erstellen.  
  
-   Verwenden der **IUnknown** Zeiger, die Sie als Parameter definiert die [COM_INTERFACE_ENTRY_AGGREGATE](http://msdn.microsoft.com/library/c671fa40-a57b-4797-ae88-c9762dabd4dc) Makro.  
  
-   Überschreiben Sie `FinalRelease` Freigeben der **IUnknown** Zeiger.  
  
##  <a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse ggf. für Ihr Objekt erforderliche Bereinigung ausführen.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CComObjectRootEx::FinalRelease` wird keine Aktion ausgeführt.  
  
 Ausführen der Bereinigung in `FinalRelease` empfiehlt sich, den Destruktor der Klasse Code hinzugefügt, da das Objekt weiterhin vollständig an die Stelle, an der erstellt wird `FinalRelease` aufgerufen wird. Dadurch können Sie problemlos von am stärksten abgeleitete Klasse bereitgestellten Methoden zugreifen. Dies ist besonders wichtig für die Freigabe von aggregierten Objekte vor dem Löschen.  
  
##  <a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 Der Verweiszähler eines zusammengesetzten Objekts erhöht um 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose und testen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das Threadmodell Multithreadanwendung, **InterlockedIncrement** wird verwendet, um zu verhindern, dass mehrere Threads den Verweiszähler gleichzeitig ändern.  
  
##  <a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `pThis`  
 [in] Ein Zeiger auf das Objekt mit der COM-Zuordnung von Schnittstellen verfügbar gemacht werden, um `QueryInterface`.  
  
 `pEntries`  
 [in] Ein Zeiger auf die **_ATL_INTMAP_ENTRY** -Struktur, die eine Übersicht über die verfügbaren Schnittstellen zugreift.  
  
 `iid`  
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 `InternalQueryInterface`behandelt nur Schnittstellen im COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `InternalQueryInterface` wird nicht an die äußere unbekannte delegieren. Sie können die Schnittstellen in der COM-Zuordnungstabelle mit dem Makro eingeben [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) oder einer seiner Varianten.  
  
##  <a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 Dekrementiert den Verweiszähler eines zusammengesetzten Objekts um 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In beiden nicht-Debugversion und Debugbuilds, diese Funktion gibt einen Wert, der möglicherweise hilfreich für die Diagnose oder testen. Der genaue Wert zurückgegeben wird, hängt von vielen Faktoren ab, wie das Betriebssystem verwendet, und eventuell oder auch nicht, werden die Anzahl der Verweise.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das Threadmodell Multithreadanwendung, **InterlockedDecrement** wird verwendet, um zu verhindern, dass mehrere Threads den Verweiszähler gleichzeitig ändern.  
  
##  <a name="lock"></a>CComObjectRootEx::Lock  
 Wenn das Threadmodell multithreaded ist, ruft diese Methode die Win32-API-Funktion [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), welche wartet, bis der Thread den kritischen Abschnittsobjekt Besitz kann über einen privaten Datenmember abgerufen.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der geschützte Code die Ausführung beendet hat, muss der Thread Aufrufen `Unlock` den Besitz der den kritischen Abschnitt freigibt.  
  
 Wenn das Threadmodell Singlethread ist, bewirkt diese Methode nichts.  
  
##  <a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 Teil einer Union, die vier Byte des Speichers zugreift.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>Hinweise  
 Mit `m_pOuterUnknown`, Teil einer Union:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Wenn das Objekt nicht zusammengesetzt ist wird, der Verweiszähler zugegriffen `AddRef` und **Version** befindet sich in `m_dwRef`. Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in [M_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 Teil einer Union, die vier Byte des Speichers zugreift.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>Hinweise  
 Mit `m_dwRef`, Teil einer Union:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in `m_pOuterUnknown`. Wenn das Objekt nicht zusammengesetzt ist wird, der Verweiszähler zugegriffen `AddRef` und **Version** befindet sich in [M_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 Für jede Klasse aufgelistet, die der [objektzuordnung](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), diese Funktion wird aufgerufen, wenn bei der Initialisierung des Moduls, und erneut beim wird beendet.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Parameter  
 `bStarting`  
 [out] Der Wert ist **true** die Klasse initialisiert wird; andernfalls wird **false**.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der `bStarting` Parameter angibt, ob das Modul initialisiert oder beendet. Die standardmäßige Implementierung des `ObjectMain` wird keine Aktion ausgeführt, aber Sie können diese Funktion überschreiben, in der Klasse initialisieren oder Bereinigen von Ressourcen, die für die Klasse zugeordnet werden soll. Beachten Sie, dass `ObjectMain` wird aufgerufen, bevor alle Instanzen der Klasse angefordert werden.  
  
 `ObjectMain`wird von den Einstiegspunkt der DLL aufgerufen damit der Typ der Operation, die die Einstiegspunktfunktion ausführen können, eingeschränkt wird. Weitere Informationen zu diesen Einschränkungen finden Sie unter [Verhalten der Laufzeitbibliothek](../../build/run-time-library-behavior.md) und [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#41;](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 Inkrementiert den Verweiszähler für die äußere unbekannte einer Aggregation.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose und testen.  
  
##  <a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
 Ruft einen indirekten Zeiger auf die angeforderte Schnittstelle ab.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** Wenn die Aggregation die Schnittstelle nicht unterstützt.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 Dekrementiert den Verweiszähler für die äußere unbekannte einer Aggregation.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer 0 zurück. In Debugbuilds gibt einen Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="unlock"></a>CComObjectRootEx::Unlock  
 Wenn das Threadmodell multithreaded ist, ruft diese Methode die Win32-API-Funktion [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), welche Versionen Besitzrechte Objekt des kritischen Abschnitts über einen privaten Datenmember abgerufen.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Um den Besitz zu erhalten, muss der Thread Aufrufen `Lock`. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf `Unlock` den Besitz der den kritischen Abschnitt freigibt.  
  
 Wenn das Threadmodell Singlethread ist, bewirkt diese Methode nichts.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

