---
title: CComPtrBase Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 28207e483b0bf56b9e3e98f487d174b8ae47e9e7
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptrbase-class"></a>CComPtrBase-Klasse
Diese Klasse bietet eine Grundlage für intelligente Zeiger-Klassen, die mit COM-basierten Speicher Routinen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp des intelligenten Zeigers verwiesen werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase:: Advise](#advise)|Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`des Verbindungspunkts und der Senke eines Clients.|  
|[CComPtrBase::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.|  
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|Rufen Sie diese Methode, um ein Objekt der Klasse, die mit einer angegebenen Klasse oder Programm-ID erstellen|  
|[CComPtrBase::CopyTo](#copyto)|Rufen Sie diese Methode zum Kopieren der `CComPtrBase` Zeiger auf einen anderen Zeigervariable.|  
|[CComPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CComPtrBase::IsEqualObject](#isequalobject)|Rufen Sie diese Methode überprüft, ob das angegebene **IUnknown** verweist auf das gleiche Objekt zugeordneten der `CComPtrBase` Objekt.|  
|[CComPtrBase::QueryInterface](#queryinterface)|Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.|  
|[CComPtrBase::Release](#release)|Rufen Sie diese Methode zum Freigeben der Schnittstelle.|  
|[CComPtrBase::SetSite](#setsite)|Rufen Sie diese Methode zum Festlegen des Standorts der `CComPtrBase` -Objekt an die **IUnknown** des übergeordneten Objekts.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CComPtrBase::operator!](#operator_not)|Der NOT-Operator.|  
|[CComPtrBase::operator &](#operator_amp)|Die & -Operator.|  
|[CComPtrBase::operator *](#operator_star)|Die * Operator.|  
|[CComPtrBase::operator](#ccomptrbase__operator lt)|Das kleiner-als-Operator.|  
|[CComPtrBase::operator ==](#operator_eq_eq)|Den Gleichheitsoperator.|  
|[CComPtrBase::operator->](#operator_ptr)|Der Operator für Zeiger auf Member.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtrBase::p](#p)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt die Basis für andere intelligente Zeiger für die Verwendung von COM-arbeitsspeicherverwaltungsroutinen, wie [CComQIPtr](../../atl/reference/ccomqiptr-class.md) und [CComPtr](../../atl/reference/ccomptr-class.md). Die abgeleiteten Klassen eigene Konstruktoren und Operatoren hinzufügen, aber abhängig von den Methoden von `CComPtrBase`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcomcli.h  
  
##  <a name="advise"></a>CComPtrBase:: Advise  
 Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`des Verbindungspunkts und der Senke eines Clients.  
  
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
 Die GUID des Verbindungspunkts. In der Regel ist dies die von den Verbindungspunkt verwalteten Ausgangsschnittstelle identisch.  
  
 `pdw`  
 Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [AtlAdvise](http://msdn.microsoft.com/library/625a2f03-6b7f-4761-be5d-d2871d1d3254) Weitere Informationen.  
  
##  <a name="attach"></a>CComPtrBase::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p2`  
 Das `CComPtrBase` Objekt wird die Besitzrechte des this-Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** Aufrufe [CComPtrBase::Release](#release) des vorhandenen [CComPtrBase::p](#p) Membervariable und weist anschließend `p2` zu `CComPtrBase::p`. Wenn ein `CComPtrBase` Objekt übernimmt den Besitz eines Zeigers, er ruft automatisch `Release` auf dem Zeiger auf den Zeiger und alle entfernen, wird reservierte Daten, wenn der Verweiszähler für das Objekt auf 0 zurückgeht.  
  
##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase  
 Der Destruktor.  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Schnittstelle, die auf den `CComPtrBase`.  
  
##  <a name="cocreateinstance"></a>CComPtrBase:: CoCreateInstance  
 Rufen Sie diese Methode, um ein Objekt der Klasse, die mit einer angegebenen Klasse oder Programm-ID erstellen  
  
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
 Ein Zeiger auf eine ProgID, die zum Wiederherstellen der CLSID.  
  
 `pUnkOuter`  
 Wenn **NULL**, gibt an, dass das Objekt nicht als Teil der Aggregatfunktion erstellt wird. Bei nicht - **NULL**, ist ein Zeiger auf des aggregatobjekts **IUnknown** Schnittstelle (steuernde **IUnknown**).  
  
 `dwClsContext`  
 Der Kontext, in dem der Code, der das neu erstellte Objekt verwaltet ausgeführt wird.  
  
 `rclsid`  
 Die CLSID zugeordneten Daten und Code, der zum Erstellen des Objekts verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück auf Erfolg oder REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING oder E_NOINTERFACE bei einem Fehler. Finden Sie unter [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) und [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) eine Beschreibung dieser Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Form der Methode aufgerufen wird, [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) wird verwendet, um die CLSID wiederherstellen. Rufen Sie dann beide Formen [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn [CComPtrBase::p](#p) ist ungleich NULL.  
  
##  <a name="copyto"></a>CComPtrBase::CopyTo  
 Rufen Sie diese Methode zum Kopieren der `CComPtrBase` Zeiger auf einen anderen Zeigervariable.  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *ppT*  
 Adresse der Variablen der empfängt die `CComPtrBase` Zeiger.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei E_POINTER bei Erfolg S_OK zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Kopiert die `CComPtrBase` Zeiger auf *ppT*. Den Verweiszähler für die [CComPtrBase::p](#p) Membervariable wird erhöht.  
  
 Fehler-HRESULT zurückgegeben wird, wenn *ppT* gleich NULL ist. In Debugbuilds wird ein Assertionsfehler auftreten, wenn *ppT* gleich NULL ist.  
  
##  <a name="detach"></a>CComPtrBase::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird die [CComPtrBase::p](#p) Daten-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück.  
  
##  <a name="isequalobject"></a>CComPtrBase::IsEqualObject  
 Rufen Sie diese Methode überprüft, ob das angegebene **IUnknown** verweist auf das gleiche Objekt zugeordneten der `CComPtrBase` Objekt.  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pOther`  
 Die **IUnknown \* ** , verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Objekte identisch, andernfalls false sind.  
  
##  <a name="operator_not"></a>CComPtrBase::operator!  
 Der NOT-Operator.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die `CComHeapPtr` Zeiger ist gleich NULL, false, andernfalls.  
  
##  <a name="operator_amp"></a>CComPtrBase::operator&amp;  
 Die & -Operator.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des Objekts, auf das das `CComPtrBase` Objekt.  
  
##  <a name="operator_star"></a>CComPtrBase::operator *  
 Die * Operator.  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CComPtrBase::p](#p); d. h. ein Zeiger auf das Objekt, auf die `CComPtrBase` Objekt.  
  
 Wenn Debug erstellt wird, wird ein Assertionsfehler angezeigt, wenn [CComPtrBase::p](#p) ist ungleich NULL.  
  
##  <a name="operator_eq_eq"></a>CComPtrBase::operator ==  
 Den Gleichheitsoperator.  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 Ein Zeiger auf ein Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn `CComPtrBase` und *pT* zeigen auf dasselbe Objekt false andernfalls.  
  
##  <a name="operator_ptr"></a>CComPtrBase::operator-&gt;  

 Der Zeiger-auf-Member-Operator.  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CComPtrBase::p](#p) Daten Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist, auf die `CComPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn der `CComPtrBase` -Datenmember auf NULL zeigt.  
  
##  <a name="operator_lt"></a>CComPtrBase::operator&lt;  
 Das kleiner-als-Operator.  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *pT*  
 Ein Zeiger auf ein Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn der Zeiger vom aktuellen Objekt verwaltet ist kleiner als der Zeiger mit dem verglichen wird.  
  
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
 Diese Membervariable enthält Zeigerinformationen.  
  
##  <a name="queryinterface"></a>CComPtrBase::QueryInterface  
 Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `Q`  
 Der Objekttyp, dessen Schnittstellenzeiger erforderlich ist.  
  
 `pp`  
 Adresse einer Ausgabevariable, die den angeforderten Schnittstellenzeiger empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder E_NOINTERFACE zurück, bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [IUnknown:: QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn *pp* ist ungleich NULL.  
  
##  <a name="release"></a>CComPtrBase::Release  
 Rufen Sie diese Methode zum Freigeben der Schnittstelle.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Schnittstelle freigegeben wird, und [CComPtrBase::p](#p) auf NULL festgelegt ist.  
  
##  <a name="setsite"></a>CComPtrBase::SetSite  
 Rufen Sie diese Methode zum Festlegen des Standorts der `CComPtrBase` -Objekt an die **IUnknown** des übergeordneten Objekts.  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `punkParent`  
 Ein Zeiger auf die **IUnknown** Schnittstelle des übergeordneten Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [AtlSetChildSite](http://msdn.microsoft.com/library/2a8ece19-6bfd-4e89-9d1d-e5a78f95e2df).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

