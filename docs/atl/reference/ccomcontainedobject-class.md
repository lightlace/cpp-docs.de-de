---
title: Klasse CComContainedObject | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
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
ms.openlocfilehash: 60958f328d78205c3432f35ed4e3e3c4b652ebfe
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontainedobject-class"></a>CComContainedObject-Klasse
Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) durch die Delegierung an den des Besitzerobjekts **IUnknown**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Der Konstruktor. Den Member Zeiger auf den des Besitzerobjekts initialisiert `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Ruft den des Besitzerobjekts `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die Schnittstelle, die in dem Objekt angefordert.|  
|[CComContainedObject::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet `CComContainedObject` in Klassen [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), und [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) durch die Delegierung an den des Besitzerobjekts **IUnknown**. (Der Besitzer ist das äußere Objekt einer Aggregation oder das Objekt, für das eine Tearoff Schnittstelle erstellt wird.) `CComContainedObject` Aufrufe `CComObjectRootEx`des `OuterQueryInterface`, `OuterAddRef`, und `OuterRelease`, bis alle geerbten `Base`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-nameaddrefa--ccomcontainedobjectaddref"></a><a name="addref"></a>CComContainedObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="a-nameccomcontainedobjecta--ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 Der Konstruktor.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Der des Besitzerobjekts **IUnknown**.  
  
### <a name="remarks"></a>Hinweise  
 Legt die `m_pOuterUnknown` Member Zeiger (vererbt, bis die `Base` Klasse) auf `pv`.  
  
##  <a name="a-namedtora--ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 Der Destruktor.  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="a-namegetcontrollingunknowna--ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 Gibt die `m_pOuterUnknown` Member Zeiger (über vererbt der *Base* Klasse), enthält des Besitzerobjekts **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der des Besitzerobjekts **IUnknown**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist möglicherweise virtuellen Wenn `Base` deklariert hat, die [DECLARE_GET_CONTROLLING_UNKNOWN](http://msdn.microsoft.com/library/82b0199a-a9d5-4f95-a711-fa1ae18e1f77) Makro.  
  
##  <a name="a-namequeryinterfacea--ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CComContainedObject::QueryInterface  
 Ruft einen Zeiger auf die Schnittstelle, die in dem Objekt angefordert.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObject` Wert **NULL**.  
  
 `pp`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt diese Schnittstelle nicht unterstützt `pp` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="a-namereleasea--ccomcontainedobjectrelease"></a><a name="release"></a>CComContainedObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds **Version** gibt einen Wert an, die hilfreich für die Diagnose oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

