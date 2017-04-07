---
title: CComPolyObject Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 37be4c985983cb760246a4a2450c27d175d1f440
ms.lasthandoff: 02/24/2017

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
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Der Konstruktor.|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|Inkrementiert Verweiszähler des Objekts.|  
|[CComPolyObject::CreateInstance](#createinstance)|(Statisch) Können Sie zum Erstellen eines neuen **CComPolyObject** `contained` ** > ** ohne den Aufwand für das Objekt [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|Führt die letzte Initialisierung der `m_contained`.|  
|[CComPolyObject::FinalRelease](#finalrelease)|Führt die endgültigen Beseitigung von `m_contained`.|  
|[CComPolyObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComPolyObject::Release](#release)|Dekrementiert die Verweiszähler des Objekts.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|Delegaten **IUnknown** an die äußere unbekannte aufgerufen wird, wenn das Objekt aggregiert wird oder auf die **IUnknown** des Objekts, wenn das Objekt nicht aggregiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CComPolyObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein Objekt aggregierte oder aggregiert.  
  
 Wenn eine Instanz des `CComPolyObject` erstellt wird, wird den Wert des äußeren unbekannt aktiviert ist. Ist dies **NULL**, **IUnknown** ist für ein nicht zusammengesetztes Objekt implementiert. Wenn die äußere unbekannte nicht **NULL**, **IUnknown** für ein zusammengesetztes Objekt implementiert wird.  
  
 Der Vorteil der Verwendung `CComPolyObject` besteht darin, dass Sie vermeiden, dass beide [CComAggObject](../../atl/reference/ccomaggobject-class.md) und [CComObject](../../atl/reference/ccomobject-class.md) in Ihrem Modul zusammengefasste und aggregierte behandelt. Ein einzelnes `CComPolyObject` -Objekt verarbeitet beide Fälle. Dies bedeutet, dass nur eine Kopie der Vtable und eine Kopie der Funktionen im Modul vorhanden sind. Wenn die Vtable umfangreich ist, kann dies Modulgröße erheblich beeinträchtigen. Wenn die Vtable klein ist, jedoch mithilfe `CComPolyObject` kann in einem etwas größeren Modul führen, da er nicht für ein Objekt aggregierten oder aggregierte optimiert ist wie `CComAggObject` und `CComObject`.  
  
 Wenn die `DECLARE_POLY_AGGREGATABLE` Makro wird in der Object-Klassendefinition angegeben `CComPolyObject` verwendet werden, um das Objekt zu erstellen. `DECLARE_POLY_AGGREGATABLE`wird automatisch deklariert werden, wenn Sie ATL-Projekt-Assistenten verwenden, um eine vollständige Kontrolle oder Internet Explorer-Steuerelement zu erstellen.  
  
 Wenn aggregiert, die `CComPolyObject` Objekt verfügt über einen eigenen **IUnknown**, des äußeren Objekts trennen **IUnknown**, und verwaltet seine eigenen Verweiszähler. `CComPolyObject`verwendet [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) an die äußere unbekannte delegieren.  
  
 Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComPolyObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="ccompolyobject"></a>CComPolyObject::CComPolyObject  
 Der Konstruktor.  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Ein Zeiger auf die äußere unbekannte, wenn das Objekt aggregiert werden soll, oder **NULL** Wenn das Objekt, wenn das Objekt nicht aggregiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Datenmember, [M_contained](#m_contained), und erhöht die Anzahl der Sperren Modul.  
  
 Der Destruktor verringert das Modul Sperrenanzahl.  
  
##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject  
 Der Destruktor.  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert das Modul Sperrenanzahl.  
  
##  <a name="createinstance"></a>CComPolyObject::CreateInstance  
 Können Sie zum Erstellen eines neuen **CComPolyObject** `contained` ** > ** ohne den Aufwand für das Objekt [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComPolyObject** `contained` ** > ** Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt besitzt einen Verweiszähler&0; (null), rufen Sie also `AddRef` verwenden Sie dann sofort **Version** den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht Zugriff auf das Objekt direkten benötigen, aber dennoch, erstellen Sie ein neues Objekt der Mehraufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
##  <a name="finalconstruct"></a>CComPolyObject::FinalConstruct  
 Während der letzten Stufen der Objektkonstruktion aufgerufen wird, führt diese Methode keine endgültige Initialisierung auf dem [M_contained](#m_contained) -Datenmember.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="finalrelease"></a>CComPolyObject::FinalRelease  
 Diese Methode aufgerufen wird, während die Zerstörung freigegeben werden die [M_contained](#m_contained) -Datenmember.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComPolyObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von der-Klasse abgeleitetes Objekt.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
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
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObject` Wert **NULL**.  
  
 `pp`  
 [out] Ein Zeiger auf die Schnittstelle identifizierten **__uuidof(Q)**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Für ein zusammengesetztes Objekt, wenn die angeforderte Schnittstelle wird **IUnknown**, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts **IUnknown** und den Verweiszähler erhöht. Anderenfalls fragt diese Methode für die Schnittstelle über die `CComContainedObject` Datenmember, [M_contained](#m_contained).  
  
##  <a name="release"></a>CComPolyObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds **Version** gibt einen Wert an, die hilfreich für die Diagnose oder testen. Bei der Builderstellung aufgeführt **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

