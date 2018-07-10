---
title: CComObjectNoLock Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd7f9fa0ac67592c5fca805eaa4bb4ec4b0ca153
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361474"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock-Klasse
Diese Klasse implementiert **IUnknown** eines zusammengesetzten Objekts, aber wird nicht die Sperrenanzahl Modul im Konstruktor Inkrement.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie gut wie aus einer beliebigen anderen Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Konstruktor.|  
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt an.|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle zurück.|  
|[CComObjectNoLock::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectNoLock` ähnelt dem [CComObject](../../atl/reference/ccomobject-class.md) dahingehend, dass er implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für ein Objekt auf aggregierte jedoch `CComObjectNoLock` wird im Konstruktor nicht Inkrement die Modul-Sperre gezählt.  
  
 ATL verwendet `CComObjectNoLock` intern für Klassenfactorys. Im Allgemeinen verwenden Sie diese Klasse nicht direkt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectNoLock::AddRef  
 Inkrementiert den Verweiszähler für das Objekt an.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock  
 Der Konstruktor. Im Gegensatz zu [CComObject](../../atl/reference/ccomobject-class.md), erhöht sich die Anzahl der Sperren Modul nicht.  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 **void\***  
 [in] Dieses unbenannte Parameter wird nicht verwendet. Es vorhanden ist, für die Symmetrie mit anderen **CCom *** XXX*`Object`*XXX* Konstruktoren.  
  
##  <a name="dtor"></a>  CComObjectNoLock:: ~ CComObjectNoLock  
 Der Destruktor.  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen und ruft [FinalRelease](ccomobjectrootex-class.md#finalrelease).  

  
##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `iid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObject` festgelegt ist, um **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="release"></a>  CComObjectNoLock::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Debug-Builds **Version** gibt einen Wert an, die möglicherweise bei der Diagnose hilfreich oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
