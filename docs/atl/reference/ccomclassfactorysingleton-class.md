---
title: CComClassFactorySingleton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 55d8fb96dfce1b278763cc348c605f8e76b5f56f
ms.lasthandoff: 03/31/2017

---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton-Klasse
Diese Klasse leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) So erstellen Sie ein einzelnes Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse.  
  
 `CComClassFactorySingleton`leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und verwendet [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) So erstellen Sie ein einzelnes Objekt. Bei jedem Aufruf der `CreateInstance` Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Abfragen `m_spObj` für einen Schnittstellenzeiger auf.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|Die [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt erstellt, indem `CComClassFactorySingleton`.|  
  
## <a name="remarks"></a>Hinweise  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, `CComClassFactory` als der standardfactory-Klasse. Mit `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM #10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactorySingleton::CreateInstance  
 Aufrufe `QueryInterface` über [M_spObj](#m_spobj) um einen Schnittstellenzeiger abzurufen.  
  
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
  
##  <a name="m_spobj"></a>CComClassFactorySingleton::m_spObj  
 Die [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt erstellt, indem `CComClassFactorySingleton`.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>Hinweise  
 Bei jedem Aufruf der [CreateInstance](#createinstance) Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
 Beachten Sie, dass das aktuelle Formular des `m_spObj` stellt eine wichtige Änderung gegenüber, `CComClassFactorySingleton` arbeitet in früheren Versionen von ATL In früheren Versionen der `CComClassFactorySingleton` Objekt gleichzeitig als Klassenfactory, bei der Initialisierung des erstellt wurde. In Visual C++ .NET 2003 wird das Objekt verzögert, bei der ersten Anforderung erstellt. Diese Änderung kann in Programmen, die früh während der Initialisierung beruhen, Fehler verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

