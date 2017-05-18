---
title: DispatchState-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a617d1f1d7f68c00c7011daffc6ba59f08c43a1e
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|[DispatchState:: DispatchState](#ctor)|Erstellt ein neues `DispatchState`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState:: M_dispatchstatesize](#m_dispatchstatesize)|Die Größe dieser Struktur, die für die Versionskontrolle verwendet wird.|  
|[DispatchState:: M_fispreviouscontextasynchronouslyblocked](#m_fispreviouscontextasynchronouslyblocked)|Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherige Kontext asynchron blockiert hat. Dies wird nur im UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für alle anderen Ausführungskontexte.|  
|[DispatchState:: M_reserved](#m_reserved)|Bits für zukünftige Informationen reserviert.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DispatchState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>DispatchState:: DispatchState-Konstruktor  
 Erstellt ein neues `DispatchState`-Objekt.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>DispatchState:: M_dispatchstatesize-Datenmember  
 Die Größe dieser Struktur, die für die Versionskontrolle verwendet wird.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState:: M_fispreviouscontextasynchronouslyblocked-Datenmember  
 Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherige Kontext asynchron blockiert hat. Dies wird nur im UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für alle anderen Ausführungskontexte.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>DispatchState:: M_reserved-Datenmember  
 Bits für zukünftige Informationen reserviert.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

