---
title: DispatchState-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::DispatchState
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 46c2219464e57da4931596e970199549405d02ec
ms.lasthandoff: 02/24/2017

---
# <a name="dispatchstate-structure"></a>DispatchState-Struktur
Die `DispatchState`-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`-Methode verwendet. Sie beschreibt die Umstände, unter denen die `Dispatch`-Methode für eine `IExecutionContext`-Schnittstelle aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState:: DispatchState-Konstruktor](#ctor)|Erstellt ein neues `DispatchState`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState:: M_dispatchstatesize-Datenmember](#m_dispatchstatesize)|Die Größe dieser Struktur, die für die Versionskontrolle verwendet wird.|  
|[DispatchState:: M_fispreviouscontextasynchronouslyblocked-Datenmember](#m_fispreviouscontextasynchronouslyblocked)|Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherige Kontext asynchron blockiert hat. Dies wird nur im UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für alle anderen Ausführungskontexte.|  
|[DispatchState:: M_reserved-Datenmember](#m_reserved)|Bits für zukünftige Informationen reserviert.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DispatchState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora--dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>DispatchState:: DispatchState-Konstruktor  
 Erstellt ein neues `DispatchState`-Objekt.  
  
```
DispatchState();
```  
  
##  <a name="a-namemdispatchstatesizea--dispatchstatemdispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>DispatchState:: M_dispatchstatesize-Datenmember  
 Die Größe dieser Struktur, die für die Versionskontrolle verwendet wird.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="a-namemfispreviouscontextasynchronouslyblockeda--dispatchstatemfispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState:: M_fispreviouscontextasynchronouslyblocked-Datenmember  
 Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherige Kontext asynchron blockiert hat. Dies wird nur im UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für alle anderen Ausführungskontexte.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="a-namemreserveda--dispatchstatemreserved-data-member"></a><a name="m_reserved"></a>DispatchState:: M_reserved-Datenmember  
 Bits für zukünftige Informationen reserviert.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

