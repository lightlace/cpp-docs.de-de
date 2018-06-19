---
title: CComClassFactory2 Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da2b47290d3d0be525ca65b16733c9f42835d24e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363515"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2-Klasse
Diese Klasse implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>Parameter  
 *Lizenz*  
 Eine Klasse, die folgenden statischen Funktionen implementiert:  
  
- **statische BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **statische BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **statische IsLicenseValid BOOL ();**  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Ein Lizenzschlüssel erstellt ein Objekt der angegebenen CLSID.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Ruft Informationen beschreiben die Lizenzierung Funktionen der Klassenfactory ab.|  
|[CComClassFactory2::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Erstellt und gibt einen Lizenzschlüssel.|  
  
## <a name="remarks"></a>Hinweise  
 `CComClassFactory2` implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) -Schnittstelle, die eine Erweiterung der [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** Steuerelemente Objekt erstellen, die über eine Lizenz. Eine Klasse Factory ausführen auf eine lizenzierte Computer kann einen Laufzeit-Lizenzschlüssel bereitstellen. Diese Lizenzschlüssel ermöglicht eine Anwendung, um Objekte zu instanziieren, wenn eine Lizenz für die vollständige Computer nicht vorhanden ist.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als der standardfactory-Klasse. Mit `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, der Vorlagenparameter `CComClassFactory2`, muss die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel einer einfachen Lizenz-Klasse:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` leitet sich von sowohl **CComClassFactory2Base** und *Lizenz*. **CComClassFactory2Base**, leitet sich wiederum von **IClassFactory2** und **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance  
 Erstellt ein Objekt der angegebenen CLSID und ruft einen Schnittstellenzeiger für dieses Objekt ab.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Parameter  
 `pUnkOuter`  
 [in] Wenn das Objekt als Teil einer Aggregatfunktion gehört, dann erstellt wird `pUnkOuter` muss die äußere unbekannte sein. Andernfalls `pUnkOuter` muss **NULL**.  
  
 `riid`  
 [in] Die IID der angeforderten Schnittstelle. Wenn `pUnkOuter` nicht **NULL**, `riid` muss **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObj` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Erfordert, dass der Computer vollständig lizenziert werden. Wenn eine Lizenz für die vollständige Computer nicht vorhanden ist, rufen Sie [CreateInstanceLic](#createinstancelic).  
  
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
 `pUnkOuter`  
 [in] Wenn das Objekt als Teil einer Aggregatfunktion gehört, dann erstellt wird `pUnkOuter` muss die äußere unbekannte sein. Andernfalls `pUnkOuter` muss **NULL**.  
  
 *pUnkReserved*  
 [in] Nicht verwendet. Muss **NULL**.  
  
 `riid`  
 [in] Die IID der angeforderten Schnittstelle. Wenn `pUnkOuter` nicht **NULL**, `riid` muss **IID_IUnknown**.  
  
 `bstrKey`  
 [in] Der Laufzeit-Lizenzschlüssel wird bereits von einem Aufruf abgerufen `RequestLicKey`. Dieser Schlüssel ist erforderlich, um das Objekt zu erstellen.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der gemäß `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObject` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sie erhalten einen Lizenz mit [RequestLicKey](#requestlickey). Um ein Objekt auf eine nicht lizenzierte Computer zu erstellen, rufen Sie `CreateInstanceLic`.  
  
##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo  
 Füllt eine [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) Struktur mit Informationen, die die Klassenfactory beschreiben die Funktionen Lizenzierung.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pLicInfo*  
 [out] Zeiger auf eine **LICINFO** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die `fRuntimeKeyAvail` Mitglied dieser Struktur überprüfen, ob, erhält einen Lizenzschlüssel, die Klassenfactory Objekte auf eine nicht lizenzierte Computer erstellt werden kann. Die *fLicVerified* Element gibt an, ob eine vollständige Computer Lizenz vorhanden ist.  
  
##  <a name="lockserver"></a>  CComClassFactory2::LockServer  
 Erhöht und verringert die Sperrenanzahl Modul durch Aufrufen von **_Module::Lock** und **_Module::Unlock**zugeordnet.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Parameter  
 `fLock`  
 [in] Wenn **"true"** die Anzahl der Sperren andernfalls erhöht, wird die Anzahl der Sperren wird verringert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **_Module** bezieht sich auf die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
 Aufrufen von `LockServer` ermöglicht einem Client zu einer Klassenfactory festzuhalten, sodass mehrere Objekte schnell erstellt werden können.  
  
##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey  
 Erstellt und gibt einen Lizenzschlüssel bereitgestellt, die die `fRuntimeKeyAvail` Mitglied der [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) Struktur ist **"true"**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 [in] Nicht verwendet. NULL muss sein.  
  
 `pbstrKey`  
 [out] Ein Zeiger auf den Lizenzschlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Ein Lizenzschlüssel ist erforderlich für den Aufruf von [CreateInstanceLic](#createinstancelic) zum Erstellen eines Objekts auf einem Computer mit nicht lizenziert. Wenn `fRuntimeKeyAvail` ist **"false"**, und klicken Sie dann die Objekte nur auf eine vollständig lizenzierte Computer erstellt werden können.  
  
 Rufen Sie [GetLicInfo](#getlicinfo) zum Abrufen des Werts der `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
