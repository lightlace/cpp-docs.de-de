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
ms.openlocfilehash: 7cf777f3ff0d298f224157735a06bf57a2c10cf5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495862"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl-Klasse

Diese Klasse definiert eine Enumeratorschnittstelle, die auf C++ einer Standard Bibliotheks Auflistung basiert.

## <a name="syntax"></a>Syntax

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Ein com-Enumerator. Ein Beispiel finden Sie unter " [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) ".

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, das von der Enumeratorschnittstelle verfügbar gemacht wird.

*Kopieren*<br/>
Eine [Kopier Richtlinien Klasse](../../atl/atl-copy-policy-classes.md).

*Colltype*<br/>
Eine C++ Container Klasse der Standard Bibliothek.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|Die Implementierung von **Clone**.|
|[IEnumOnSTLImpl::Init](#init)|Initialisiert den Enumerator.|
|[IEnumOnSTLImpl::Next](#next)|Die Implementierung von **Next**.|
|[IEnumOnSTLImpl::Reset](#reset)|Die Implementierung der **zurück**Setzung.|
|[IEnumOnSTLImpl::Skip](#skip)|Die Implementierung von **Skip**.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|Der Iterator, der die aktuelle Position des Enumerators in der Auflistung darstellt.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Ein Zeiger auf den C++ Container der Standard Bibliothek, der die aufzuzählenden Elemente enthält.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|Der `IUnknown` Zeiger des Objekts, das die Auflistung bereitstellt.|

## <a name="remarks"></a>Hinweise

`IEnumOnSTLImpl`stellt die Implementierung für eine com-Enumeratorschnittstelle bereit, bei der die aufzuzählenden Elemente C++ in einem mit der Standard Bibliothek kompatiblen Container gespeichert werden. Diese Klasse entspricht der [CCom-umimpl](../../atl/reference/ccomenumimpl-class.md) -Klasse, die eine Implementierung für eine Enumeratorschnittstelle bereitstellt, die auf einem Array basiert.

> [!NOTE]
>  Weitere Informationen zu weiteren Unterschieden zwischen `CComEnumImpl` und `IEnumOnSTLImpl`finden Sie unter [ccomsumimpl:: init](../../atl/reference/ccomenumimpl-class.md#init) .

In der Regel müssen Sie *keine* eigene Enumeratorklasse erstellen, indem Sie von dieser Schnittstellen Implementierung ableiten. Wenn Sie einen von ATL bereitgestellten Enumerator verwenden möchten, der auf C++ einem Standard Bibliothek Container basiert, ist es häufiger, eine Instanz von [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)zu erstellen oder eine Auflistungs Klasse zu erstellen, die einen Enumerator durch Ableiten von [ICollectionOnSTLImpl zurückgibt. ](../../atl/reference/icollectiononstlimpl-class.md).

Wenn Sie jedoch einen benutzerdefinierten Enumerator angeben müssen (z. b. einen, der Schnittstellen zusätzlich zur Enumeratorschnittstelle verfügbar macht), können Sie von dieser Klasse ableiten. In dieser Situation ist es wahrscheinlich, dass Sie die [Klon](#clone) Methode überschreiben müssen, um eine eigene Implementierung bereitzustellen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="init"></a>IEnumOnSTLImpl:: init

Initialisiert den Enumerator.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>Parameter

*pUnkForRelease*<br/>
in Der `IUnknown` Zeiger eines Objekts, das während der Lebensdauer des Enumerators aufrechterhalten werden muss. Übergeben Sie NULL, wenn kein solches Objekt vorhanden ist.

*Auflistung*<br/>
Ein Verweis auf den C++ Container der Standard Bibliothek, der die aufzuzählenden Elemente enthält.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Wenn Sie einen `Init` Verweis an eine Auflistung übergeben, die in einem anderen Objekt enthalten ist, können Sie mit dem Parameter " *pUnkForRelease* " sicherstellen, dass das Objekt und die Auflistung, die es enthält, so lange verfügbar sind, wie der Enumerator es benötigt.

Sie müssen diese Methode vor dem Übergeben eines Zeigers an die Enumeratorschnittstelle zurück an alle Clients ausführen.

##  <a name="clone"></a>IEnumOnSTLImpl:: Clone

Diese Methode bietet die Implementierung der **Klon** Methode, indem ein Objekt vom Typ `CComEnumOnSTL`erstellt wird, das mit der gleichen Auflistung und dem gleichen Iterator initialisiert wird, die vom aktuellen-Objekt verwendet werden, und die-Schnittstelle für das neu erstellte-Objekt zurückgegeben wird.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Parameter

*ppEnum*<br/>
vorgenommen Die Enumeratorschnittstelle für ein neu erstelltes Objekt, das vom aktuellen Enumerator geklont wurde.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="m_spunk"></a>IEnumOnSTLImpl:: m_spUnk

Der `IUnknown` Zeiger des Objekts, das die Auflistung bereitstellt.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>Hinweise

Dieser intelligente Zeiger behält einen Verweis auf das an [IEnumOnSTLImpl:: init](#init)übergebenen Objekt bei und stellt sicher, dass es während der Lebensdauer des Enumerators aktiv bleibt.

##  <a name="m_pcollection"></a>IEnumOnSTLImpl:: m_pcollection

Dieser Member verweist auf die Auflistung, die die Daten bereitstellt, die die Implementierung der Enumeratorschnittstelle antreiben.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>Hinweise

Dieser Member wird durch einen [IEnumOnSTLImpl:: init](#init)-Rückruf initialisiert.

##  <a name="m_iter"></a>IEnumOnSTLImpl:: m_iter

Dieser Member enthält den Iterator, der verwendet wird, um die aktuelle Position in der Auflistung zu markieren und zu nachfolgenden Elementen zu navigieren.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>IEnumOnSTLImpl:: Next

Diese Methode bietet die Implementierung der **nächsten** Methode.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>Parameter

*celt*<br/>
in Die Anzahl der angeforderten Elemente.

*rgelt*<br/>
vorgenommen Das Array, das mit den Elementen aufgefüllt werden soll.

*pceltFetched*<br/>
vorgenommen Die Anzahl der Elemente, die tatsächlich in *rgelt*zurückgegeben werden. Dies kann kleiner als der *celt* sein, wenn weniger als *celt* -Elemente in der Liste verbleiben.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="reset"></a>IEnumOnSTLImpl:: Reset

Diese Methode stellt die Implementierung der **Reset** -Methode bereit.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="skip"></a>IEnumOnSTLImpl:: Skip

Diese Methode stellt die Implementierung der **Skip** -Methode bereit.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Parameter

*celt*<br/>
in Die Anzahl der zu über springenden Elemente.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
