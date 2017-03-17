---
title: CComQIPtr Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
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
ms.openlocfilehash: e2060a0be3f9780191c316c2df41115e66033d4d
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptr-class"></a>CComQIPtr-Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.  
  
 `piid`  
 Ein Zeiger auf die ID der `T`.  
  
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
 ATL verwendet `CComQIPtr` und [CComPtr](../../atl/reference/ccomptr-class.md) die zum Verwalten von COM-Schnittstellenzeigern abgeleitet [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Beide Klassen auszuführen, automatische verweiszählung, die durch Aufrufe von `AddRef` und **Version**. Überladene Operatoren Zeigeroperationen zu behandeln.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcomcli.h  
  
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
 Ein Zeiger auf die ID der `T`.  
  
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
 Ein Zeiger auf die ID der `T`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die aktualisierte `CComQIPtr` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [CComPtrBase-Klasse](../../atl/reference/ccomptrbase-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits-Klasse](../../atl/reference/ccomqiptrelementtraits-class.md)

