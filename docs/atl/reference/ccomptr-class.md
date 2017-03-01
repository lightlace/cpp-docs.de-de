---
title: CComPtr-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
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
ms.openlocfilehash: ae7bb5e85f23492bdbef4af86d9f68fa83c991e2
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptr-class"></a>CComPtr-Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|Der Konstruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|Weist einen Zeiger auf den Member-Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 ATL verwendet `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM-Schnittstellenzeiger zu verwalten. Beide abgeleitet sind [CComPtrBase](../../atl/reference/ccomptrbase-class.md), und führen Sie sowohl automatische verweiszählung.  
  
 Die **CComPtr** und [CComQIPtr](../../atl/reference/ccomqiptr-class.md) Klassen können Speicherverluste zu vermeiden, indem Sie automatische verweiszählung ausführen.  Die folgenden Funktionen werden die gleichen logischen Operationen ausführen; Beachten Sie jedoch, wie die zweite Version weniger fehleranfällig mit möglicherweise die **CComPtr** Klasse:  
  
 [!code-cpp[NVC_ATL_Utilities&#130;](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities&#131;](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 Verknüpfen Sie in Debugbuilds atlsd.lib für codeablaufverfolgung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameccomptra--ccomptrccomptr"></a><a name="ccomptr"></a>CComPtr::CComPtr  
 Der Konstruktor.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>Parameter  
 `lp`  
 Wird verwendet, um den Schnittstellenzeiger zu initialisieren.  
  
 `T`  
 Eine COM-Schnittstelle.  
  
##  <a name="a-nameoperatoreqa--ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::operator =  
 Zuweisungsoperator.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die aktualisierte `CComPtr` Objekt  
  
### <a name="remarks"></a>Hinweise  
 Dieser Vorgang AddRefs das neue Objekt und Versionen, die im vorhandene Objekt, wenn eine vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

