---
title: CComPtrBase Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs: C++
helpviewer_keywords: CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f0d9b4d49a7568df905a595e2cf6494b2b98706d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomptrbase-class"></a>CComPtrBase-Klasse
Diese Klasse bietet eine Grundlage für intelligente zeigerklassen Routinen COM-basierten Speicher verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp des intelligenten Zeigers verwiesen werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase:: Advise](#advise)|Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`des Connection Point verwendet und der Senke eines Clients.|  
|[CComPtrBase::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.|  
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|Rufen Sie diese Methode, um ein Objekt der Klasse mit einer angegebenen Klasse oder Programm-ID, zu erstellen.|  
|[CComPtrBase::CopyTo](#copyto)|Rufen Sie diese Methode zum Kopieren der `CComPtrBase` Zeiger auf einen anderen Zeigervariablen.|  
|[CComPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CComPtrBase::IsEqualObject](#isequalobject)|Rufen Sie diese Methode beim Überprüfen der angegebenen **IUnknown** verweist auf das gleiche Objekt zugeordneten der `CComPtrBase` Objekt.|  
|[CComPtrBase::QueryInterface](#queryinterface)|Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückgibt.|  
|[CComPtrBase::Release](#release)|Rufen Sie diese Methode, um die Benutzeroberfläche freigeben.|  
|[CComPtrBase::SetSite](#setsite)|Rufen Sie diese Methode zum Festlegen der Website von der `CComPtrBase` -Objekt an die **IUnknown** des übergeordneten Objekts.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CComPtrBase::operator!](#operator_not)|Der NOT-Operator.|  
|[CComPtrBase::operator &](#operator_amp)|Der &-Operator.|  
|[CComPtrBase::operator *](#operator_star)|Der *-Operator.|  
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Kleiner-als-Operator.|  
|[CComPtrBase::operator ==](#operator_eq_eq)|Den Gleichheitsoperator.|  
|[CComPtrBase::operator ->](#operator_ptr)|Der Zeiger auf Member-Operator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase::p](#p)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt die Grundlage für andere intelligente Zeiger der COM-arbeitsspeicherverwaltungsroutinen, z. B. mit [CComQIPtr](../../atl/reference/ccomqiptr-class.md) und [CComPtr](../../atl/reference/ccomptr-class.md). Die abgeleiteten Klassen hinzufügen, ihre eigenen Konstruktoren und Operatoren, aber abhängig ist, die von bereitgestellten Methoden `CComPtrBase`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  
  
##  <a name="advise"></a>CComPtrBase:: Advise  
 Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`des Connection Point verwendet und der Senke eines Clients.  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 Ein Zeiger auf des Clients **IUnknown**.  
  
 `iid`  
 Die GUID des Verbindungspunkt. Dies ist normalerweise identisch mit der Ausgangsschnittstelle, von dem Verbindungspunkt verwaltet werden.  
  
 `pdw`  
 Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [AtlAdvise](connection-point-global-functions.md#atladvise) für Weitere Informationen.  
  
##  <a name="attach"></a>CComPtrBase::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p2`  
 Die `CComPtrBase` Objekt wird die Besitzrechte des this-Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** Aufrufe [CComPtrBase::Release](#release) auf dem vorhandenen [CComPtrBase::p](#p) Membervariablen gespeichert, und klicken Sie dann weist `p2` auf `CComPtrBase::p`. Wenn eine `CComPtrBase` Objekt übernimmt den Besitz des einen Zeiger, er ruft automatisch `Release` auf dem Zeiger hierbei den Zeiger und alle gelöscht zugeordnet Daten, wenn der Verweiszähler für das Objekt auf 0 geht.  
  
##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase  
 Der Destruktor.  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Schnittstelle frei, die durch `CComPtrBase`.  
  
##  <a name="cocreateinstance"></a>CComPtrBase:: CoCreateInstance  
 Rufen Sie diese Methode, um ein Objekt der Klasse mit einer angegebenen Klasse oder Programm-ID, zu erstellen.  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `szProgID`  
 Ein Zeiger auf eine ProgID her, die zum Wiederherstellen der CLSID.  
  
 `pUnkOuter`  
 Wenn **NULL**, gibt an, dass das Objekt nicht im Rahmen eines Aggregats erstellt wird. Wenn nicht- **NULL**, ist ein Zeiger auf des aggregatobjekts **IUnknown** Schnittstelle (steuernde **IUnknown**).  
  
 `dwClsContext`  
 Der Kontext, in dem der Code, der das neu erstellte Objekt verwaltet ausgeführt wird.  
  
 `rclsid`  
 Die CLSID verknüpft sind mit den Daten und den Code, der zum Erstellen des Objekts verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK auf Erfolg oder REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING oder E_NOINTERFACE zurückgegeben, bei einem Fehler. Finden Sie unter [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) und [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) eine Beschreibung dieser Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Form der Methode aufgerufen wird, [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) wird verwendet, um die CLSID wiederherstellen. Rufen Sie dann beide Formen [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn [CComPtrBase::p](#p) ist nicht gleich NULL.  
  
##  <a name="copyto"></a>CComPtrBase::CopyTo  
 Rufen Sie diese Methode zum Kopieren der `CComPtrBase` Zeiger auf einen anderen Zeigervariablen.  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *ppT*  
 Adresse der Variablen der empfängt die `CComPtrBase` Zeiger.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei E_POINTER bei Erfolg S_OK zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Kopiert die `CComPtrBase` Zeiger auf *ppT*. Den Verweiszähler für den [CComPtrBase::p](#p) Membervariable wird erhöht.  
  
 Fehler-HRESULT zurückgegeben wird, wenn *ppT* gleich NULL. Debug-Builds wird ein Assertionsfehler auftreten, wenn *ppT* gleich NULL.  
  
##  <a name="detach"></a>CComPtrBase::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird dadurch die [CComPtrBase::p](#p) Data-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück.  
  
##  <a name="isequalobject"></a>CComPtrBase::IsEqualObject  
 Rufen Sie diese Methode beim Überprüfen der angegebenen **IUnknown** verweist auf das gleiche Objekt zugeordneten der `CComPtrBase` Objekt.  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pOther`  
 Die **IUnknown \***  , verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Objekte identisch, andernfalls false sind.  
  
##  <a name="operator_not"></a>CComPtrBase::operator!  
 Der NOT-Operator.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die `CComHeapPtr` Zeiger gleich NULL, "false" andernfalls.  
  
##  <a name="operator_amp"></a>CComPtrBase::operator&amp;  
 Der &-Operator.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des Objekts verweist, zu der `CComPtrBase` Objekt.  
  
##  <a name="operator_star"></a>CComPtrBase::operator *  
 Der *-Operator.  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CComPtrBase::p](#p); d. h. ein Zeiger auf das Objekt verwiesen wird, indem Sie die `CComPtrBase` Objekt.  
  
 Wenn Debug erstellt wird, wird ein Assertionsfehler auftreten, wenn [CComPtrBase::p](#p) ist nicht gleich NULL.  
  
##  <a name="operator_eq_eq"></a>CComPtrBase::operator ==  
 Den Gleichheitsoperator.  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 Ein Zeiger auf ein Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn `CComPtrBase` und *pT* zeigen Sie auf das gleiche Objekt "false" andernfalls.  
  
##  <a name="operator_ptr"></a>CComPtrBase::operator-&gt;  

 Der Pointer-to-Member-Operator.  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CComPtrBase::p](#p) Daten Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse, die durch die `CComPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CComPtrBase` -Datenmember auf NULL verweist.  
  
##  <a name="operator_lt"></a>CComPtrBase::operator&lt;  
 Kleiner-als-Operator.  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 Ein Zeiger auf ein Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Zeiger vom aktuellen Objekt verwaltet ist kleiner als der Zeiger mit dem verglichen wird.  
  
##  <a name="operator_t_star"></a>CComPtrBase::operator T *  
 Der Cast-Operator.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.  
  
##  <a name="p"></a>CComPtrBase::p  
 Die Zeiger-Membervariable.  
  
```
T* p;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält die Zeigerinformationen zur.  
  
##  <a name="queryinterface"></a>CComPtrBase::QueryInterface  
 Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückgibt.  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `Q`  
 Der Objekttyp, dessen Schnittstellenzeiger erforderlich ist.  
  
 `pp`  
 Adresse des Output-Variable, die den angeforderten Schnittstellenzeiger empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK auf Erfolg oder E_NOINTERFACE zurückgegeben, bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [IUnknown:: QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn *pp* ist nicht gleich NULL.  
  
##  <a name="release"></a>CComPtrBase::Release  
 Rufen Sie diese Methode, um die Benutzeroberfläche freigeben.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle wird freigegeben und [CComPtrBase::p](#p) auf NULL festgelegt ist.  
  
##  <a name="setsite"></a>CComPtrBase::SetSite  
 Rufen Sie diese Methode zum Festlegen der Website von der `CComPtrBase` -Objekt an die **IUnknown** des übergeordneten Objekts.  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `punkParent`  
 Ein Zeiger auf die **IUnknown** Schnittstelle des übergeordneten Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
