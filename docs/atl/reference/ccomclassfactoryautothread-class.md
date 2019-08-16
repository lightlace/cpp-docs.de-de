---
title: Ccomclassfactoryautothread-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: 73879a73a48290e19d2a27307884953129826df7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497491"
---
# <a name="ccomclassfactoryautothread-class"></a>Ccomclassfactoryautothread-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle und ermöglicht das Erstellen von Objekten in mehreren Apartments.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|

## <a name="remarks"></a>Hinweise

`CComClassFactoryAutoThread`ähnelt [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ermöglicht aber das Erstellen von Objekten in mehreren Apartments. Um diese Unterstützung zu nutzen, leiten Sie das exe-Modul von [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)ab.

ATL-Objekte erhalten normalerweise eine Klassenfactory durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), das [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standardklassenfactory deklariert. Um zu `CComClassFactoryAutoThread`verwenden, geben Sie das [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) -Makro in der Klassendefinition Ihres Objekts an. Beispiel:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="createinstance"></a>Ccomclassfactoriyautothread:: forateinstance

Erstellt ein Objekt der angegebenen CLSID und Ruft einen Schnittstellen Zeiger auf dieses Objekt ab.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

### <a name="remarks"></a>Hinweise

Wenn das Modul von [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)abgeleitet ist `CreateInstance` , wählt zuerst einen Thread aus, um das Objekt im zugeordneten Apartment zu erstellen.

##  <a name="lockserver"></a>Ccomclassfactoriyautothread:: LockServer

Inkrementen und Dekrement der Modul Sperr Anzahl durch `_Module::Lock` aufrufen `_Module::Unlock`von bzw.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Parameter

*fLock*<br/>
in TRUE gibt an, dass die Sperrenanzahl inkrementiert wird. Andernfalls wird die Sperrenanzahl dekrementiert.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Wenn verwendet `CComClassFactoryAutoThread`wird `_Module` , verweist in der Regel auf die globale Instanz von [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Das `LockServer` Aufrufen von ermöglicht es einem Client, eine Klassenfactory anzuhalten, sodass mehrere Objekte schnell erstellt werden können.

## <a name="see-also"></a>Siehe auch

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
