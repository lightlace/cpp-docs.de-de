---
title: CComClassFactory-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 85ef287a905abc7b3151628c0f5dc29b9050b187
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246721"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle.

## <a name="syntax"></a>Syntax

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactory::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|
|[CComClassFactory::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|

## <a name="remarks"></a>Hinweise

`CComClassFactory` implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle, die Methoden zum Erstellen eines Objekts von einer bestimmten CLSID als auch die Klassenfactory im Arbeitsspeicher, um neue Objekte schneller erstellt werden können Sperren enthält. `IClassFactory` muss für jede Klasse implementiert werden, die Sie in der Registrierung und Zuweisen von dem Sie eine CLSID registrieren.

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, `CComClassFactory` als der Standardklassenfactory. Um diese Standardeinstellung zu überschreiben, geben Sie eine der der `DECLARE_CLASSFACTORY` *XXX* Makros in der Klassendefinition. Z. B. die [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) Makro verwendet die angegebene Klasse für die Klassenfactory:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Die oben genannten Klassendefinition gibt an, dass `CMyClassFactory` als Standardklassenfactory des Objekts verwendet wird. `CMyClassFactory` muss abgeleitet `CComClassFactory` und überschreiben `CreateInstance`.

ATL stellt drei andere Makros, die eine Klassenfactory zu deklarieren:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), welche Steuerelemente erstellen, die über eine Lizenz.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), die Objekte in mehreren Apartments erstellt.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), die eine einzelne erstellt [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory::CreateInstance

Erstellt ein Objekt der angegebenen CLSID und einen Schnittstellenzeiger für dieses Objekt abgerufen.

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

##  <a name="lockserver"></a>  CComClassFactory::LockServer

Erhöht und verringert die Sperrenanzahl Modul durch Aufrufen von `_Module::Lock` und `_Module::Unlock`bzw.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parameter

*fLock*<br/>
[in] True gibt an, die Anzahl der Sperren erhöht. Andernfalls ist die Anzahl der Sperren verringert.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

`_Module` bezieht sich auf die globale Instanz des [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet wird.

Aufrufen von `LockServer` kann ein Client eine Klassenfactory enthalten, damit mehrere Objekte können schnell erstellt werden.

## <a name="see-also"></a>Siehe auch

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
