---
title: CComClassFactory2-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: b3b14fa59765aa72a1142e0eef41aa84abea35de
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301848"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2-Klasse

Diese Klasse implementiert die [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) Schnittstelle.

## <a name="syntax"></a>Syntax

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parameter

*license*<br/>
Eine Klasse, die folgenden statischen Funktionen implementiert:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactory2::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Ein Lizenzschlüssel erstellt ein Objekt der angegebenen CLSID.|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Ruft die Informationen, die die Lizenzierung Funktionen des die Klassenfactory beschreiben.|
|[CComClassFactory2::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|
|[CComClassFactory2::RequestLicKey](#requestlickey)|Erstellt und gibt einen Lizenzschlüssel.|

## <a name="remarks"></a>Hinweise

`CComClassFactory2` implementiert die [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) -Schnittstelle, die eine Erweiterung der [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` Steuerelemente Objekt-und Arrayerstellung über eine Lizenz. Eine Klasse Factory ausführen auf einem lizenzierten Computer kann einen Laufzeit-Lizenzschlüssel bereitstellen. Diesen Lizenzschlüssel kann es sich um eine Anwendung, um Objekte zu instanziieren, wenn eine Lizenz des gesamten Computers nicht vorhanden ist.

ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der Standardklassenfactory. Verwendung von `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Makro in der Definition der Klasse des Objekts. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, der Vorlagenparameter `CComClassFactory2`, müssen die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel für eine einfache Lizenz-Klasse:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` leitet sich von sowohl `CComClassFactory2Base` und *Lizenz*. `CComClassFactory2Base`, leitet sich wiederum von `IClassFactory2` und `CComObjectRootEx< CComGlobalsThreadModel >`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance

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

### <a name="remarks"></a>Hinweise

Erfordert, dass der Computer vollständig lizenziert werden. Wenn eine Lizenz des gesamten Computers nicht vorhanden ist, rufen Sie [CreateInstanceLic](#createinstancelic).

##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic

Ähnlich wie [CreateInstance](#createinstance), außer dass `CreateInstanceLic` erfordert einen Lizenzschlüssel.

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>Parameter

*pUnkOuter*<br/>
[in] Wenn das Objekt dann als Teil eines Aggregats erstellt wird *pUnkOuter* muss die äußere unbekannte sein. Andernfalls *pUnkOuter* muss NULL sein.

*pUnkReserved*<br/>
[in] Nicht verwendet. Muss NULL sein.

*riid*<br/>
[in] Die IID der angeforderten Schnittstelle. Wenn *pUnkOuter* ungleich NULL, *Riid* muss `IID_IUnknown`.

*bstrKey*<br/>
[in] Die Laufzeit-Lizenzschlüssel zuvor abgerufen haben, von einem Aufruf von `RequestLicKey`. Dieser Schlüssel ist erforderlich, um das Objekt zu erstellen.

*ppvObject*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger, der anhand des *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Sie erhalten eine Lizenz mit [RequestLicKey](#requestlickey). Um ein Objekt auf einem nicht lizenzierter Computer zu erstellen, müssen Sie aufrufen `CreateInstanceLic`.

##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo

Füllt ein [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) Struktur mit Informationen, die die Klassenfactory beschreiben die Funktionen Lizenzierung.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parameter

*pLicInfo*<br/>
[out] Zeiger auf eine `LICINFO` Struktur.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die `fRuntimeKeyAvail` Mitglied dieser Struktur gibt an, ob erhalten einen Lizenzschlüssel, der die Klassenfactory Objekte auf einem nicht lizenzierter Computer erstellt werden kann. Die *fLicVerified* Member angibt, ob eine Lizenz des gesamten Computers vorhanden ist.

##  <a name="lockserver"></a>  CComClassFactory2::LockServer

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

##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey

Erstellt und gibt Sie einen Lizenzschlüssel, bereitgestellt, die die `fRuntimeKeyAvail` Mitglied der [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) Struktur ist "true".

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
[in] Nicht verwendet. NULL muss sein.

*pbstrKey*<br/>
[out] Zeiger auf den Lizenzschlüssel.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Ist für den Aufruf erforderlich, ein Lizenzschlüssel [CreateInstanceLic](#createinstancelic) zum Erstellen eines Objekts auf einem Computer mit nicht lizenziert. Wenn `fRuntimeKeyAvail` ist "false", und klicken Sie dann die Objekte nur auf eine vollständig lizenzierte Computer erstellt werden können.

Rufen Sie [GetLicInfo](#getlicinfo) zum Abrufen des Werts der `fRuntimeKeyAvail`.

## <a name="see-also"></a>Siehe auch

[CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
