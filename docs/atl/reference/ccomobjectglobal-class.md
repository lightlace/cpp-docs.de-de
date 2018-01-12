---
title: CComObjectGlobal Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs: C++
helpviewer_keywords: CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d5264a2ab8e1bbc4c3f4eac4d83d096d91e8846
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal-Klasse
Diese Klasse verwaltet einen Verweiszähler für das Modul mit Ihrem `Base` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut wie aus einer beliebigen anderen Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Der Konstruktor.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Implementiert einen globalen `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Implementiert einen globalen `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Implementiert einen globalen **Version**.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Enthält die **HRESULT** während der Erstellung der zurückgegebenen der `CComObjectGlobal` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectGlobal`verwaltet einen Verweiszähler für das Modul mit Ihrem `Base` Objekt. `CComObjectGlobal`Stellt sicher, dass das Objekt wird nicht gelöscht werden, solange das Modul nicht freigegeben wird. Das Objekt wird nur entfernt werden, wenn der Verweiszähler für das gesamte Modul auf Null geht.  
  
 Beispiel für die Verwendung `CComObjectGlobal`, eine Klassenfactory aufnehmen kann ein allgemeine globales Objekt, das von allen Clients gemeinsam verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 Inkrementiert den Verweiszähler des Objekts um 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise nützlich für die Diagnose und testen.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `AddRef` Aufrufe **_Module::Lock**, wobei **_Module** wird die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 Der Konstruktor. Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) auf die `HRESULT` zurückgegebenes `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht die Basisklasse aus abgeleiteten [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), geben Sie an Ihre eigenen `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 Der Destruktor.  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 Enthält die `HRESULT` aufrufenden `FinalConstruct` während der Erstellung von der `CComObjectGlobal` Objekt.  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectGlobal::QueryInterface  
 Ruft einen Zeiger auf den angeforderten Schnittstellenzeiger ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Die GUID der Schnittstelle angefordert wird.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch die Iid oder **NULL** , wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 `QueryInterface`nur behandelt Schnittstellen in der COM-Zuordnungstabelle.  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 Dekrementiert den Verweiszähler des Objekts um 1.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds **Version** gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich und testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig **Release** Aufrufe **_Module::Unlock**, wobei **_Module** wird die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectStack-Klasse](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
