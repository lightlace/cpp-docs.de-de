---
title: CComObject Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27da00e09ca88cc06b8bafed8f8601dac756fd34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobject-class"></a>CComObject-Klasse
Diese Klasse implementiert **IUnknown** für eine aggregierte Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut ebenso andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Der Konstruktor.|  
|[CComObject:: ~ CComObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt an.|  
|[CComObject::CreateInstance](#createinstance)|(Statisch) Erstellt ein neues `CComObject` Objekt.|  
|[CComObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComObject::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine aggregierte Objekt. Allerdings Aufrufe von `QueryInterface`, `AddRef`, und **Release** werden an delegiert `CComObjectRootEx`.  
  
 Weitere Informationen zur Verwendung von `CComObject`, finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>CComObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt an.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen inkrementierte Verweiszähler für das Objekt zurück. Dieser Wert kann für die Diagnose oder testen hilfreich sein.  
  
##  <a name="ccomobject"></a>CComObject::CComObject  
 Der Konstruktor inkrementiert die Anzahl der Module Sperre.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 **void\***  
 [in] Dieses unbenannte Parameter wird nicht verwendet. Es vorhanden ist, für die Symmetrie mit anderen **CCom***XXX*`Object`*XXX* Konstruktoren.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor verringert es.  
  
 Wenn eine `CComObject`-abgeleitete Objekt wird erfolgreich erstellt mithilfe der **neue** -Operator, der der Verweiszähler ist 0. Um den Verweiszähler dieser Planergruppe den richtigen Wert (1) festzulegen, nehmen Sie einen Aufruf der [AddRef](#addref) Funktion.  
  
##  <a name="dtor"></a>CComObject:: ~ CComObject  
 Der Destruktor.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](ccomobjectrootex-class.md#finalrelease), und verringert die Modul Sperrenanzahl.  

  
##  <a name="createinstance"></a>CComObject::CreateInstance  
 Diese statische Funktion können Sie zum Erstellen eines neuen **CComObject <** `Base`  **>**  Objekt, ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComObject <** `Base`  **>**  Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort **Version** um den Verweis auf die Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht den Zugriff auf das Objekt weisen müssen, aber trotzdem zum Erstellen eines neuen Objekts ohne den Aufwand für `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="release"></a>CComObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen wieder um eins erniedrigt Verweiszähler für das Objekt zurück. Debug-Builds möglicherweise der Rückgabewert bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
