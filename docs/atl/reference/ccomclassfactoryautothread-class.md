---
title: CComClassFactoryAutoThread-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 476edd2a199ca21a9067a72cac82a6ac7b608112
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757377"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread-Klasse

Diese Klasse implementiert die [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) Schnittstelle und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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

`CComClassFactoryAutoThread` ist vergleichbar mit [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), sondern ermöglicht es Objekten, die in mehreren Apartments erstellt werden. Um diese Unterstützung nutzen zu können, leiten Sie Ihre EXE-Modul aus [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Verwendung von `CComClassFactoryAutoThread`, geben Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance

Erstellt ein Objekt der angegebenen CLSID und einen Schnittstellenzeiger für dieses Objekt abgerufen.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parameter

*pUnkOuter*  
[in] Wenn das Objekt dann als Teil eines Aggregats erstellt wird *pUnkOuter* muss die äußere unbekannte sein. Andernfalls *pUnkOuter* muss NULL sein.

*riid*  
[in] Die IID der angeforderten Schnittstelle. Wenn *pUnkOuter* ungleich NULL, *Riid* muss `IID_IUnknown`.

*ppvObj*  
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObj* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn Ihr Modul abgeleitet [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` zuerst wählt einen Thread zum Erstellen des Objekts im zugeordneten Apartment.

##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer

Erhöht und verringert die Sperrenanzahl Modul durch Aufrufen von `_Module::Lock` und `_Module::Unlock`bzw.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Parameter

*Bestand*  
[in] True gibt an, die Anzahl der Sperren erhöht. Andernfalls ist die Anzahl der Sperren verringert.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Bei Verwendung `CComClassFactoryAutoThread`, `_Module` bezieht sich normalerweise auf die globale Instanz des [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Aufrufen von `LockServer` kann ein Client eine Klassenfactory enthalten, damit mehrere Objekte können schnell erstellt werden.

## <a name="see-also"></a>Siehe auch

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)   
[CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)   
[CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)   
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
