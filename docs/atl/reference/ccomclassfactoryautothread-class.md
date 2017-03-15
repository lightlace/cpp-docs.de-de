---
title: Klasse CComClassFactoryAutoThread | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComClassFactoryAutoThread
- ATL.CComClassFactoryAutoThread
- CComClassFactoryAutoThread
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: fcc5671fc136b061bf3e8109999ac91d302d3d3b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread-Klasse
Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle und ermöglicht es Objekten, die in mehreren Apartments erstellt werden.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
  
## <a name="remarks"></a>Hinweise  
 `CComClassFactoryAutoThread`ähnelt dem [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), aber ermöglicht es Objekten, die in mehreren Apartments erstellt werden. Um diese Unterstützung nutzen zu können, leiten Sie die EXE-Moduls aus [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), die deklariert wird, [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als die standardmäßige Klassenfactory. Mit `CComClassFactoryAutoThread`, geben Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namecreateinstancea--ccomclassfactoryautothreadcreateinstance"></a><a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 Erstellt ein Objekt der angegebenen CLSID und ruft einen Schnittstellenzeiger für dieses Objekt ab.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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
 Wenn Ihr Modul abgeleitet [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` zuerst wählt einen Thread zum Erstellen des Objekts im zugehörigen Apartment.  
  
##  <a name="a-namelockservera--ccomclassfactoryautothreadlockserver"></a><a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 Inkrementiert und dekrementiert die Sperrenanzahl Modul durch Aufrufen von **_Module::Lock** und **_Module::Unlock**bzw..  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>Parameter  
 `fLock`  
 [in] Wenn **TRUE**, die Anzahl der Sperren erhöht, andernfalls die Anzahl der Sperren wird verringert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung `CComClassFactoryAutoThread`, **_Module** bezieht sich normalerweise auf die globale Instanz des [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Aufrufen von `LockServer` ermöglicht einem Client auf eine halten, damit mehrere Objekte können schnell erstellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton-Klasse](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

