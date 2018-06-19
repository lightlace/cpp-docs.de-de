---
title: CComObjectRootEx Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRootEx
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b147f0ad3f1a54c2ae640b6bf2426bcddf060b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365980"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx-Klasse
Diese Klasse stellt Methoden zum Behandeln von objektverwaltung Verweis Anzahl für aggregierte und aggregierte Objekte bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadModel`  
 Die Klasse, deren Methoden implementieren Sie das gewünschte Threadingmodell. Sie können das Threadingmodell explizit auswählen, indem er `ThreadModel` auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Sie können die Thread-Standardmodell des Servers übernehmen, durch Festlegen von `ThreadModel` auf [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Konstruktor.|  
|[InternalAddRef](#internaladdref)|Inkrementiert den Verweiszähler für eine aggregierte Objekt.|  
|[InternalRelease](#internalrelease)|Dekrementiert den Verweiszähler für eine aggregierte Objekt.|  
|[Sperre](#lock)|Wenn das Threadmodell Multithread ist, erhält den Besitz von einem kritischen Abschnittsobjekt.|  
|[Entsperren](#unlock)|Wenn das Threadmodell Multithread ist, gibt den Besitz von einem kritischen Abschnittsobjekt frei.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase-Methoden  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|In der Klasse erforderlich, die für Ihr Objekt Initialisierungen überschreiben.|  
|[FinalRelease](#finalrelease)|Überschreiben Sie in der Klasse Cleanup erforderlich, die für Ihr Objekt auszuführen.|  
|[OuterAddRef](#outeraddref)|Inkrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
|[OuterQueryInterface](#outerqueryinterface)|Delegaten des äußeren **IUnknown** eines zusammengesetzten Objekts.|  
|[OuterRelease](#outerrelease)|Dekrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Delegiert an die **IUnknown** eines zusammengesetzten Objekts.|  
|[ObjectMain](#objectmain)|Aufgerufen während der Initialisierung des Moduls und Beendigung für abgeleitete Klassen, die in der objektzuordnung aufgeführt.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|Mit `m_pOuterUnknown`, Teil einer Union. Verwendet, wenn das Objekt nicht aggregiert werden, um den Verweiszähler des halten `AddRef` und **Version**.|  
|[m_pOuterUnknown](#m_pouterunknown)|Mit `m_dwRef`, Teil einer Union. Verwendet, wenn das Objekt aggregiert werden, um einen Zeiger auf die äußere unbekannte zu halten.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectRootEx` objektverwaltung Verweis Anzahl für aggregierte und aggregierte Objekte verarbeitet werden. Sie enthält den Verweiszählerwert des Objekts, wenn Ihr Objekt wird nicht aggregiert, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt aggregiert wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können verwendet werden, die Fehler beim Erstellen des inneren Objekts behandeln und zu schützen, das äußere Objekt löschen, wenn innere Schnittstellen freigegeben werden oder das innere Objekt werden gelöscht.  
  
 Eine Klasse, die einen COM-Server muss von erben `CComObjectRootEx` oder [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Wenn Ihre Klassendefinition gibt die [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) -Makro, ATL erstellt eine Instanz des **CComPolyObject\<CYourClass >** Wenn **IClassFactory:: CreateInstance** aufgerufen wird. Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Ist er **NULL**, **IUnknown** für eine aggregierte Objekt implementiert wird. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Wenn Ihre Klasse keine der `DECLARE_POLY_AGGREGATABLE` -Makro, ATL erstellt eine Instanz des **CAggComObject\<CYourClass >** für aggregierte Objekte oder einer Instanz von **CComObject\<CYourClass >** für aggregierte Objekte.  
  
 Der Vorteil der Verwendung `CComPolyObject` ist, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die zusammengefasste und aggregierte Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt verarbeitet die beiden Fällen. Deshalb nur eine Kopie der Vtable und eine Kopie der Funktionen innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Jedoch verwenden, wenn die Vtable klein ist, `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Wenn das Objekt aggregiert wird, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird dadurch implementiert, `CComAggObject` oder `CComPolyObject`. Diese Klassen delegieren `QueryInterface`, `AddRef`, und **Release** Aufrufe von `CComObjectRootEx`des `OuterQueryInterface`, `OuterAddRef`, und `OuterRelease` , an die äußere unbekannte weiterzuleiten. Überschreiben Sie in der Regel `CComObjectRootEx::FinalConstruct` in Ihrer Klasse, um die aggregierten Objekte erstellen, und überschreiben Sie `CComObjectRootEx::FinalRelease` für freizugeben die einzelnen Objekte zusammengefasst.  
  
 Wenn Ihr Objekt nicht aggregiert wird, **IUnknown** wird dadurch implementiert, `CComObject` oder `CComPolyObject`. In diesem Fall Aufrufe von `QueryInterface`, `AddRef`, und **Release** werden an delegiert `CComObjectRootEx`des `InternalQueryInterface`, `InternalAddRef`, und `InternalRelease` für die tatsächlichen Vorgänge.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx  
 Der Konstruktor initialisiert den Verweiszähler auf 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse alle für Ihr Objekt erforderliche Initialisierung ausführen.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zurückgeben `S_OK` auf Erfolg oder eines der Standardfehler `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `CComObjectRootEx::FinalConstruct` gibt einfach auftragsantwortnachrichten zurück `S_OK`.  
  
 Es ergeben sich Vorteile Durchführung Initialisierung in `FinalConstruct` anstelle der Konstruktor der Klasse:  
  
-   Sie können nicht von einem Konstruktor gibt einen Statuscode zurück, aber Sie können zurückkehren, eine `HRESULT` anhand der `FinalConstruct`Rückgabewert. Wenn mit der standard-Klassenfactory, die von ATL bereitgestellten Objekte der Klasse erstellt werden, ist dieser Rückgabewert zurück an den COM-Client können Sie zur Angabe von Anmeldeinformationen mit detaillierten Fehlerinformationen weitergegeben.  
  
-   Sie können nicht über den Mechanismus der virtuellen Funktion vom Konstruktor einer Klasse virtuelle Funktionen aufrufen. Eine virtuelle Funktion, die vom Konstruktor einer Klasse aufgerufen wird, führt dies zu einem statisch aufgelösten Aufruf an die Funktion an, wie sie zu diesem Zeitpunkt in der Vererbungshierarchie definiert ist. Aufrufe von reinen virtuellen Funktionen zu Linker-Fehlern führen.  
  
     Die Klasse ist nicht am stärksten abgeleitete Klasse in der Vererbungshierarchie – es beruht auf einer abgeleiteten Klasse, die vom ATL, um einige ihrer Funktionen bereitzustellen. Besteht eine hohe Wahrscheinlichkeit, die die Initialisierung muss, verwenden Sie die Funktionen, die von dieser Klasse (Dies gilt immer, wenn Objekte der Klasse zum Aggregieren von anderen Objekten müssen) bereitgestellt, aber der Konstruktor in der Klasse hat keine Möglichkeit, diese Features zuzugreifen. Der Konstruktionscode für die Klasse wird ausgeführt, bevor die am stärksten abgeleitete Klasse vollständig erstellt wird.  
  
     Allerdings `FinalConstruct` wird aufgerufen, unmittelbar nachdem die am meisten abgeleitete Klasse vollständig und Sie erstellt wird können virtuelle Funktionen aufrufen und die verweiszählung Implementierung, die ATL verwenden  
  
### <a name="example"></a>Beispiel  
 Überschreiben Sie diese Methode in der abgeleiteten Klasse in der Regel `CComObjectRootEx` aggregiert Sie Objekte erstellen. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 Wenn es sich bei die Erstellung ein Fehler auftritt, können Sie einen Fehler zurück. Sie können auch das Makro [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) zum Schutz Ihrer äußeren Objekts nicht gelöscht werden soll, wenn während der Erstellung der internen aggregierte-Objekt den Verweiszähler dieser Planergruppe dann verringert die Anzahl auf 0 erhöht.  
  
 Hier ist üblicherweise ein Aggregat zu erstellen:  
  
-   Hinzufügen einer **IUnknown** Zeiger auf die Klasse Objekt, und initialisieren Sie sie mit **NULL** im Konstruktor.  
  
-   Überschreiben Sie `FinalConstruct` das Aggregat zu erstellen.  
  
-   Verwenden der **IUnknown** Zeiger, die Sie definiert als Parameter an die [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) Makro.  
  
-   Überschreiben Sie `FinalRelease` zum Freigeben der **IUnknown** Zeiger.  
  
##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse alle für Ihr Objekt erforderlichen Cleanup auszuführen.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `CComObjectRootEx::FinalRelease` wird keine Aktion ausgeführt.  
  
 Ausführen der Bereinigung in `FinalRelease` empfiehlt sich gegenüber der Destruktor der Klasse Code hinzugefügt, da das Objekt noch vollständig, an dem Punkt, an dem erstellt wird `FinalRelease` aufgerufen wird. Dadurch können Sie sicher auf die durch die am stärksten abgeleitete Klasse bereitgestellten Methoden zuzugreifen. Dies ist besonders wichtig für die Freigabe von aggregierten Objekte vor dem Löschen.  
  
##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef  
 Inkrementiert den Verweiszähler dieser Planergruppe eines zusammengesetzten Objekts um 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise nützlich für die Diagnose und testen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Threadmodell multithreaded, **InterlockedIncrement** wird verwendet, um zu verhindern, dass mehr als einem Thread den Verweiszähler dieser Planergruppe gleichzeitig ändern.  
  
##  <a name="internalqueryinterface"></a>  CComObjectRootEx::InternalQueryInterface  
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
 [in] Ein Zeiger auf die **_ATL_INTMAP_ENTRY** -Struktur, die eine Übersicht der verfügbaren Schnittstellen zugreift.  
  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
### <a name="remarks"></a>Hinweise  
 `InternalQueryInterface` Nur behandelt Schnittstellen in der COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `InternalQueryInterface` delegieren, die äußere unbekannte nicht. Geben Sie den Schnittstellen, in der COM-Zuordnungstabelle mit dem Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oder einer dessen Varianten.  
  
##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease  
 Dekrementiert den Verweiszähler eines zusammengesetzten Objekts um 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In sowohl nicht-Debug und Debugbuilds, diese Funktion gibt einen Wert, der möglicherweise bei der Diagnose hilfreich oder testen. Der genaue Wert zurückgegeben wird, hängt von vielen Faktoren ab, wie das Betriebssystem verwendet, und möglicherweise oder sind nicht berechtigt, werden den Verweiszähler dieser Planergruppe.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Threadmodell multithreaded, **InterlockedDecrement** wird verwendet, um zu verhindern, dass mehr als einem Thread den Verweiszähler dieser Planergruppe gleichzeitig ändern.  
  
##  <a name="lock"></a>  CComObjectRootEx::Lock  
 Wenn das Threadmodell Multithread ist, ruft diese Methode die Win32-API-Funktion [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), welche wartet, bis der Thread den kritischen Abschnittsobjekt Besitz kann über ein privates Datenmember abgerufen.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie der geschützte Code die Ausführung abgeschlossen ist, muss der Thread Aufrufen `Unlock` den Besitz der kritischen Abschnitt freigibt.  
  
 Wenn das Threadmodell Singlethread ist, wird diese Methode keine Aktion ausgeführt.  
  
##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef  
 Teil einer Union mit den vier Bytes des Speichers zugreift.  
  
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
  
 Wenn das Objekt nicht aggregiert wird, Zugriff auf der Verweiszähler von `AddRef` und **Release** befindet sich in `m_dwRef`. Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in [M_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown  
 Teil einer Union mit den vier Bytes des Speichers zugreift.  
  
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
  
 Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in `m_pOuterUnknown`. Wenn das Objekt nicht aggregiert wird, Zugriff auf der Verweiszähler von `AddRef` und **Release** befindet sich in [M_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain  
 Für jede Klasse aufgeführt, die der [objektzuordnung](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), diese Funktion wird aufgerufen, sobald beim Initialisieren des Moduls und erneut wenn er beendet.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Parameter  
 `bStarting`  
 [out] Der Wert ist **"true"** wird die Klasse initialisiert wurde andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert, der die `bStarting` Parameter gibt an, ob das Modul wird initialisiert oder beendet. Die standardmäßige Implementierung des `ObjectMain` wird keine Aktion ausgeführt, aber Sie können diese Funktion überschreiben, in der Klasse initialisieren oder Bereinigen von Ressourcen, die für die Klasse zugewiesen werden soll. Beachten Sie, dass `ObjectMain` wird aufgerufen, bevor alle Instanzen der Klasse angefordert werden.  
  
 `ObjectMain` wird aufgerufen vom Einstiegspunkt der DLL, damit der Typ des Vorgangs, die die Einstiegspunktfunktion ausführen können beschränkt ist. Weitere Informationen zu diesen Einschränkungen finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) und [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef  
 Inkrementiert den Verweiszähler für die äußere unbekannte einer Aggregation.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise nützlich für die Diagnose und testen.  
  
##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface  
 Ruft einen indirekten Zeiger auf die angeforderte Schnittstelle ab.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen `iid`, oder **NULL** , wenn die Aggregation der Schnittstelle nicht unterstützt.  
  
### <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease  
 Dekrementiert den Verweiszähler für die äußere unbekannte einer Aggregation.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer 0 zurück. Debug-Builds gibt einen Wert an, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="unlock"></a>  CComObjectRootEx::Unlock  
 Wenn das Threadmodell Multithread ist, ruft diese Methode die Win32-API-Funktion [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), welche Versionen den Besitz des Objekts kritischen Abschnitt über ein privates Datenmember abgerufen.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Zum Abrufen des Besitzes der Thread aufrufen, muss `Lock`. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf von `Unlock` den Besitz der kritischen Abschnitt freigibt.  
  
 Wenn das Threadmodell Singlethread ist, wird diese Methode keine Aktion ausgeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
