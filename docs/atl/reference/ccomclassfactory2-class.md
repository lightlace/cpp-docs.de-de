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
ms.openlocfilehash: e34ebffc937c3e4ef1272fdf13ddcde7513d28e4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497456"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2-Klasse

Diese Klasse implementiert die [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) -Schnittstelle.

## <a name="syntax"></a>Syntax

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parameter

*Lizenz*<br/>
Eine Klasse, die die folgenden statischen Funktionen implementiert:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComClassFactory2::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Erstellt ein Objekt der angegebenen CLSID, wenn ein Lizenzschlüssel angegeben ist.|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Ruft Informationen ab, die die Lizenzierungs Funktionen der Klassenfactory beschreiben.|
|[CComClassFactory2::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|
|[CComClassFactory2::RequestLicKey](#requestlickey)|Erstellt einen Lizenzschlüssel und gibt ihn zurück.|

## <a name="remarks"></a>Hinweise

`CComClassFactory2`implementiert die [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) -Schnittstelle, die eine Erweiterung von [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)ist. `IClassFactory2`steuert die Objekt Erstellung über eine Lizenz. Eine Klassenfactory, die auf einem lizenzierten Computer ausgeführt wird, kann einen Laufzeitlizenz Schlüssel bereitstellen. Dieser Lizenzschlüssel ermöglicht es einer Anwendung, Objekte zu instanziieren, wenn keine vollständige Computer Lizenz vorhanden ist.

ATL-Objekte erhalten normalerweise eine Klassenfactory durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), das [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standardklassenfactory deklariert. Um zu `CComClassFactory2`verwenden, geben Sie das [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) -Makro in der Klassendefinition Ihres Objekts an. Beispiel:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, der Vorlagen Parameter für `CComClassFactory2`, muss die statischen `GetLicenseKey`Funktionen `VerifyLicenseKey`, und `IsLicenseValid`implementieren. Im folgenden finden Sie ein Beispiel für eine einfache Lizenz Klasse:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2`wird sowohl `CComClassFactory2Base` von als auch von der *Lizenz*abgeleitet. `CComClassFactory2Base`wiederum wird von `IClassFactory2` und `CComObjectRootEx< CComGlobalsThreadModel >`abgeleitet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="createinstance"></a>CComClassFactory2:: kreateingestance

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

### <a name="remarks"></a>Hinweise

Erfordert, dass der Computer vollständig lizenziert ist. Wenn keine vollständige Computer Lizenz vorhanden ist, müssen Sie " [kreateinstancelic](#createinstancelic)" aufrufen.

##  <a name="createinstancelic"></a>CComClassFactory2:: kreatinstancelic

Vergleichbar mit " [kreatanstance](#createinstance)", `CreateInstanceLic` mit dem Unterschied, dass einen Lizenzschlüssel erfordert.

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
in Wenn das Objekt als Teil eines Aggregats erstellt wird, muss es sich bei *pUnkOuter* um das äußere unbekannte Element handeln. Andernfalls muss " *pUnkOuter* " NULL sein.

*pUnkReserved*<br/>
in Nicht verwendet. Muss NULL sein.

*riid*<br/>
in Die IID der angeforderten Schnittstelle. Wenn ' *pUnkOuter* ' nicht NULL ist, muss ' *riid* ' lauten `IID_IUnknown`.

*bstrKey*<br/>
in Der Laufzeitlizenz Schlüssel, der zuvor durch einen Aufruf `RequestLicKey`von abgerufen wurde. Dieser Schlüssel ist erforderlich, um das Objekt zu erstellen.

*ppvObject*<br/>
vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der durch *riid*angegeben wird. Wenn das Objekt diese Schnittstelle nicht unterstützt, wird *ppvobject* auf NULL festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Sie können einen Lizenzschlüssel mithilfe von [RequestLicKey](#requestlickey)abrufen. Zum Erstellen eines Objekts auf einem nicht lizenzierten Computer muss aufgerufen `CreateInstanceLic`werden.

##  <a name="getlicinfo"></a>CComClassFactory2:: GetLicInfo

Füllt eine [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) -Struktur mit Informationen, die die Lizenzierungs Funktionen der Klassen-Factory beschreiben.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parameter

*pLicInfo*<br/>
vorgenommen Zeiger auf eine `LICINFO` -Struktur.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Der `fRuntimeKeyAvail` Member dieser Struktur gibt an, ob die Klassenfactory bei Angabe eines Lizenzschlüssels zulässt, dass Objekte auf einem nicht lizenzierten Computer erstellt werden. Der *flicverified* -Member gibt an, ob eine vollständige Computer Lizenz vorhanden ist.

##  <a name="lockserver"></a>CComClassFactory2:: LockServer

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

##  <a name="requestlickey"></a>CComClassFactory2:: RequestLicKey

Erstellt einen Lizenzschlüssel und gibt ihn zurück, voraus `fRuntimeKeyAvail` gesetzt, dass der Member der [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) -Struktur "true" ist.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
in Nicht verwendet. Muss 0 (null) sein.

*pbstrKey*<br/>
vorgenommen Zeiger auf den Lizenzschlüssel.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Zum Erstellen eines Objekts auf einem nicht lizenzierten Computer ist ein Lizenzschlüssel zum Aufrufen von [CreateInstanceLic](#createinstancelic) erforderlich. Wenn `fRuntimeKeyAvail` false ist, können Objekte nur auf einem vollständig lizenzierten Computer erstellt werden.

Rufen Sie [GetLicInfo](#getlicinfo) auf, um den `fRuntimeKeyAvail`Wert von abzurufen.

## <a name="see-also"></a>Siehe auch

[CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
