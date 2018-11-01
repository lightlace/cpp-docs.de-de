---
title: CComEnumImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: 2104d98cbc068eb5d8f1408cdda0898fd55c9473
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467144"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl-Klasse

Diese Klasse stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem Array gespeichert werden.

## <a name="syntax"></a>Syntax

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Eine COM-Enumerator-Schnittstelle. Finden Sie unter [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) verdeutlicht.

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.

*Kopieren*<br/>
Eine homogene [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Der Konstruktor.|
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComEnumImpl::Clone](#clone)|Die Implementierung der **Klon** Enumerationsmethode-Schnittstelle.|
|[CComEnumImpl::Init](#init)|Initialisiert den Enumerator.|
|[CComEnumImpl::Next](#next)|Die Implementierung der **Weiter**.|
|[CComEnumImpl::Reset](#reset)|Die Implementierung der **zurücksetzen**.|
|[CComEnumImpl:: Skip](#skip)|Die Implementierung der **überspringen**.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|Ein Zeiger auf das erste Element im Array.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Kopieren Sie die Flags übergeben `Init`.|
|[CComEnumImpl::m_end](#m_end)|Ein Zeiger auf die Position direkt hinter das letzte Element im Array.|
|[CComEnumImpl::m_iter](#m_iter)|Ein Zeiger auf das aktuelle Element im Array.|
|[CComEnumImpl::m_spUnk](#m_spunk)|Die `IUnknown` Zeiger, der das Objekt, das Angeben der Auflistung aufgezählt werden.|

## <a name="remarks"></a>Hinweise

Finden Sie unter [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) ein Beispiel für Implementierungen der Dienstmethode. `CComEnumImpl` Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem Array gespeichert werden. Diese Klasse ist analog zu den `IEnumOnSTLImpl` -Klasse, die eine Implementierung einer Enumerator-Schnittstelle bereitstellt, basierend auf einem C++-Standardbibliothek-Container.

> [!NOTE]
>  Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`, finden Sie unter [CComEnumImpl::Init](#init).

Sehen Sie in der Regel *nicht* müssen Ihren eigenen Enumerator-Klasse durch Ableiten von dieser Implementierung der Schnittstelle zu erstellen. Wenn Sie einen basierten auf einem Wertearray ATL bereitgestellter-Enumerator verwenden möchten, ist es eher üblich, zum Erstellen einer Instanz von [CComEnum](../../atl/reference/ccomenum-class.md).

Sie benötigen, geben Sie einen benutzerdefinierten Enumerator (z. B. eine, die Schnittstellen, die zusätzlich zu den Enumerator-Schnittstelle verfügbar macht), können Sie von dieser Klasse ableiten. In diesem Fall ist es wahrscheinlich, dass Sie außer Kraft setzen müssen die [CComEnumImpl::Clone](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.

Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`CComEnumImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="ccomenumimpl"></a>  CComEnumImpl::CComEnumImpl

Der Konstruktor.

```
CComEnumImpl();
```

##  <a name="dtor"></a>  CComEnumImpl:: ~ CComEnumImpl

Der Destruktor.

```
~CComEnumImpl();
```

##  <a name="init"></a>  CComEnumImpl::Init

Sie müssen diese Methode aufrufen, bevor Sie die Übergabe eines Zeigers auf die Enumeratorschnittstelle an alle Clients.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>Parameter

*begin*<br/>
Ein Zeiger auf das erste Element des Arrays mit den Elementen aufgelistet werden sollen.

*end*<br/>
Ein Zeiger auf die Position direkt hinter dem letzten Element des Arrays mit den Elementen aufgelistet werden sollen.

*pUnk*<br/>
[in] Die `IUnknown` Zeiger, der ein Objekt, das während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie NULL, wenn kein entsprechendes Objekt vorhanden ist.

*flags*<br/>
Flags, die unabhängig davon, ob der Enumerator des Besitzes des Arrays übernehmen sollte, oder erstellen Sie eine Kopie des Zertifikats angeben. Mögliche Werte werden nachfolgend beschrieben.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode nur einmal, den Enumerator zu initialisieren, verwenden Sie diese, und schon.

Wenn Sie Verweise auf Elemente in einem Array in ein anderes Objekt gespeicherten übergeben (und Sie nicht den Enumerator zum Kopieren der Daten stellen), können Sie mithilfe der *pUnk* Parameter, um sicherzustellen, dass das Objekt und das Array ist so lange wie den Enumerator verfügbar sind. benötigt. Der Enumerator enthält lediglich einen COM-Verweis auf das Objekt, das am Leben zu erhalten. COM-Verweises wird automatisch freigegeben, wenn der Enumerator zerstört wird.

Die *Flags* Parameter können Sie angeben, wie der Enumerator für Elemente des Arrays, die an sie übergebenen behandeln soll. *Flags* kann einen der Werte aus annehmen der `CComEnumFlags` Enumeration, die unten gezeigten:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy` bedeutet, dass die Lebensdauer des Arrays nicht vom Enumerator gesteuert wird. In diesem Fall entweder das Array werden statische oder das Objekt, das identifizierte *pUnk* ist zuständig für das Array freigeben, wenn es nicht mehr benötigt wird.

`AtlFlagTakeOwnership` bedeutet, dass die Zerstörung des Arrays vom Enumerator gesteuert werden. In diesem Fall das Array muss dynamisch zugeteilt wurde mit **neue**. Der Enumerator wird das Array in seinem Destruktor gelöscht. In der Regel, übergeben Sie NULL für *pUnk*, obwohl Sie immer noch einen gültigen Zeiger übergeben können, wenn Sie über die Zerstörung des Enumerators aus irgendeinem Grund benachrichtigt werden möchten.

`AtlFlagCopy` bedeutet, dass ein neues Array erstellt werden, kopieren Sie das Parameterarray übergeben `Init`. Lebensdauer für das neue Array besteht darin, über den Enumerator gesteuert werden. Der Enumerator wird das Array in seinem Destruktor gelöscht. In der Regel, übergeben Sie NULL für *pUnk*, obwohl Sie immer noch einen gültigen Zeiger übergeben können, wenn Sie über die Zerstörung des Enumerators aus irgendeinem Grund benachrichtigt werden möchten.

> [!NOTE]
>  Der Prototyp dieser Methode gibt die Elemente des Arrays als Typ `T`, wobei `T` als Vorlagenparameter für die Klasse definiert wurde. Dies ist der gleiche Typ, die mithilfe der COM-Schnittstellenmethode verfügbar gemacht wird [CComEnumImpl::Next](#next). Die Implikation hiervon ist, dass im Gegensatz zu [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), diese Klasse unterstützt keine anderen Speicher und Datentypen verfügbar. Der Datentyp der Elemente im Array muss identisch mit dem Datentyp, der mithilfe der COM-Schnittstelle verfügbar gemacht werden.

##  <a name="clone"></a>  CComEnumImpl::Clone

Diese Methode bietet die Implementierung von der **Klon** Methode erstellen Sie ein Objekt des Typs `CComEnum`, initialisieren es mit dem gleichen Array und dem angegebenen Iterator vom aktuellen Objekt verwendet und die Schnittstelle für das neu erstellte zurückgeben -Objekt.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parameter

*ppEnum*<br/>
[out] Die Enumeratorschnittstelle für ein neu erstelltes Objekt, das von der aktuelle Enumerator geklont werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die geklonte Enumeratoren Sie niemals mit ihren eigenen kopieren (oder den Besitz übernehmen), der vom ursprünglichen Enumerator verwendeten Daten. Bei Bedarf werden geklonte Enumeratoren den ursprünglichen Enumerator (mit einem COM-Verweis) aufrechtzuerhalten um sicherzustellen, dass die Daten für die verfügbar sind, solange sie sie benötigen.

##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk

Dieses intelligenten Zeigers behält einen Verweis auf das Objekt, übergeben [CComEnumImpl::Init](#init), um sicherzustellen, dass es während der Lebensdauer des Enumerators aktiv bleibt.

```
CComPtr<IUnknown> m_spUnk;
```

##  <a name="m_begin"></a>  CComEnumImpl::m_begin

Ein Zeiger auf die Position direkt hinter dem letzten Element des Arrays mit den Elementen aufgelistet werden sollen.

```
T* m_begin;
```

##  <a name="m_end"></a>  CComEnumImpl::m_end

Ein Zeiger auf das erste Element des Arrays mit den Elementen aufgelistet werden sollen.

```
T* m_end;
```

##  <a name="m_iter"></a>  CComEnumImpl::m_iter

Ein Zeiger auf das aktuelle Element des Arrays mit den Elementen aufgelistet werden sollen.

```
T* m_iter;
```

##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags

Die Flags übergeben an [CComEnumImpl::Init](#init).

```
DWORD m_dwFlags;
```

##  <a name="next"></a>  CComEnumImpl::Next

Diese Methode bietet die Implementierung der **Weiter** Methode.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>Parameter

*"celt"*<br/>
[in] Die Anzahl der angeforderten Elemente.

*rgelt*<br/>
[out] Das Array mit Elementen gefüllt werden soll.

*pceltFetched*<br/>
[out] Die Anzahl der Elemente im tatsächlich zurückgegebenen *Rgelt*. Dies liegt möglicherweise weniger als *"celt"* Wenn weniger als *"celt"* Elemente bleibt in der Liste.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="reset"></a>  CComEnumImpl::Reset

Diese Methode bietet die Implementierung der **zurücksetzen** Methode.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="skip"></a>  CComEnumImpl:: Skip

Diese Methode bietet die Implementierung der **überspringen** Methode.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parameter

*"celt"*<br/>
[in] Die Anzahl der zu überspringenden Elemente.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Gibt E_INVALIDARG zurück, wenn *"celt"* 0 (null) ist, gibt S_FALSE zurück, wenn es weniger als *"celt"* Elemente zurückgegeben werden, gibt S_OK zurück, andernfalls.

## <a name="see-also"></a>Siehe auch

[IEnumOnSTLImpl-Klasse](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum-Klasse](../../atl/reference/ccomenum-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
