---
title: Klasse CComClassFactorySingleton | Microsoft-Dokumentation
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 7ff6f3a9d00c0f579077d9502aefad5cbea35f17
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton-Klasse
Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) ein einzelnes Objekt zu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse.  
  
 `CComClassFactorySingleton`leitet sich von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) ein einzelnes Objekt zu erstellen. Jeder Aufruf von der `CreateInstance` -Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
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
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), die deklariert wird, `CComClassFactory` als die standardmäßige Klassenfactory. Mit `CComClassFactorySingleton`, geben Sie die [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478) Makro in die Definition der Klasse des Objekts. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
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
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObj` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="m_spobj"></a>CComClassFactorySingleton::m_spObj  
 Die [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt erstellt, indem `CComClassFactorySingleton`.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>Hinweise  
 Jeder Aufruf von der [CreateInstance](#createinstance) -Methode fragt einfach dieses Objekts für einen Schnittstellenzeiger auf.  
  
 Beachten Sie, dass das aktuelle Formular des `m_spObj` stellt eine wichtige Änderung gegenüber, `CComClassFactorySingleton` war in früheren Versionen von ATL In früheren Versionen der `CComClassFactorySingleton` Objekt gleichzeitig als ClassFactory, während der Initialisierung erstellt wurde. In Visual C++ .NET 2003 wird das Objekt verzögert, bei der ersten Anforderung erstellt. Diese Änderung kann in Programmen, die frühe Initialisierung verwenden, Fehler verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2-Klasse](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread-Klasse](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

