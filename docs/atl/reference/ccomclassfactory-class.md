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
ms.openlocfilehash: 892153e47ac4e9dd45d5dfc01b76f1ce29d23938
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497451"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle.

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

`CComClassFactory`implementiert die [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) -Schnittstelle, die Methoden zum Erstellen eines Objekts einer bestimmten CLSID enthält, sowie zum Sperren der Klassenfactory im Speicher, sodass neue Objekte schneller erstellt werden können. `IClassFactory`muss für jede Klasse implementiert werden, die Sie in der Systemregistrierung registrieren und denen Sie eine CLSID zuweisen.

ATL-Objekte erhalten normalerweise eine Klassenfactory durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), das als `CComClassFactory` Standardklassenfactory deklariert. Um diese Standardeinstellung zu überschreiben, geben `DECLARE_CLASSFACTORY`Sie eines der *xxx* -Makros in der Klassendefinition an. Beispielsweise verwendet das [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) -Makro die angegebene Klasse für die Klassenfactory:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Die obige Klassendefinition gibt an `CMyClassFactory` , dass als Standardklassenfactory des Objekts verwendet wird. `CMyClassFactory`muss von `CComClassFactory` abgeleitet und über `CreateInstance`schrieben werden.

ATL bietet drei weitere Makros, die eine Klassenfactory deklarieren:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), das die Erstellung über eine Lizenz steuert.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Verwendet [ccomclassfactor yautothread](../../atl/reference/ccomclassfactoryautothread-class.md), mit dem Objekte in mehreren Apartments erstellt werden.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Verwendet [ccomclassfactorysingleton](../../atl/reference/ccomclassfactorysingleton-class.md), das ein einzelnes [ccomobjectglobal](../../atl/reference/ccomobjectglobal-class.md) -Objekt erstellt.

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="createinstance"></a>CComClassFactory:: "kreateinstance"

Erstellt ein Objekt der angegebenen CLSID und Ruft einen Schnittstellen Zeiger auf dieses Objekt ab.

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

##  <a name="lockserver"></a>CComClassFactory:: LockServer

Inkrementen und Dekrement der Modul Sperr Anzahl durch `_Module::Lock` aufrufen `_Module::Unlock`von bzw.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parameter

*fLock*<br/>
in TRUE gibt an, dass die Sperrenanzahl inkrementiert wird. Andernfalls wird die Sperrenanzahl dekrementiert.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

`_Module`verweist auf die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine von ihr abgeleitete Klasse.

Das `LockServer` Aufrufen von ermöglicht es einem Client, eine Klassenfactory anzuhalten, sodass mehrere Objekte schnell erstellt werden können.

## <a name="see-also"></a>Siehe auch

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
