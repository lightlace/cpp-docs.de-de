---
title: CComAggObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
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
ms.openlocfilehash: 2f580a33b5b92f44e40a3da2e1f7111cbb8ede88
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="ccomaggobject-class"></a>CComAggObject-Klasse
Diese Klasse implementiert die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Schnittstelle für ein zusammengesetztes Objekt. Definitionsgemäß ist ein zusammengesetztes Objekt innerhalb eines äußeren-Objekts enthalten. Die `CComAggObject` -Klasse ähnelt der [CComObject Klasse](../../atl/reference/ccomobject-class.md), außer dass eine Schnittstelle verfügbar macht, der für externe Clients direkt zugänglich ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parameter  
 `contained`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Der Konstruktor.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt aggregiert.|  
|[CComAggObject::CreateInstance](#createinstance)|Diese statische Funktion können Sie zum Erstellen eines neuen **CComAggObject** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Führt die endgültige Initialisierung der `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Führt die endgültigen Löschung von `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComAggObject::Release](#release)|Dekrementiert den Verweiszähler für das aggregierte Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Delegaten `IUnknown` Aufrufe an die äußere unbekannte.|  
  
## <a name="remarks"></a>Hinweise  
 `CComAggObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein zusammengesetztes Objekt. `CComAggObject`verfügt über eine eigene **IUnknown** -Schnittstelle, des äußeren Objekts als **IUnknown** Schnittstelle, und behält eine eigene Verweiszähler dieser Planergruppe.  
  
 Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComAggObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt aggregiert.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Der Konstruktor.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Die äußere unbekannte.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Member [M_contained](#m_contained), und erhöht die Anzahl der Module Sperre.  
  
 Der Destruktor verringert das Modul Sperrenanzahl.  
  
##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject  
 Der Destruktor.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert die Modul Sperrenanzahl.  
  
##  <a name="createinstance"></a>CComAggObject::CreateInstance  
 Diese statische Funktion können Sie zum Erstellen eines neuen **CComAggObject** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComAggObject\<***enthaltenen* **>** Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort **Version** um den Verweis auf die Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht den Zugriff auf das Objekt weisen müssen, aber trotzdem zum Erstellen eines neuen Objekts ohne den Aufwand für `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
##  <a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Wird aufgerufen, während die letzten Phasen des Objektkonstruktion, führt diese Methode endgültige Initialisierung auf dem [M_contained](#m_contained) Member.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="finalrelease"></a>CComAggObject::FinalRelease  
 Diese Methode wird aufgerufen, während die Zerstörung, freigegeben werden. die [M_contained](#m_contained) Member.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComAggObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) abgeleitetes Objekt aus der Klasse.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Alle **IUnknown** ruft über `m_contained` werden an die äußere unbekannte delegiert.  
  
##  <a name="queryinterface"></a>CComAggObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
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
  
### <a name="remarks"></a>Hinweise  
 Wenn die angeforderte Schnittstelle wird **IUnknown**, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts **IUnknown** und inkrementiert den Verweiszähler dieser Planergruppe. Andernfalls, fragt diese Methode für die Schnittstelle über den `CComContainedObject` Member [M_contained](#m_contained).  
  
##  <a name="release"></a>CComAggObject::Release  
 Dekrementiert den Verweiszähler für das aggregierte Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds **Version** gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

