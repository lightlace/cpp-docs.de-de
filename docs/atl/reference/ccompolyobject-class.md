---
title: CComPolyObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: ee44fcec146ef8a8c68b917020ae52e2300eed5e
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="ccompolyobject-class"></a>CComPolyObject-Klasse
Diese Klasse implementiert **IUnknown** für ein Objekt aggregierte oder aggregiert.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parameter  
 `contained`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Der Konstruktor.|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|Inkrementiert Verweiszählerwert des Objekts an.|  
|[CComPolyObject::CreateInstance](#createinstance)|(Statisch) Bietet die Möglichkeit zum Erstellen eines neuen **CComPolyObject** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|Führt die endgültige Initialisierung der `m_contained`.|  
|[CComPolyObject::FinalRelease](#finalrelease)|Führt die endgültigen Löschung von `m_contained`.|  
|[CComPolyObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComPolyObject::Release](#release)|Verringert die Verweiszähler des Objekts.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|Delegaten **IUnknown** an die äußere unbekannte aufgerufen wird, wenn das Objekt aggregiert wird oder auf die **IUnknown** des Objekts, wenn das Objekt nicht aggregiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CComPolyObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein Objekt aggregierte oder aggregiert.  
  
 Wenn eine Instanz von `CComPolyObject` erstellt wird, wird den Wert des äußeren unbekannt aktiviert ist. Ist er **NULL**, **IUnknown** für eine aggregierte Objekt implementiert wird. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Der Vorteil der Verwendung `CComPolyObject` ist, dass Sie vermeiden, dass beide [CComAggObject](../../atl/reference/ccomaggobject-class.md) und [CComObject](../../atl/reference/ccomobject-class.md) innerhalb des Moduls, die zusammengefasste und aggregierte Fälle zu behandeln. Ein einzelnes `CComPolyObject` Objekt verarbeitet die beiden Fällen. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen, die innerhalb des Moduls vorhanden sind. Wenn Ihre Vtable groß ist, kann dies die Modulgröße erheblich verringern. Jedoch verwenden, wenn die Vtable klein ist, `CComPolyObject` kann dazu führen, etwas Modul größer, da sie nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Wenn die `DECLARE_POLY_AGGREGATABLE` Makro wird in der Klassendefinition des Objekts angegeben `CComPolyObject` verwendet werden, um das Objekt zu erstellen. `DECLARE_POLY_AGGREGATABLE`wird automatisch deklariert werden, wenn Sie ATL-Projekt-Assistent zum Erstellen einer Vollzugriff oder Internet Explorer-Steuerelements verwenden.  
  
 Wenn nicht aggregiert, die `CComPolyObject` Objekt verfügt über eine eigene **IUnknown**, des äußeren Objekts als **IUnknown**, und verwaltet seine eigenen Verweiszähler dieser Planergruppe. `CComPolyObject`verwendet [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) an die äußere unbekannte delegieren.  
  
 Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComPolyObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt an.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="ccompolyobject"></a>CComPolyObject::CComPolyObject  
 Der Konstruktor.  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Ein Zeiger auf die äußere unbekannte, wenn das Objekt aggregiert werden, oder **NULL** Wenn das Objekt, wenn das Objekt nicht aggregiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Datenmember, [M_contained](#m_contained), und erhöht die Anzahl der Module Sperre.  
  
 Der Destruktor verringert das Modul Sperrenanzahl.  
  
##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject  
 Der Destruktor.  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert die Modul Sperrenanzahl.  
  
##  <a name="createinstance"></a>CComPolyObject::CreateInstance  
 Bietet die Möglichkeit zum Erstellen eines neuen **CComPolyObject** `contained` **>** Objekt ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComPolyObject** `contained` **>** Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort **Version** um den Verweis auf die Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht Zugriff auf das Objekt direkter benötigen, aber trotzdem zum Erstellen eines neuen Objekts ohne den Aufwand für `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
##  <a name="finalconstruct"></a>CComPolyObject::FinalConstruct  
 Wird aufgerufen, während die letzten Phasen des Objektkonstruktion, führt diese Methode endgültige Initialisierung auf dem [M_contained](#m_contained) -Datenmember.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="finalrelease"></a>CComPolyObject::FinalRelease  
 Diese Methode wird aufgerufen, während die Zerstörung, freigegeben werden. die [M_contained](#m_contained) -Datenmember.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComPolyObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) abgeleitetes Objekt aus der Klasse.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 **IUnknown** ruft über `m_contained` an die äußere unbekannte delegiert werden, wenn das Objekt aggregiert wird, oder auf die **IUnknown** dieses Objekts, wenn das Objekt nicht aggregiert werden.  
  
##  <a name="queryinterface"></a>CComPolyObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `Q`  
 Die COM-Schnittstelle.  
  
 `iid`  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObject` festgelegt ist, um **NULL**.  
  
 `pp`  
 [out] Ein Zeiger auf die Schnittstelle identifizierten **__uuidof(Q)**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Für ein zusammengesetztes Objekt, wenn die angeforderte Schnittstelle wird **IUnknown**, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts **IUnknown** und inkrementiert den Verweiszähler dieser Planergruppe. Andernfalls, fragt diese Methode für die Schnittstelle über den `CComContainedObject` Datenmember, [M_contained](#m_contained).  
  
##  <a name="release"></a>CComPolyObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds **Version** gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder testen. Bei der Builderstellung aufgeführt **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

