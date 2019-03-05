---
title: CComClassFactorySingleton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 480b4c2a6e052e8e0823b97b548fc5d07b55230f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290390"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton-Klasse

Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) um ein einzelnes Objekt zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse.

`CComClassFactorySingleton` leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) um ein einzelnes Objekt zu erstellen. Jeder Aufruf der `CreateInstance` -Methode fragt einfach dieses Objekt für einen Schnittstellenzeiger auf.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Abfragen `m_spObj` für einen Schnittstellenzeiger auf.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|Die [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt erstellt, indem `CComClassFactorySingleton`.|

## <a name="remarks"></a>Hinweise

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, `CComClassFactory` als der Standardklassenfactory. Verwendung von `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance

Aufrufe `QueryInterface` über [M_spObj](#m_spobj) um einen Schnittstellenzeiger abzurufen.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parameter

*pUnkOuter*<br/>
[in] Wenn das Objekt dann als Teil eines Aggregats erstellt wird *pUnkOuter* muss die äußere unbekannte sein. Andernfalls *pUnkOuter* muss NULL sein.

*riid*<br/>
[in] Die IID der angeforderten Schnittstelle. Wenn *pUnkOuter* ungleich NULL, *Riid* muss `IID_IUnknown`.

*ppvObj*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObj* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj

Die [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt erstellt, indem `CComClassFactorySingleton`.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Hinweise

Jeder Aufruf der [CreateInstance](#createinstance) -Methode fragt einfach dieses Objekt für einen Schnittstellenzeiger auf.

Beachten Sie, dass das aktuelle Formular des `m_spObj` stellt eine bedeutende Änderung verglichen mit der Möglichkeit, `CComClassFactorySingleton` war in früheren Versionen von ATL In früheren Versionen der `CComClassFactorySingleton` Objekt zur gleichen Zeit wie die Klassenfactory, während der Initialisierung erstellt wurde. In Visual C++ .NET 2003 wird das Objekt verzögert, bei der ersten Anforderung erstellt. Diese Änderung kann in Programmen, die frühe Initialisierung abhängen, Fehler verursachen.

## <a name="see-also"></a>Siehe auch

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
