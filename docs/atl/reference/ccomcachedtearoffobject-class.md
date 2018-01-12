---
title: CComCachedTearOffObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs: C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 89240e913f46a3522062317da8089c3ae4bd81ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject-Klasse
Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine abtrennbare-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parameter  
 `contained`  
 Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Der Konstruktor.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|Inkrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Ruft die `m_contained::FinalConstruct` (abtrennbare Methode der Klasse).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Ruft die `m_contained::FinalRelease` (abtrennbare Methode der Klasse).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die `IUnknown` von der `CComCachedTearOffObject` -Objekt, oder auf die angeforderte Schnittstelle für Ihre Klasse abtrennbare (die Klasse `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Dekrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt, und es zerstört, wenn der Verweiszähler auf 0 ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|Ein `CComContainedObject` abgeleitetes Objekt aus der Klasse abtrennbare (die Klasse `contained`).|  
  
## <a name="remarks"></a>Hinweise  
 `CComCachedTearOffObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine abtrennbare-Schnittstelle. Diese Klasse unterscheidet sich von `CComTearOffObject` , `CComCachedTearOffObject` verfügt über eine eigene **IUnknown**, getrennt von den Besitzer des Objekts **IUnknown** (der Besitzer ist das Objekt, für die die abtrennbare erstellt wird). `CComCachedTearOffObject`verwaltet einen eigenen Verweiszähler auf seine **IUnknown** und löscht Sie selbst, sobald der entsprechende Verweiszähler 0 (null) ist. Allerdings bei Abfragen für keines der abtrennbare Schnittstellen, der Besitzer des Objekts den Verweiszähler dieser Planergruppe **IUnknown** wird erhöht.  
  
 Wenn die `CComCachedTearOffObject` -Objekt implementieren die abtrennbare bereits instanziiert wird, und die Schnittstelle abtrennbare für erneut, den gleichen abgefragt `CComCachedTearOffObject` Objekt wiederverwendet wird. Im Gegensatz dazu wird die Implementierung einer Schnittstelle abtrennbare durch eine `CComTearOffObject` erneut über das Besitzerobjekt abgefragt wird eine andere `CComTearOffObject` instanziiert werden.  
  
 Die Besitzerklasse implementieren muss `FinalRelease` und rufen **Release** auf die zwischengespeicherten **IUnknown** für die `CComCachedTearOffObject`, wird der entsprechende Verweiszähler zu verringern. Dies bewirkt, dass `CComCachedTearOffObject`des `FinalRelease` aufgerufen werden, und die abtrennbare löschen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComCachedTearOffObject::AddRef  
 Inkrementiert den Verweiszähler des dem `CComCachedTearOffObject` Objekts um 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise nützlich für die Diagnose und testen.  
  
##  <a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 Der Konstruktor.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Zeiger auf die **IUnknown** von der `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Member [M_contained](#m_contained).  
  
##  <a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 Der Destruktor.  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen und ruft [FinalRelease](#finalrelease).  
  
##  <a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 Aufrufe **m_contained::FinalConstruct** erstellen `m_contained`, `CComContainedObject` <  `contained`> Objekt, mit dem die Schnittstelle implementiert, die von Ihrer Klasse abtrennbare zugreifen.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 Aufrufe **m_contained::FinalRelease** freizugeben `m_contained`, `CComContainedObject` <  `contained`> Objekt.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von Ihrem abtrennbare-Klasse abgeleitetes Objekt.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Abgeleitet von die Klasse abtrennbare `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methoden `m_contained` erbt werden verwendet, um die Schnittstelle abtrennbare in Ihrer Klasse abtrennbare über zwischengespeicherte abtrennbare des Objekts zugreifen `QueryInterface`, `FinalConstruct`, und `FinalRelease`.  
  
##  <a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`, oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die angeforderte Schnittstelle wird **IUnknown**, gibt einen Zeiger auf die `CComCachedTearOffObject`des eigenen **IUnknown** und inkrementiert den Verweiszähler dieser Planergruppe. Andernfalls, Abfragen für die Schnittstelle abtrennbare Klasse unter Verwendung der [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) Methode geerbt von `CComObjectRootEx`.  

  
##  <a name="release"></a>CComCachedTearOffObject::Release  
 Dekrementiert den Verweiszähler um 1 und, wenn der Verweiszähler auf 0 ist, löscht der `CComCachedTearOffObject` Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer 0 zurück. Debug-Builds gibt einen Wert an, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
## <a name="see-also"></a>Siehe auch  
 [CComTearOffObject-Klasse](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
