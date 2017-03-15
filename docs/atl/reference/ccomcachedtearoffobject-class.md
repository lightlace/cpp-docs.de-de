---
title: Klasse CComCachedTearOffObject | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComCachedTearOffObject
- ATL.CComCachedTearOffObject
- ATL.CComCachedTearOffObject<contained>
- CComCachedTearOffObject
- ATL::CComCachedTearOffObject<contained>
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 96f040c732c5545a9b8febb32fcb1636f0fe4a40
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject-Klasse
Diese Klasse implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine Tearoff Schnittstelle.  
  
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
 Die Klasse abtrennbare abgeleitet `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Der Konstruktor.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|Inkrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Ruft die `m_contained::FinalConstruct` (abtrennbare-Methode der Klasse).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Ruft die `m_contained::FinalRelease` (abtrennbare-Methode der Klasse).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die `IUnknown` von der `CComCachedTearOffObject` -Objekt, oder die angeforderte Schnittstelle für die Klasse abtrennbare (Klasse `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Dekrementiert den Verweiszähler für eine `CComCachedTearOffObject` Objekt, und es zerstört, wenn der Verweiszähler 0 ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|Ein `CComContainedObject` abgeleitetes Objekt aus der Klasse abtrennbare (Klasse `contained`).|  
  
## <a name="remarks"></a>Hinweise  
 `CComCachedTearOffObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine Tearoff Schnittstelle. Diese Klasse unterscheidet sich von `CComTearOffObject` , `CComCachedTearOffObject` verfügt über einen eigenen **IUnknown**getrennt von den des Besitzerobjekts **IUnknown** (der Besitzer ist das Objekt, für die die abtrennbare erstellt wird). `CComCachedTearOffObject`behält sein eigenes Verweiszähler auf seine **IUnknown** und selbst löscht, wenn der Verweiszähler&0; (null) ist. Jedoch bei einer Abfrage für eines seiner abtrennbare Schnittstellen, den Verweiszähler des des Objekts des **IUnknown** erhöht.  
  
 Wenn die `CComCachedTearOffObject` -Objekt implementieren die abtrennbare bereits instanziiert und die Tearoff Schnittstelle für erneut, den gleichen abgefragt `CComCachedTearOffObject` Objekt wiederverwendet wird. Im Gegensatz dazu wird eine Tearoff Schnittstelle von implementiert eine `CComTearOffObject` wird erneut abgefragt, über dem Objekt ein anderes `CComTearOffObject` instanziiert werden.  
  
 Die Besitzerklasse implementieren muss `FinalRelease` und rufen **Version** auf die zwischengespeicherten **IUnknown** für die `CComCachedTearOffObject`, wird der entsprechende Verweiszähler verringert. Dies bewirkt, dass `CComCachedTearOffObject`des `FinalRelease` aufgerufen werden, und die abtrennbare löschen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-nameaddrefa--ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOffObject::AddRef  
 Inkrementiert den Verweiszähler des dem `CComCachedTearOffObject` Objekts um 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose und testen.  
  
##  <a name="a-nameccomcachedtearoffobjecta--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 Der Konstruktor.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Zeiger auf die **IUnknown** von der `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Element [M_contained](#m_contained).  
  
##  <a name="a-namedtora--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 Der Destruktor.  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordneten Ressourcen und ruft frei [FinalRelease](#finalrelease).  
  
##  <a name="a-namefinalconstructa--ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 Aufrufe **m_contained::FinalConstruct** erstellen `m_contained`, `CComContainedObject` <  `contained`> Objekt verwendet, um die von der Klasse abtrennbare implementierten Schnittstelle zugreifen.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="a-namefinalreleasea--ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 Aufrufe **m_contained::FinalRelease** freigeben `m_contained`, `CComContainedObject` <  `contained`> Objekt.  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomcachedtearoffobjectmcontained"></a><a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von Ihrem abtrennbare-Klasse abgeleitetes Objekt.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Die Klasse abtrennbare abgeleitet `CComTearOffObjectBase` und die Schnittstellen, die Ihre abtrennbare Objekt unterstützen soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Methoden `m_contained` erbt werden verwendet, um die Tearoff Schnittstelle in Ihrer Klasse abtrennbare über zwischengespeicherte abtrennbare des Objekts zugreifen `QueryInterface`, `FinalConstruct`, und `FinalRelease`.  
  
##  <a name="a-namequeryinterfacea--ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`, oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die angeforderte Schnittstelle wird **IUnknown**, gibt einen Zeiger auf die `CComCachedTearOffObject`des eigenen **IUnknown** und den Verweiszähler erhöht. Anderenfalls fragt die-Schnittstelle abtrennbare Klasse unter Verwendung der [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) Methode geerbt von `CComObjectRootEx`.  

  
##  <a name="a-namereleasea--ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOffObject::Release  
 Dekrementiert den Verweiszähler um 1 und, wenn der Verweiszähler 0 ist, löscht der `CComCachedTearOffObject` Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In nicht-Debugbuilds gibt immer 0 zurück. In Debugbuilds gibt einen Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
## <a name="see-also"></a>Siehe auch  
 [CComTearOffObject-Klasse](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

