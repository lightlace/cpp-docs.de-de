---
title: Klasse CComObjectGlobal | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 8c371eee9de660a2bb08e67f35a5a6c81d32eee0
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal-Klasse
Diese Klasse verwaltet einen Verweiszähler für das Modul mit der `Base` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Der Konstruktor.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Implementiert ein globales `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Implementiert ein globales `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Implementiert eine globale **Version**.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Enthält die **HRESULT** während der Erstellung der zurückgegebenen der `CComObjectGlobal` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectGlobal`verwaltet einen Verweiszähler für das Modul mit der `Base` Objekt. `CComObjectGlobal`Stellt sicher, dass das Objekt nicht gelöscht wird, solange das Modul nicht freigegeben wird. Das Objekt wird nur entfernt werden, wenn der Verweiszähler für das gesamte Modul auf Null geht.  
  
 Verwenden Sie z. B. `CComObjectGlobal`, eine Klassenfactory aufnehmen kann ein allgemeine globales Objekt, das von allen Clients gemeinsam verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 Erhöht den Verweiszähler des Objekts um 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose und testen.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `AddRef` Aufrufe **_Module::Lock**, wobei **_Module** ist die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 Der Konstruktor. Aufrufe `FinalConstruct` und legt dann [M_hResFinalConstruct](#m_hresfinalconstruct) an der `HRESULT` zurückgegebene `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie nicht die Basisklasse abgeleitet haben [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), Sie müssen angeben, eigene `FinalConstruct` Methode. Der Destruktor ruft `FinalRelease` auf.  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 Der Destruktor.  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordneten Ressourcen und ruft frei [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 Enthält die `HRESULT` aus Aufrufen von `FinalConstruct` während der Erstellung eines der `CComObjectGlobal` Objekt.  
  
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
 [in] Die GUID der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom Iid oder **NULL** Wenn die Schnittstelle nicht gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 `QueryInterface`behandelt nur Schnittstellen im COM-Zuordnungstabelle.  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 Dekrementiert den Verweiszähler des Objekts um 1.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds **Version** gibt einen Wert an, die möglicherweise hilfreich für die Diagnose und testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung **Version** Aufrufe **_Module::Unlock**, wobei **_Module** ist die globale Instanz von [CComModule](../../atl/reference/ccommodule-class.md) oder eine Klasse abgeleitet.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectStack-Klasse](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

