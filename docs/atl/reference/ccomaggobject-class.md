---
title: CComAggObject Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 386ab09418c879c0de0d82d729a3de1b2e270016
ms.lasthandoff: 02/24/2017

---
# <a name="ccomaggobject-class"></a>CComAggObject-Klasse
Diese Klasse implementiert die [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) Schnittstelle für ein zusammengesetztes Objekt. Definitionsgemäß ist ein zusammengesetztes Objekt innerhalb eines äußeren Objekts enthalten. Die `CComAggObject` -Klasse ähnelt der [CComObject Klasse](../../atl/reference/ccomobject-class.md), außer dass es eine Schnittstelle verfügbar macht, die direkt für externe Clients zugänglich ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Parameter  
 `contained`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Der Konstruktor.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das aggregierte Objekt.|  
|[CComAggObject::CreateInstance](#createinstance)|Die statische Funktion können Sie zum Erstellen eines neuen **CComAggObject** `contained` ** > ** ohne den Aufwand für das Objekt [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Führt die letzte Initialisierung der `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Führt die endgültigen Beseitigung von `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComAggObject::Release](#release)|Dekrementiert den Verweiszähler für das aggregierte Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Delegaten `IUnknown` Aufrufe an die äußere unbekannte.|  
  
## <a name="remarks"></a>Hinweise  
 `CComAggObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein zusammengesetztes Objekt. `CComAggObject`verfügt über einen eigenen **IUnknown** -Schnittstelle, des äußeren Objekts trennen **IUnknown** -Schnittstelle und verwaltet seine eigenen Verweiszähler.  
  
 Weitere Informationen über die Aggregation finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComAggObject::AddRef  
 Inkrementiert den Verweiszähler für das aggregierte Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Der Konstruktor.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Die äußere unbekannte.  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComContainedObject` Element [M_contained](#m_contained), und erhöht die Anzahl der Sperren Modul.  
  
 Der Destruktor verringert das Modul Sperrenanzahl.  
  
##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject  
 Der Destruktor.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](#finalrelease), und verringert das Modul Sperrenanzahl.  
  
##  <a name="createinstance"></a>CComAggObject::CreateInstance  
 Die statische Funktion können Sie zum Erstellen eines neuen **CComAggObject** `contained` ** > ** ohne den Aufwand für das Objekt [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComAggObject\<***enthaltenen* ** > ** Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt besitzt einen Verweiszähler&0; (null), rufen Sie also `AddRef` verwenden Sie dann sofort **Version** den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht den Zugriff auf das Objekt weisen müssen, aber dennoch, erstellen Sie ein neues Objekt der Mehraufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
##  <a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Während der letzten Stufen der Objektkonstruktion aufgerufen wird, führt diese Methode keine endgültige Initialisierung auf dem [M_contained](#m_contained) Element.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="finalrelease"></a>CComAggObject::FinalRelease  
 Diese Methode aufgerufen wird, während die Zerstörung freigegeben werden die [M_contained](#m_contained) Element.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComAggObject::m_contained  
 Ein [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) von der-Klasse abgeleitetes Objekt.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Parameter  
 `contained`  
 [in] Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
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
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObject` Wert **NULL**.  
  
 `pp`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt diese Schnittstelle nicht unterstützt `pp` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die angeforderte Schnittstelle wird **IUnknown**, `QueryInterface` gibt einen Zeiger auf die aggregierten Objekts **IUnknown** und den Verweiszähler erhöht. Anderenfalls fragt diese Methode für die Schnittstelle über die `CComContainedObject` Element [M_contained](#m_contained).  
  
##  <a name="release"></a>CComAggObject::Release  
 Dekrementiert den Verweiszähler für das aggregierte Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds **Version** gibt einen Wert an, die hilfreich für die Diagnose oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_ONLY_AGGREGATABLE](http://msdn.microsoft.com/library/a54220df-4330-4e4d-b7fb-8b63dd62d337)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

