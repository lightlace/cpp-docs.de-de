---
title: CComQIPtr Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs: C++
helpviewer_keywords: CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6240b779977f99d362f7fd37ef5526ce08e89bd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomqiptr-class"></a>CComQIPtr-Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine COM-Schnittstelle, die Angabe des Typs der Zeiger gespeichert werden soll.  
  
 `piid`  
 Ein Zeiger auf die IID der `T`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet `CComQIPtr` und [CComPtr](../../atl/reference/ccomptr-class.md) zum Verwalten von COM-Schnittstellenzeiger auf beide abgeleitet [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Beide Klassen ausführen automatische verweiszählung über Aufrufe von `AddRef` und **Version**. Überladene Operatoren zeigervorgängen zu behandeln.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcomcli.h"  
  
##  <a name="ccomqiptr"></a>CComQIPtr::CComQIPtr  
 Der Konstruktor.  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Wird verwendet, um den Schnittstellenzeiger zu initialisieren.  
  
 `T`  
 Eine COM-Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf die IID der `T`.  
  
##  <a name="operator_eq"></a>CComQIPtr::operator =  
 Der Zuweisungsoperator.  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Wird verwendet, um den Schnittstellenzeiger zu initialisieren.  
  
 `T`  
 Eine COM-Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf die IID der `T`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die aktualisierte `CComQIPtr` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase-Klasse](../../atl/reference/ccomptrbase-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)
