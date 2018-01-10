---
title: CComClassFactory Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs: C++
helpviewer_keywords: CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2af57c666cf2ee452d2707045d259ada695a2848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomclassfactory-class"></a>CComClassFactory-Klasse
Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle.  
  
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
 `CComClassFactory`implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) -Schnittstelle, die enthält Methoden zum Erstellen eines Objekts von einem bestimmten CLSID sowie das Sperren der Klassenfactory im Arbeitsspeicher, damit neue Objekte schneller erstellt werden können. **IClassFactory** muss für jede Klasse, die Sie in der Registrierung und Zuweisen von dem Sie CLSID registrieren implementiert werden.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), die deklariert wird, `CComClassFactory` als der standardfactory-Klasse. Um diese Standardeinstellung zu überschreiben, geben Sie einen von der `DECLARE_CLASSFACTORY` *XXX* Makros in der Klasse. Z. B. die [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) Makro verwendet die angegebene Klasse für die Klassenfactory:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 Die oben genannten Klassendefinition gibt an, dass **CMyClassFactory** als Klassenfactory für das Objekt standardmäßig verwendet wird. **CMyClassFactory** leiten von `CComClassFactory` und überschreiben `CreateInstance`.  
  
 ATL stellt drei Makros, die eine Klassenfactory deklarieren:  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), welche Steuerelemente erstellen, die über eine Lizenz.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), die Objekte in mehreren Apartments erstellt.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), die ein einzelnes erstellt [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory::CreateInstance  
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
  
##  <a name="lockserver"></a>CComClassFactory::LockServer  
 Erhöht und verringert die Sperrenanzahl Modul durch Aufrufen von **_Module::Lock** und **_Module::Unlock**zugeordnet.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Parameter  
 `fLock`  
 [in] Wenn **"true"**die Anzahl der Sperren andernfalls erhöht, wird die Anzahl der Sperren wird verringert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 **_Module** bezieht sich auf die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
 Aufrufen von `LockServer` ermöglicht einem Client zu einer Klassenfactory festzuhalten, sodass mehrere Objekte schnell erstellt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
