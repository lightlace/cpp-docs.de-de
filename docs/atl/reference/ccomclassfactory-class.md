---
title: CComClassFactory Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComClassFactory
- CComClassFactory
- ATL::CComClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7c488732d7b32248acaaa5c5c9c6a29404c3872
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory-class"></a>CComClassFactory-Klasse
Diese Klasse implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|Erstellt ein Objekt der angegebenen CLSID.|  
|[CComClassFactory::LockServer](#lockserver)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
  
## <a name="remarks"></a>Hinweise  
 `CComClassFactory`implementiert die [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) -Schnittstelle, die Methoden für das Erstellen eines Objekts einer bestimmten CLSID sowie das Sperren der Klassenfactory im Arbeitsspeicher, um neue Objekte schneller erstellt werden können. **IClassFactory** für jede Klasse, die Sie in der Registrierung und die CLSID zuweisen registrieren implementiert werden muss.  
  
 ATL-Objekte abrufen eine Klassenfactory normalerweise durch Ableiten von [CComCoClass](../../atl/reference/ccomcoclass-class.md). Diese Klasse enthält das Makro [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), die deklariert wird, `CComClassFactory` als die standardmäßige Klassenfactory. Um diese Standardeinstellung zu überschreiben, geben Sie einen von der `DECLARE_CLASSFACTORY` *XXX* Makros in die Klassendefinition. Zum Beispiel die [DECLARE_CLASSFACTORY_EX](http://msdn.microsoft.com/library/4181ef00-0f30-4e19-b0ee-e7648062e926) Makro verwendet die angegebene Klasse für die Klassenfactory:  
  
 [!code-cpp[NVC_ATL_COM&#8;](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 Die oben genannten Klassendefinition gibt an, dass **CMyClassFactory** als Standard-Klassenfactory des Objekts verwendet wird. **CMyClassFactory** durch Ableiten von `CComClassFactory` , und überschreiben Sie `CreateInstance`.  
  
 ATL stellt drei Makros, die eine Klassenfactory deklarieren:  
  
- [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), welche Steuerelemente erstellen, die über eine Lizenz.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), die Objekte in mehreren Apartments erstellt.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), die ein einzelnes erstellt [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namecreateinstancea--ccomclassfactorycreateinstance"></a><a name="createinstance"></a>CComClassFactory::CreateInstance  
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
  
##  <a name="a-namelockservera--ccomclassfactorylockserver"></a><a name="lockserver"></a>CComClassFactory::LockServer  
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
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

