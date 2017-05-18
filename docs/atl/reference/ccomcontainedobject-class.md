---
title: CComContainedObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: ac817cedb4c7ed67e698969b14645f5659aab2ad
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="ccomcontainedobject-class"></a>CComContainedObject-Klasse
Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) delegiert Vorgänge an den Besitzer des Objekts **IUnknown**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Der Konstruktor. Initialisiert die Member-Zeiger auf des Besitzerobjekt `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Besitzerobjekt an.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Ruft des Besitzerobjekt `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die Schnittstelle für das Besitzerobjekt angefordert.|  
|[CComContainedObject::Release](#release)|Dekrementiert den Verweiszähler für das Besitzerobjekt.|  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet `CComContainedObject` in Klassen [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), und [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) delegiert Vorgänge an den Besitzer des Objekts **IUnknown**. (Der Besitzer ist das äußere Objekt einer Aggregation oder das Objekt, für das eine Schnittstelle abtrennbare erstellt wird.) `CComContainedObject` Aufrufe `CComObjectRootEx`des `OuterQueryInterface`, `OuterAddRef`, und `OuterRelease`, bis alle geerbten `Base`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComContainedObject::AddRef  
 Inkrementiert den Verweiszähler für das Besitzerobjekt an.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 Der Konstruktor.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Des Besitzerobjekt **IUnknown**.  
  
### <a name="remarks"></a>Hinweise  
 Legt die `m_pOuterUnknown` Member Zeiger (vererbt, bis die `Base` Klasse) auf `pv`.  
  
##  <a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 Der Destruktor.  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 Gibt die `m_pOuterUnknown` Member Zeiger (vererbt, bis die *Base* Klasse), enthält des Besitzerobjekt **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Des Besitzerobjekt **IUnknown**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist möglicherweise virtuelle Wenn `Base` wurde deklariert die [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) Makro.  
  
##  <a name="queryinterface"></a>CComContainedObject::QueryInterface  
 Ruft einen Zeiger auf die Schnittstelle für das Besitzerobjekt angefordert.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObject` festgelegt ist, um **NULL**.  
  
 `pp`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `pp` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="release"></a>CComContainedObject::Release  
 Dekrementiert den Verweiszähler für das Besitzerobjekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds **Version** gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

