---
title: CComPtrBase-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 5bb599b88671447e219421efacac7a2d8a5f7b06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246230"
---
# <a name="ccomptrbase-class"></a>CComPtrBase-Klasse

Diese Klasse bietet eine Grundlage für intelligente Zeiger-Klassen, die mit COM-basierten Speicher Routinen.

## <a name="syntax"></a>Syntax

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Objekttyp des intelligenten Zeigers verwiesen werden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::~CComPtrBase](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::Advise](#advise)|Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`Verbindungspunkt und der Senke eines Clients.|
|[CComPtrBase::Attach](#attach)|Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Rufen Sie diese Methode, um ein Objekt der Klasse eine angegebene Klasse oder Programm-ID zugeordnet zu erstellen.|
|[CComPtrBase::CopyTo](#copyto)|Rufen Sie diese Methode kopiert die `CComPtrBase` Zeiger auf einen anderen Zeigervariable.|
|[CComPtrBase::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.|
|[CComPtrBase::IsEqualObject](#isequalobject)|Rufen Sie diese Methode überprüft, ob das angegebene `IUnknown` verweist auf das gleiche Objekt zugeordnete der `CComPtrBase` Objekt.|
|[CComPtrBase::QueryInterface](#queryinterface)|Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.|
|[CComPtrBase::Release](#release)|Rufen Sie diese Methode, um die Benutzeroberfläche freigeben.|
|[CComPtrBase::SetSite](#setsite)|Rufen Sie diese Methode zum Festlegen der Website von der `CComPtrBase` -Objekt an die `IUnknown` des übergeordneten Objekts.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::operator T*](#operator_t_star)|Der Cast-Operator.|
|[CComPtrBase::operator!](#operator_not)|Der NOT-Operator.|
|[CComPtrBase::operator &](#operator_amp)|Die & Operator.|
|[CComPtrBase::operator *](#operator_star)|Der Operator \*.|
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Das kleiner-als-Operator.|
|[CComPtrBase::operator ==](#operator_eq_eq)|Der Gleichheitsoperator.|
|[CComPtrBase::operator ->](#operator_ptr)|Der Zeiger auf Member-Operator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComPtrBase::p](#p)|Die Zeiger-Membervariable.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt die Grundlage für andere intelligente Zeiger auf die COM-arbeitsspeicherverwaltungsroutinen, z. B. verwenden [CComQIPtr](../../atl/reference/ccomqiptr-class.md) und [CComPtr](../../atl/reference/ccomptr-class.md). Die abgeleitete Klassen ihre eigenen Konstruktoren und Operatoren hinzufügen, aber abhängig vom bereitgestellten Methoden `CComPtrBase`.

## <a name="requirements"></a>Anforderungen

**Header:** atlcomcli.h

##  <a name="advise"></a>  CComPtrBase:: Advise

Rufen Sie diese Methode zum Erstellen einer Verbindung zwischen dem `CComPtrBase`Verbindungspunkt und der Senke eines Clients.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parameter

*pUnk*<br/>
Ein Zeiger auf des Clients `IUnknown`.

*iid*<br/>
Die GUID des Verbindungspunkts. Dies ist normalerweise identisch mit der von den Verbindungspunkt verwalteten Ausgangsschnittstelle.

*pdw*<br/>
Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [AtlAdvise](connection-point-global-functions.md#atladvise) für Weitere Informationen.

##  <a name="attach"></a>  CComPtrBase::Attach

Rufen Sie diese Methode, um den Besitz eines bestehenden Zeigers zu übernehmen.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parameter

*p2*<br/>
Die `CComPtrBase` Objekt übernimmt dann den Besitz des this-Zeigers.

### <a name="remarks"></a>Hinweise

`Attach` Aufrufe [CComPtrBase::Release](#release) auf dem vorhandenen [CComPtrBase::p](#p) Membervariablen gespeichert, und klicken Sie dann weist *p2* zu `CComPtrBase::p`. Wenn eine `CComPtrBase` Objekt übernimmt den Besitz eines Zeigers, ruft es automatisch `Release` auf dem Zeiger auf die der Zeiger und eine gelöscht werden zugeordnete Daten, wenn der Verweiszähler für das Objekt auf 0 zurückgeht.

##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase

Der Destruktor.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Hinweise

Gibt die Schnittstelle frei verweist `CComPtrBase`.

##  <a name="cocreateinstance"></a>  CComPtrBase:: CoCreateInstance

Rufen Sie diese Methode, um ein Objekt der Klasse eine angegebene Klasse oder Programm-ID zugeordnet zu erstellen.

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

*szProgID*<br/>
Zeiger auf ein Programm-ID verwendet, um die CLSID wiederherzustellen.

*pUnkOuter*<br/>
Wenn der Wert NULL ist, gibt Sie an, dass das Objekt nicht als Teil eines Aggregats erstellt wird. Wenn nicht NULL ist, ist ein Zeiger auf des aggregatobjekts `IUnknown` Schnittstelle (das steuernde `IUnknown`).

*dwClsContext*<br/>
Der Kontext, in dem der Code, der das neu erstellte Objekt verwaltet ausgeführt wird.

*rclsid*<br/>
Die CLSID zugeordnet, die Daten und Code, der zum Erstellen des Objekts verwendet wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück auf Erfolg oder REGDB_E_CLASSNOTREG CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING oder E_NOINTERFACE bei einem Fehler. Finden Sie unter [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) und [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) eine Beschreibung dieser Fehler.

### <a name="remarks"></a>Hinweise

Wenn die erste Form der Methode aufgerufen wird, [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) wird verwendet, um die CLSID wiederherstellen. Rufen Sie dann beide Formen [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

In Debugbuilds wird ein Assertionsfehler auftreten, wenn [CComPtrBase::p](#p) ist nicht gleich NULL.

##  <a name="copyto"></a>  CComPtrBase::CopyTo

Rufen Sie diese Methode kopiert die `CComPtrBase` Zeiger auf einen anderen Zeigervariable.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parameter

*ppT*<br/>
Adresse der Variablen der empfängt die `CComPtrBase` Zeiger.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg E_POINTER bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Kopiert die `CComPtrBase` Zeiger auf *ppT*. Den Verweiszähler für den [CComPtrBase::p](#p) Membervariable wird erhöht.

Fehler-HRESULT zurückgegeben, wenn *ppT* gleich NULL ist. In Debugbuilds wird ein Assertionsfehler auftreten, wenn *ppT* gleich NULL ist.

##  <a name="detach"></a>  CComPtrBase::Detach

Rufen Sie diese Methode, um den Besitz eines Zeigers freizugeben.

```
T* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Kopie des Zeigers.

### <a name="remarks"></a>Hinweise

Gibt den Besitz eines Zeigers, legt die [CComPtrBase::p](#p) Data-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück.

##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject

Rufen Sie diese Methode überprüft, ob das angegebene `IUnknown` verweist auf das gleiche Objekt zugeordnete der `CComPtrBase` Objekt.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parameter

*pOther*<br/>
Der zu vergleichende `IUnknown *`.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Objekte identisch, andernfalls false sind.

##  <a name="operator_not"></a>  CComPtrBase::operator!

Der NOT-Operator.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die `CComHeapPtr` Zeiger gleich NULL ist, wird "false" andernfalls.

##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;

Die & Operator.

```
T** operator&() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse des Objekts verweist die `CComPtrBase` Objekt.

##  <a name="operator_star"></a>  CComPtrBase::operator \*

Der Operator \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert der [CComPtrBase::p](#p); d. h. ein Zeiger auf das Objekt, das auf die `CComPtrBase` Objekt.

Wenn Debug erstellt wird, wird ein Assertionsfehler auftreten, wenn [CComPtrBase::p](#p) ist nicht gleich NULL.

##  <a name="operator_eq_eq"></a>  CComPtrBase::operator ==

Der Gleichheitsoperator.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parameter

*pT*<br/>
Ein Zeiger auf ein Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn `CComPtrBase` und *pT* zeigen Sie auf das gleiche Objekt "false" andernfalls.

##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;

Der Zeiger-auf-Member-Operator.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert des der [CComPtrBase::p](#p) Daten Membervariablen gespeichert.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist die `CComPtrBase` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CComPtrBase` -Datenmember auf NULL.

##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;

Das kleiner-als-Operator.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parameter

*pT*<br/>
Ein Zeiger auf ein Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Zeiger vom aktuellen Objekt verwaltet ist kleiner als der Zeiger mit dem verglichen wird.

##  <a name="operator_t_star"></a>  CComPtrBase::operator T\*

Der Cast-Operator.

```
operator T*() const throw();
```

### <a name="remarks"></a>Hinweise

Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.

##  <a name="p"></a>  CComPtrBase::p

Die Zeiger-Membervariable.

```
T* p;
```

### <a name="remarks"></a>Hinweise

Diese Membervariable enthält Zeigerinformationen.

##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface

Rufen Sie diese Methode, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parameter

*Q*<br/>
Der Objekttyp, dessen Schnittstellenzeiger erforderlich ist.

*pp*<br/>
Adresse des Output-Variable, die den angeforderten Schnittstellenzeiger empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder E_NOINTERFACE bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [IUnknown:: QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

In Debugbuilds wird ein Assertionsfehler auftreten, wenn *pp* ist nicht gleich NULL.

##  <a name="release"></a>  CComPtrBase::Release

Rufen Sie diese Methode, um die Benutzeroberfläche freigeben.

```
void Release() throw();
```

### <a name="remarks"></a>Hinweise

Die Schnittstelle freigegeben wird, und [CComPtrBase::p](#p) auf NULL festgelegt ist.

##  <a name="setsite"></a>  CComPtrBase::SetSite

Rufen Sie diese Methode zum Festlegen der Website von der `CComPtrBase` -Objekt an die `IUnknown` des übergeordneten Objekts.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parameter

*punkParent*<br/>
Ein Zeiger auf die `IUnknown` Schnittstelle des übergeordneten Elements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
