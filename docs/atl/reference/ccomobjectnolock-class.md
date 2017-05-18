---
title: Klasse CComObjectNoLock | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 4cf4cad1a3b1a4ac0a21ef76a0eaca35732abf3a
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock-Klasse
Diese Klasse implementiert **IUnknown** für eine aggregierte Objekt unterstützt nicht die Sperrenanzahl Modul im Konstruktor inkrementieren.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Die Klasse abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), wie auch über eine beliebige andere Schnittstelle für das Objekt unterstützt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Konstruktor.|  
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|Inkrementiert den Verweiszähler für das Objekt.|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|Gibt einen Zeiger auf die angeforderte Schnittstelle.|  
|[CComObjectNoLock::Release](#release)|Dekrementiert den Verweiszähler für das Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CComObjectNoLock`ähnelt dem [CComObject](../../atl/reference/ccomobject-class.md) , als dass es implementiert [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) für eine aggregierte Objekt jedoch `CComObjectNoLock` wird im Konstruktor nicht erhöhen die Modul-Sperre angerechnet.  
  
 ATL verwendet `CComObjectNoLock` intern für Klassenfactorys. Im Allgemeinen wird diese Klasse nicht direkt verwendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="addref"></a>CComObjectNoLock::AddRef  
 Inkrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
##  <a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock  
 Der Konstruktor. Im Gegensatz zu [CComObject](../../atl/reference/ccomobject-class.md), erhöht sich die Anzahl der Sperren Modul nicht.  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 **"void"\***  
 [in] Dieses unbenannte Parameter wird nicht verwendet. Für die Symmetrie mit anderen vorhanden **CCom***XXX*`Object`*XXX* Konstruktoren.  
  
##  <a name="dtor"></a>CComObjectNoLock:: ~ CComObjectNoLock  
 Der Destruktor.  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordneten Ressourcen und ruft frei [FinalRelease](ccomobjectrootex-class.md#finalrelease).  

  
##  <a name="queryinterface"></a>CComObjectNoLock::QueryInterface  
 Ruft einen Zeiger auf die angeforderte Schnittstelle ab.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der angeforderten Schnittstelle.  
  
 `ppvObject`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `iid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObject` Wert **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
##  <a name="release"></a>CComObjectNoLock::Release  
 Dekrementiert den Verweiszähler für das Objekt.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Rückgabewert  
 In Debugbuilds **Version** gibt einen Wert an, die hilfreich für die Diagnose oder testen. In nicht-Debugbuilds **Version** gibt immer 0 zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

