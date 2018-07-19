---
title: CComObjectRootEx-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 55da0705027d6625d4140691b1b91912fb94c555
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027526"
---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx-Klasse
Diese Klasse stellt Methoden zur Behandlung von Objekt Anzahl verweisverwaltung für aggregierte und zusammengesetzten Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>Parameter  
 *ThreadModel*  
 Die Klasse, deren Methoden implementieren Sie das gewünschte Threadingmodell. Sie können das Threadingmodell explizit auswählen, durch Festlegen von *ThreadModel* zu [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), oder [ CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md). Sie können die Thread-Standardmodell des Servers übernehmen, durch Festlegen von *ThreadModel* zu [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) oder [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel).  

  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|Konstruktor.|  
|[InternalAddRef](#internaladdref)|Inkrementiert den Verweiszähler für einen zusammengesetzten Objekt.|  
|[InternalRelease](#internalrelease)|Dekrementiert den Verweiszähler für einen zusammengesetzten Objekt.|  
|[Sperre](#lock)|Wenn das Threadmodell Multithreadanwendung ist, ruft den Besitz von einem kritischen Abschnittsobjekt ab.|  
|[Entsperren](#unlock)|Wenn das Threadmodell Multithreadanwendung ist, gibt den Besitz der ein kritisches Abschnittsobjekt.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase-Methoden  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|In der Klasse des Objekts erforderlichen Initialisierungen überschreiben.|  
|[FinalRelease](#finalrelease)|Überschreiben Sie in der Klasse des Objekts erforderlichen Bereinigungen ausführen.|  
|[OuterAddRef](#outeraddref)|Inkrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
|[OuterQueryInterface](#outerqueryinterface)|Delegiert an die äußere `IUnknown` eines aggregierten Objekts.|  
|[OuterRelease](#outerrelease)|Dekrementiert den Verweiszähler für ein zusammengesetztes Objekt.|  
  
### <a name="static-functions"></a>Statische Funktionen  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|Delegiert an die `IUnknown` eines zusammengesetzten Objekts.|  
|[ObjectMain](#objectmain)|Während der Initialisierung des Moduls und beenden für abgeleitete Klassen aufgeführt, die in der objektzuordnung aufgerufen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|Mit `m_pOuterUnknown`, Teil einer Union. Verwendet, wenn das Objekt nicht aggregiert werden, um den Verweiszähler von aufzunehmen `AddRef` und `Release`.|  
|[m_pOuterUnknown](#m_pouterunknown)|Mit `m_dwRef`, Teil einer Union. Wird verwendet, wenn das Objekt aggregiert wird, um einen Zeiger auf die äußere unbekannte zu speichern.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectRootEx` verarbeitet die objektverwaltung Verweis Anzahl für aggregierte und zusammengesetzten Objekte. Sie enthält den Verweiszählerwert des Objekts, wenn das Objekt nicht aggregiert werden wird, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt aggregiert wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können verwendet werden, um das innere Objekt zum Erstellen der Ausfall behandelt, und schützen das äußere Objekt vor dem Löschen, wenn interne Schnittstellen freigegeben werden oder das innere Objekt gelöscht wird.  
  
 Eine Klasse, einen COM-Server implementiert, erben muss `CComObjectRootEx` oder [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Wenn es sich bei Ihrer Klassendefinition gibt an, die [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) -Makro, ATL erstellt eine Instanz des `CComPolyObject<CYourClass>` beim `IClassFactory::CreateInstance` aufgerufen wird. Während der Erstellung wird der Wert, der die äußere unbekannte überprüft. Wenn auf NULL, `IUnknown` für einen zusammengesetzten Objekt implementiert wird. Wenn die äußere unbekannte ungleich NULL ist `IUnknown` wird für ein zusammengesetztes Objekt implementiert.  
  
 Wenn Ihre Klasse nicht das Makro DECLARE_POLY_AGGREGATABLE angibt, ATL erstellt eine Instanz von `CAggComObject<CYourClass>` für aggregierte Objekte oder eine Instanz von `CComObject<CYourClass>` für zusammengesetzten Objekte.  
  
 Der Vorteil der Verwendung `CComPolyObject` besteht darin, dass Sie vermeiden, dass beide `CComAggObject` und `CComObject` innerhalb des Moduls, die aggregierte und zusammengesetzten Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt behandelt beide Fälle. Aus diesem Grund nur eine Kopie der Vtable und eine Kopie der Funktionen im Modul vorhanden sein. Wenn Ihre Vtable groß ist, kann dies Modulgröße erheblich verringern. Die Vtable klein ist, jedoch verwenden `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt zusammengesetzten oder aggregiert, optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Wenn das Objekt aggregiert wird, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) wird implementiert, indem `CComAggObject` oder `CComPolyObject`. Diese Klassen delegieren `QueryInterface`, `AddRef`, und `Release` Aufrufe von `CComObjectRootEx`des `OuterQueryInterface`, `OuterAddRef`, und `OuterRelease` , an die äußere unbekannte weiterzuleiten. In der Regel, die Sie überschreiben `CComObjectRootEx::FinalConstruct` in Ihrer Klasse, um alle aggregierten Objekte erstellen, und überschreiben `CComObjectRootEx::FinalRelease` aggregierten Objekte freizugeben.  
  
 Wenn das Objekt nicht aggregiert werden, `IUnknown` wird implementiert, indem `CComObject` oder `CComPolyObject`. In diesem Fall die Aufrufe von `QueryInterface`, `AddRef`, und `Release` delegiert werden `CComObjectRootEx`des `InternalQueryInterface`, `InternalAddRef`, und `InternalRelease` die tatsächlichen Vorgänge ausführen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>  CComObjectRootEx::CComObjectRootEx  
 Der Konstruktor initialisiert den Verweiszähler auf 0.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>  CComObjectRootEx::FinalConstruct  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse zum Ausführen von Initialisierungen, die für Ihr Objekt erforderlich.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder eines der Standard-Fehler-HRESULT-Werte zurück.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CComObjectRootEx::FinalConstruct` einfach gibt S_OK zurück.  
  
 Es gibt Vorteile zum Ausführen der Initialisierung in `FinalConstruct` statt den Konstruktor der Klasse:  
  
-   Sie können einen Statuscode zurückgeben, von einem Konstruktor, aber Sie können ein HRESULT von zurückgeben `FinalConstruct`Rückgabewert. Bei der Verwendung von ATL bereitgestellten Standardklasse Factory Objekte der Klasse erstellt werden, wird dieser Rückgabewert zurück an der COM-Client, sodass Sie sie mit detaillierten Fehlerinformationen bereitstellen weitergegeben.  
  
-   Sie können nicht über den Mechanismus der virtuellen Funktion aus dem Konstruktor einer Klasse virtuelle Funktionen aufrufen. Eine virtuelle Funktion aus dem Konstruktor einer Klasse aufrufen wird, führt dies zu einem statisch aufgelösten Aufruf an die Funktion an, wie sie zu diesem Zeitpunkt in der Vererbungshierarchie definiert ist. Aufrufen von reinen virtuellen Funktionen führen Linker-Fehler.  
  
     Die Klasse ist nicht die am stärksten abgeleitete Klasse in der Vererbungshierarchie – es beruht auf einer abgeleiteten Klasse, die vom ATL, um einen Teil der Funktionen bereitzustellen. Besteht eine hohe Wahrscheinlichkeit, die der Initialisierung mithilfe der Funktionen von dieser Klasse (Dies gilt natürlich, wenn Objekte der Klasse zum Aggregieren von anderen Objekten müssen) muss, aber der Konstruktor in der Klasse hat keine Möglichkeit, diese Funktionen zugreifen. Der Code zur Konstruktion für die Klasse wird ausgeführt, bevor die am stärksten abgeleitete Klasse vollständig erstellt wird.  
  
     Allerdings `FinalConstruct` wird aufgerufen, unmittelbar nach dem am meisten abgeleitete Klasse vollständig erstellt wird es Ihnen ermöglichen virtuelle Funktionen aufrufen oder verwenden Sie die verweiszählung Implementierung von ATL  
  
### <a name="example"></a>Beispiel  
 In der Regel überschreiben diese Methode in der Klasse, die von abgeleiteten `CComObjectRootEx` AECs erstellt Objekte zusammengefasst. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 Wenn es sich bei die Erstellung ein Fehler auftritt, können Sie einen Fehler zurück. Sie können auch das Makro [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) das äußere Objekt nicht schützen gelöscht werden soll, wenn während der Erstellung, internen aggregierten Objekts den Verweiszähler und verringert die Anzahl auf 0 erhöht sich.  
  
 Hier ist eine typische Möglichkeit zum Erstellen eines Aggregats aus:  
  
-   Hinzufügen einer `IUnknown` Zeiger auf die Klasse Objekt, und initialisieren Sie es im Konstruktor auf NULL.  
  
-   Außer Kraft setzen `FinalConstruct` So erstellen Sie das Aggregat.  
  
-   Verwenden der `IUnknown` Zeiger, die Sie als Parameter definiert die [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) Makro.  
  
-   Außer Kraft setzen `FinalRelease` Freigeben der `IUnknown` Zeiger.  
  
##  <a name="finalrelease"></a>  CComObjectRootEx::FinalRelease  
 Sie können diese Methode überschreiben, in der abgeleiteten Klasse, um alle für Ihr Objekt erforderlichen Cleanups durchzuführen.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `CComObjectRootEx::FinalRelease` hat keine Auswirkungen.  
  
 Durchführen der Bereinigung in `FinalRelease` empfiehlt sich, den Destruktor der Klasse Code hinzugefügt, da das Objekt weiterhin vollständig, an dem Punkt, an dem erstellt wird `FinalRelease` aufgerufen wird. Dadurch können Sie sicher auf die von der am stärksten abgeleitete Klasse bereitgestellten Methoden zuzugreifen. Dies ist besonders wichtig für die Freigabe der aggregierte Objekte vor dem Löschen.  
  
##  <a name="internaladdref"></a>  CComObjectRootEx::InternalAddRef  
 Erhöht den Verweiszähler eines zusammengesetzten Objekts um 1.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der bei der Diagnose hilfreich und Tests sein kann.  
  
### <a name="remarks"></a>Hinweise  
 Ist das Threadmodell multithreaded, `InterlockedIncrement` wird verwendet, um zu verhindern, dass mehr als einem Thread den Verweiszähler zur gleichen Zeit ändern.  
  
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
 *pThis*  
 [in] Ein Zeiger auf das Objekt, das die Zuordnung der COM-Schnittstellen verfügbar gemacht werden, um enthält `QueryInterface`.  
  
 *pEntries*  
 [in] Ein Zeiger auf die `_ATL_INTMAP_ENTRY` -Struktur, die eine Übersicht über die verfügbaren Schnittstellen zugreift.  
  
 *IID*  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 *ppvObject*  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen *Iid*, oder NULL, wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 `InternalQueryInterface` behandelt nur Schnittstellen in der COM-Zuordnungstabelle. Wenn das Objekt aggregiert wird, `InternalQueryInterface` ist das nicht an die äußere unbekannte delegieren. Sie können Schnittstellen eingeben, in die COM-Zuordnungstabelle mit dem Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oder eine ihrer Varianten.  
  
##  <a name="internalrelease"></a>  CComObjectRootEx::InternalRelease  
 Dekrementiert den Verweiszähler eines zusammengesetzten Objekts um 1.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In beide nicht für das Debuggen und Debuggen von builds, diese Funktion gibt einen Wert, der möglicherweise bei der Diagnose hilfreich oder Tests zurück. Der genaue Wert zurückgegeben wird, hängt von vielen Faktoren ab, z.B. das Betriebssystem verwendet, und möglicherweise oder sind nicht dazu berechtigt, der Verweiszähler werden.  
  
### <a name="remarks"></a>Hinweise  
 Ist das Threadmodell multithreaded, `InterlockedDecrement` wird verwendet, um zu verhindern, dass mehr als einem Thread den Verweiszähler zur gleichen Zeit ändern.  
  
##  <a name="lock"></a>  CComObjectRootEx::Lock  
 Wenn das Threadmodell Multithreadanwendung ist, wird diese Methode ruft die Win32-API-Funktion [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), welche wartet, bis der Thread den kritischen Abschnittsobjekt Besitz kann über einen privaten Datenmember abgerufen.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der geschützte Code die Ausführung abgeschlossen ist, muss der Thread Aufrufen `Unlock` um den Besitz der des kritischen Abschnitts freizugeben.  
  
 Wenn das Threadmodell Singlethread ist, bewirkt diese Methode nichts.  
  
##  <a name="m_dwref"></a>  CComObjectRootEx::m_dwRef  
 Teil einer Union, der vier Bytes an Arbeitsspeicher zugreift.  
  
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
  
 Wenn das Objekt nicht aggregiert werden, Zugriff auf der Verweiszähler von `AddRef` und `Release` befindet sich in `m_dwRef`. Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in [M_pOuterUnknown](#m_pouterunknown).  
  
##  <a name="m_pouterunknown"></a>  CComObjectRootEx::m_pOuterUnknown  
 Teil einer Union, der vier Bytes an Arbeitsspeicher zugreift.  
  
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
  
 Wenn das Objekt aggregiert wird, befindet sich der Zeiger auf die äußere unbekannte in `m_pOuterUnknown`. Wenn das Objekt nicht aggregiert werden, Zugriff auf der Verweiszähler von `AddRef` und `Release` befindet sich in [M_dwRef](#m_dwref).  
  
##  <a name="objectmain"></a>  CComObjectRootEx::ObjectMain  
 Für jede Klasse aufgeführt, die der [objektzuordnung](http://msdn.microsoft.com/b57619cc-534f-4b8f-bfd4-0c12f937202f), diese Funktion wird aufgerufen, sobald beim Initialisieren des Moduls, und es wenn er beendet.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>Parameter  
 *bStarting*  
 [out] Der Wert ist "true", wenn die Klasse initialisiert wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des der *bStarting* Parameter gibt an, ob das Modul wird initialisiert oder beendet. Die standardmäßige Implementierung des `ObjectMain` hat keine Auswirkungen, aber Sie können diese Funktion außer Kraft setzen, in der Klasse initialisieren oder Bereinigen von Ressourcen, die für die Klasse zugeordnet werden soll. Beachten Sie, dass `ObjectMain` wird aufgerufen, bevor alle Instanzen der Klasse angefordert werden.  
  
 `ObjectMain` wird aufgerufen von der aus der DLL, damit der Typ des Vorgangs, die die Einstiegspunktfunktion ausführen können, eingeschränkt wird. Weitere Informationen zu diesen Einschränkungen finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) und [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>  CComObjectRootEx::OuterAddRef  
 Inkrementiert den Verweiszähler der die äußere unbekannte einer Aggregation.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der bei der Diagnose hilfreich und Tests sein kann.  
  
##  <a name="outerqueryinterface"></a>  CComObjectRootEx::OuterQueryInterface  
 Ruft einen indirekten Zeiger auf die angeforderte Schnittstelle ab.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 *IID*  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 *ppvObject*  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der im angegebenen *Iid*, oder NULL, wenn die Aggregation der Schnittstelle nicht unterstützt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="outerrelease"></a>  CComObjectRootEx::OuterRelease  
 Dekrementiert den Verweiszähler der äußeren unbekannten einer Aggregation.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debug-Builds gibt immer 0 zurück. In Debugbuilds müssen Sie einen Wert aus, der möglicherweise bei der Diagnose hilfreich oder Tests zurück.  
  
##  <a name="unlock"></a>  CComObjectRootEx::Unlock  
 Wenn das Threadmodell Multithreadanwendung ist, wird diese Methode ruft die Win32-API-Funktion [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), welche Versionen des Besitzes von Objekt des kritischen Abschnitts über einen privaten Datenmember abgerufen.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>Hinweise  
 Um den Besitz zu erhalten, muss der Thread Aufrufen `Lock`. Jeder Aufruf von `Lock` erfordert einen entsprechenden Aufruf `Unlock` um den Besitz der des kritischen Abschnitts freizugeben.  
  
 Wenn das Threadmodell Singlethread ist, bewirkt diese Methode nichts.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
