---
title: CComObject Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComObject<Base>
- ATL::CComObject
- ATL::CComObject<Base>
- ATL.CComObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
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
ms.openlocfilehash: 5f752b96d4a722fbddfcc9e5be3a82b8b12a86a1
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobject-class"></a>CComObject-Klasse
Diese Klasse implementiert **IUnknown** für ein nicht zusammengesetztes Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über andere Schnittstellen für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Der Konstruktor.|  
|[CComObject:: ~ CComObject](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt.|  
|[CComObject::CreateInstance](#createinstance)|(Statisch) Erstellt ein neues `CComObject` Objekt.|  
|[CComObject::QueryInterface](#queryinterface)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComObject::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObject`implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein nicht zusammengesetztes Objekt. Ruft jedoch zu `QueryInterface`, `AddRef`, und **Version** an delegiert werden `CComObjectRootEx`.  
  
 Weitere Informationen zur Verwendung von `CComObject`, finden Sie im Artikel [Grundlagen von ATL-COM-Objekte](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-nameaddrefa--ccomobjectaddref"></a><a name="addref"></a>CComObject::AddRef  
 Inkrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen inkrementiert Verweiszähler für das Objekt. Dieser Wert möglicherweise hilfreich bei der Diagnose oder testen.  
  
##  <a name="a-nameccomobjecta--ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject  
 Der Konstruktor inkrementiert die Sperrenanzahl des Moduls.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 **"void"\***  
 [in] Dieses unbenannte Parameter wird nicht verwendet. Für die Symmetrie mit anderen vorhanden **CCom***XXX*`Object`*XXX* Konstruktoren.  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor verringert es.  
  
 Wenn ein `CComObject`-abgeleitetes Objekt wird erfolgreich erstellt mithilfe der **neue** Operatoren und der Verweiszähler ist 0. Um den Verweiszähler auf den korrekten Wert (1) festzulegen, stellen Sie einen Aufruf der [AddRef](#addref) Funktion.  
  
##  <a name="a-namedtora--ccomobjectccomobject"></a><a name="dtor"></a>CComObject:: ~ CComObject  
 Der Destruktor.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, Aufrufe [FinalRelease](ccomobjectrootex-class.md#finalrelease), und verringert das Modul Sperrenanzahl.  

  
##  <a name="a-namecreateinstancea--ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::CreateInstance  
 Die statische Funktion können Sie zum Erstellen eines neuen **CComObject** `Base` ** > ** -Objekts, ohne den Aufwand für das [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `pp`  
 [out] Ein Zeiger auf eine **CComObject** `Base` ** > ** Zeiger. Wenn `CreateInstance` ist fehlgeschlagen, `pp` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Objekt besitzt einen Verweiszähler&0; (null), rufen Sie also `AddRef` verwenden Sie dann sofort **Version** den Verweis auf den Objektzeiger freizugeben, wenn Sie fertig sind.  
  
 Wenn Sie nicht den Zugriff auf das Objekt weisen müssen, aber dennoch, erstellen Sie ein neues Objekt der Mehraufwand für möchten `CoCreateInstance`, verwenden Sie [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) stattdessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#38;](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM NR.&39;](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="a-namequeryinterfacea--ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="a-namereleasea--ccomobjectrelease"></a><a name="release"></a>CComObject::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt den neuen dekrementiert Verweiszähler für das Objekt. In Debugbuilds möglicherweise der Rückgabewert hilfreich für die Diagnose oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

