---
title: CComObject-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89a909b715633488cff37fa87ea5950681e208cd
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881840"
---
# <a name="ccomobject-class"></a>CComObject-Klasse
Diese Klasse implementiert `IUnknown` für einen zusammengesetzten Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 *Basis*  
 Abgeleitet von die Klasse [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Der Konstruktor.|  
|[CComObject::~CComObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt an.|  
|[CComObject::CreateInstance](#createinstance)|(Statisch) Erstellt ein neues `CComObject` Objekt.|  
|[CComObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComObject::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObject` implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für einen zusammengesetzten Objekt. Ruft jedoch um `QueryInterface`, `AddRef`, und `Release` delegiert werden `CComObjectRootEx`.  
  
 Weitere Informationen zur Verwendung von `CComObject`, finden Sie im Artikel [Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>  CComObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt an.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen inkrementiert Verweiszähler für das Objekt zurück. Dieser Wert kann für die Diagnose oder testen hilfreich sein.  
  
##  <a name="ccomobject"></a>  CComObject::CComObject  
 Der Konstruktor erhöht die Sperrenanzahl des Moduls.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 **void\***  
 [in] Dieser unbenannte Parameter wird nicht verwendet. Sie vorhanden ist, für die Symmetrie mit anderen **CCom *** XXX*`Object`*XXX* Konstruktoren.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor verringert es.  
  
 Wenn eine `CComObject`-abgeleitetes Objekt wurde erfolgreich erstellt mithilfe der **neue** Operatoren und die Initiale Verweisanzahl ist 0. Um die Anzahl der Verweise auf den entsprechenden Wert (1) festzulegen, stellen Sie einen Aufruf der ["AddRef"](#addref) Funktion.  
  
##  <a name="dtor"></a>  CComObject:: ~ CComObject  
 Der Destruktor.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](ccomobjectrootex-class.md#finalrelease), und verringert die Modul Sperrenanzahl.  

  
##  <a name="createinstance"></a>  CComObject::CreateInstance  
 Diese statischen Funktion können Sie zum Erstellen eines neuen **CComObject <** `Base` **>** Objekt, ohne den Aufwand für [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 *PP*  
 [out] Ein Zeiger auf eine **CComObject <** `Base` **>** Zeiger. Wenn `CreateInstance` nicht erfolgreich ist, ist *pp* auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt weist einer Verweisanzahl von 0 (null), weshalb `AddRef` verwenden Sie dann sofort `Release` , den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie die nicht den Zugriff auf das Objekt weisen müssen, aber dennoch, erstellen Sie ein neues Objekt ohne den Aufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>  CComObject::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Parameter  
 *IID*  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 *ppvObject*  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom *Iid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObject* auf NULL festgelegt ist.  
  
 *PP*  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom Typ `Q`. Wenn das Objekt nicht über diese Schnittstelle unterstützt *pp* auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
##  <a name="release"></a>  CComObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen dekrementiert Verweiszähler für das Objekt zurück. In Debugbuilds möglicherweise der Rückgabewert bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds `Release` gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
