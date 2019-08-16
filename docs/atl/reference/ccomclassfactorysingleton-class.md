---
title: Ccomclassfactorysingleton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 71705d02140f0392a9ce023c64e7b4125c14443f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497377"
---
# <a name="ccomclassfactorysingleton-class"></a>Ccomclassfactorysingleton-Klasse

Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) abgeleitet und verwendet [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) , um ein einzelnes Objekt zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ihre Klasse.

`CComClassFactorySingleton`wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) abgeleitet und verwendet [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) , um ein einzelnes Objekt zu erstellen. Jeder Aufrufe der `CreateInstance` -Methode fragt dieses Objekt einfach nach einem Schnittstellen Zeiger ab.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Fragt `m_spObj` nach einem Schnittstellen Zeiger ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|Das von `CComClassFactorySingleton`erstellte [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) -Objekt.|

## <a name="remarks"></a>Hinweise

ATL-Objekte erhalten normalerweise eine Klassenfactory durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), das als `CComClassFactory` Standardklassenfactory deklariert. Um zu `CComClassFactorySingleton`verwenden, geben Sie das [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) -Makro in der Klassendefinition Ihres Objekts an. Beispiel:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="createinstance"></a>Ccomclassfactoriysingleton:: "kreateinstance"

Ruft `QueryInterface` über [m_spObj](#m_spobj) auf, um einen Schnittstellen Zeiger abzurufen.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parameter

*pUnkOuter*<br/>
in Wenn das Objekt als Teil eines Aggregats erstellt wird, muss es sich bei *pUnkOuter* um das äußere unbekannte Element handeln. Andernfalls muss " *pUnkOuter* " NULL sein.

*riid*<br/>
in Die IID der angeforderten Schnittstelle. Wenn ' *pUnkOuter* ' nicht NULL ist, muss ' *riid* ' lauten `IID_IUnknown`.

*ppvObj*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *riid*identifiziert wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *ppvObj* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="m_spobj"></a>Ccomclassfactoriysingleton:: m_spObj

Das von `CComClassFactorySingleton`erstellte [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) -Objekt.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Hinweise

Bei jedem Aufrufen der Methode " [kreateinstance](#createinstance) " wird dieses Objekt einfach nach einem Schnittstellen Zeiger abgefragt.

Beachten Sie, dass die aktuelle `m_spObj` Form von eine Breaking Change von der Art `CComClassFactorySingleton` darstellt, in der in früheren Versionen von ATL gearbeitet wurde. In früheren Versionen wurde `CComClassFactorySingleton` das Objekt während der Server Initialisierung zur gleichen Zeit erstellt wie die Klassenfactory. In Visual C++.NET 2003 und höher wird das Objekt verzögert erstellt, bei der ersten Anforderung. Diese Änderung kann zu Fehlern in Programmen führen, die von der frühen Initialisierung abhängen.

## <a name="see-also"></a>Siehe auch

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
