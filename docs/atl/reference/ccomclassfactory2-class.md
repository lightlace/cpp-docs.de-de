---
title: Klasse CComClassFactory2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComClassFactory2<license>
- CComClassFactory2
- ATL.CComClassFactory2<license>
- ATL::CComClassFactory2
- ATL.CComClassFactory2
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3787214d5479e1cd57295c9c25335e87651a16bb
ms.lasthandoff: 02/24/2017

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
  
- **statische BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **);**  
  
- **statische BOOL IsLicenseValid ();**  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Erstellt ein Objekt mit der angegebenen CLSID einen Lizenzschlüssel.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Ruft Informationen für die Lizenzierung Funktionen der Klassenfactory ab.|  
|[CComClassFactory2::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Erstellt und gibt einen Lizenzschlüssel.|  
  
## <a name="remarks"></a>Hinweise  
 `CComClassFactory2`implementiert die [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) -Schnittstelle, die eine Erweiterung der [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** Steuerelemente-Objekt erstellen, die über eine Lizenz. Eine Klasse Factory ausgeführt auf einem lizenzierten Computer kann zur Laufzeit Lizenzschlüssel bereitstellen. Dieser Lizenzschlüssel kann eine Anwendung Objekte zu instanziieren, wenn eine vollständige Computer Lizenz nicht vorhanden ist.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Mit `CComClassFactory2`, geben Sie die [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, der Vorlagenparameter `CComClassFactory2`, müssen die statischen Funktionen implementieren `VerifyLicenseKey`, `GetLicenseKey`, und `IsLicenseValid`. Im folgenden finden ein Beispiel für eine einfache Lizenzklasse:  
  
 [!code-cpp[NVC_ATL_COM&3;](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`Beide abgeleitet **CComClassFactory2Base** und *Lizenz*. **CComClassFactory2Base**, leitet sich wiederum aus **IClassFactory2** und **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namecreateinstancea--ccomclassfactory2createinstance"></a><a name="createinstance"></a>CComClassFactory2::CreateInstance  
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
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObj` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Erfordert, dass der Computer vollständig lizenziert werden. Wenn eine vollständige Computer Lizenz nicht vorhanden ist, rufen Sie [CreateInstanceLic](#createinstancelic).  
  
##  <a name="a-namecreateinstancelica--ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic  
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
 [in] Die Laufzeit-Lizenzschlüssel zuvor abgerufen haben, durch einen Aufruf von `RequestLicKey`. Dieser Schlüssel ist erforderlich, um das Objekt zu erstellen.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch angegebenen `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObject` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Sie erhalten eine Lizenz mit [RequestLicKey](#requestlickey). Um ein Objekt auf ein nicht lizenzierter Computer zu erstellen, müssen Sie aufrufen `CreateInstanceLic`.  
  
##  <a name="a-namegetlicinfoa--ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a>CComClassFactory2::GetLicInfo  
 Füllt ein [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) Struktur mit Informationen über die Klassenfactory der Lizenzierung Funktionen.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Parameter  
 *pLicInfo*  
 [out] Zeiger auf eine **LICINFO** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der `fRuntimeKeyAvail` Member dieser Struktur gibt an, ob, wenn Sie einen Lizenzschlüssel, die Klassenfactory Objekte auf ein nicht lizenzierter Computer erstellt werden. Die *fLicVerified* Element gibt an, ob eine vollständige Computer Lizenz vorhanden ist.  
  
##  <a name="a-namelockservera--ccomclassfactory2lockserver"></a><a name="lockserver"></a>CComClassFactory2::LockServer  
 Inkrementiert und dekrementiert die Sperrenanzahl Modul durch Aufrufen von **_Module::Lock** und **_Module::Unlock**bzw..  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Parameter  
 `fLock`  
 [in] Wenn **TRUE**, die Anzahl der Sperren erhöht, andernfalls die Anzahl der Sperren wird verringert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **_Module** bezieht sich auf die globale Instanz des [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
 Aufrufen von `LockServer` ermöglicht einem Client auf eine halten, damit mehrere Objekte können schnell erstellt werden.  
  
##  <a name="a-namerequestlickeya--ccomclassfactory2requestlickey"></a><a name="requestlickey"></a>CComClassFactory2::RequestLicKey  
 Erstellt und gibt einen Lizenzschlüssel bereitgestellt, die die `fRuntimeKeyAvail` Mitglied der [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) -Struktur ist **TRUE**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 [in] Nicht verwendet. Muss Null sein.  
  
 `pbstrKey`  
 [out] Ein Zeiger auf den Lizenzschlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Lizenzschlüssel ist erforderlich für den Aufruf von [CreateInstanceLic](#createinstancelic) zum Erstellen eines Objekts auf ein nicht lizenzierter Computer. Wenn `fRuntimeKeyAvail` ist **FALSE**, und klicken Sie dann die Objekte nur auf eine vollständig lizenzierte Computer erstellt werden können.  
  
 Rufen Sie [GetLicInfo](#getlicinfo) zum Abrufen des Werts von `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>Siehe auch  
 [CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

