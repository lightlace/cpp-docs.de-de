---
title: IEnumOnSTLImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 0ec505871f057d90f6580e547c23a0879af4c3f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638749"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl-Klasse

Diese Klasse definiert eine Enumeratorschnittstelle, die auf Grundlage einer C++-Standardbibliothek-Auflistung.

## <a name="syntax"></a>Syntax

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Ein COM-Enumerator. Finden Sie unter [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) verdeutlicht.

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.

*Kopieren*<br/>
Ein [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).

*CollType*<br/>
Eine C++-Standardbibliothek-Container-Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|Die Implementierung der **Klon**.|
|[IEnumOnSTLImpl::Init](#init)|Initialisiert den Enumerator.|
|[IEnumOnSTLImpl::Next](#next)|Die Implementierung der **Weiter**.|
|[IEnumOnSTLImpl::Reset](#reset)|Die Implementierung der **zurücksetzen**.|
|[IEnumOnSTLImpl::Skip](#skip)|Die Implementierung der **überspringen**.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|Der Iterator, der die Position des Enumerators aktuelle in der Auflistung darstellt.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Ein Zeiger auf den C++-Standardbibliothek-Container enthält die Elemente aufgelistet werden sollen.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|Die `IUnknown` Zeiger, der das Objekt, das die Sammlung angeben.|

## <a name="remarks"></a>Hinweise

`IEnumOnSTLImpl` Stellt die Implementierung für eine COM-Enumerator-Schnittstelle, in dem die Elemente, die aufgezählt werden in einem C++-Standard-Bibliothek-kompatible Container gespeichert werden. Diese Klasse ist analog zu den [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) -Klasse, die eine Implementierung für eine Enumeratorschnittstelle bereitstellt, basierend auf einem Wertearray.

> [!NOTE]
>  Finden Sie unter [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`.

Sehen Sie in der Regel *nicht* müssen Ihren eigenen Enumerator-Klasse durch Ableiten von dieser Implementierung der Schnittstelle zu erstellen. Wenn Sie einen ATL bereitgestellten Enumerator, der basierend auf einem C++-Standardbibliothek-Container verwenden möchten, ist es eher üblich, zum Erstellen einer Instanz von [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), oder erstellen eine Auflistungsklasse, die einen Enumerator durch Ableiten von zurückgibt[ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).

Sie benötigen, geben Sie einen benutzerdefinierten Enumerator (z. B. eine, die Schnittstellen, die zusätzlich zu den Enumerator-Schnittstelle verfügbar macht), können Sie von dieser Klasse ableiten. In diesem Fall ist es wahrscheinlich, dass Sie außer Kraft setzen müssen die [Klon](#clone) Methode, um Ihre eigene Implementierung bereitzustellen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="init"></a>  IEnumOnSTLImpl::Init

Initialisiert den Enumerator.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parameter

*pUnkForRelease*<br/>
[in] Die `IUnknown` Zeiger, der ein Objekt, das während der Lebensdauer des Enumerators beibehalten werden muss. Übergeben Sie NULL, wenn kein entsprechendes Objekt vorhanden ist.

*Auflistung*<br/>
Ein Verweis auf den C++-Standardbibliothek-Container, der aufzulistenden Elemente enthält.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn Sie übergeben `Init` frei, die ein Verweis auf eine Auflistung in ein anderes Objekt können Sie die *pUnkForRelease* Parameter, um sicherzustellen, dass das Objekt und der Auflistung, die er hält, ist für verfügbar, solange der Enumerator benötigt.

Sie müssen diese Methode aufrufen, bevor Sie die Übergabe eines Zeigers auf die Enumeratorschnittstelle an alle Clients.

##  <a name="clone"></a>  IEnumOnSTLImpl::Clone

Diese Methode bietet die Implementierung der **Klon** Methode erstellen Sie ein Objekt vom Typ `CComEnumOnSTL`, initialisieren mit der gleichen Auflistung und Iterator vom aktuellen Objekt verwendet, und der Schnittstelle bei der neu erstellte Objekt.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parameter

*ppEnum*<br/>
[out] Die Enumeratorschnittstelle für ein neu erstelltes Objekt, das von der aktuelle Enumerator geklont werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk

Die `IUnknown` Zeiger, der das Objekt, das die Sammlung angeben.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Hinweise

Dieses intelligenten Zeigers behält einen Verweis auf das Objekt, übergeben [IEnumOnSTLImpl::Init](#init), um sicherzustellen, dass es während der Lebensdauer des Enumerators aktiv bleibt.

##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection

Dieses Element verweist auf die Auflistung, die die Daten, die für die Implementierung der Enumeratorschnittstelle bereitstellt.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Hinweise

Dieser Member wird initialisiert, durch einen Aufruf von [IEnumOnSTLImpl::Init](#init).

##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter

Dieser Member enthält den Iterator verwendet, um die aktuelle Position in der Auflistung zu markieren, und navigieren zu nachfolgenden Elemente.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>  IEnumOnSTLImpl::Next

Diese Methode bietet die Implementierung der **Weiter** Methode.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Parameter

*"celt"*<br/>
[in] Die Anzahl der angeforderten Elemente.

*rgelt*<br/>
[out] Das Array, das mit den Elementen gefüllt werden.

*pceltFetched*<br/>
[out] Die Anzahl der Elemente im tatsächlich zurückgegebenen *Rgelt*. Dies liegt möglicherweise weniger als *"celt"* Wenn weniger als *"celt"* Elemente bleiben in der Liste.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="reset"></a>  IEnumOnSTLImpl::Reset

Diese Methode bietet die Implementierung der **zurücksetzen** Methode.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="skip"></a>  IEnumOnSTLImpl::Skip

Diese Methode bietet die Implementierung der **überspringen** Methode.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parameter

*"celt"*<br/>
[in] Die Anzahl der zu überspringenden Elemente.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
