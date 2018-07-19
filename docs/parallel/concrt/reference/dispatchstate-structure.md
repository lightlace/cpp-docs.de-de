---
title: DispatchState-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d3b62248d305e6acebdc8a03b7ef48c2910b28
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691065"
---
# <a name="dispatchstate-structure"></a>DispatchState-Struktur
Die `DispatchState`-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`-Methode verwendet. Sie beschreibt die Umstände, unter denen die `Dispatch`-Methode für eine `IExecutionContext`-Schnittstelle aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState::DispatchState](#ctor)|Erstellt ein neues `DispatchState`-Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Die Größe dieser Struktur, die für die versionsverwaltung verwendet wird.|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherigen Kontext asynchron blockiert. Dies ist nur für den UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für andere Ausführungskontexte.|  
|[DispatchState::m_reserved](#m_reserved)|Bits reserviert für zukünftige Informationen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `DispatchState`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>  DispatchState:: DispatchState-Konstruktor  
 Erstellt ein neues `DispatchState`-Objekt.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>  DispatchState:: M_dispatchstatesize-Datenmember  
 Die Größe dieser Struktur, die für die versionsverwaltung verwendet wird.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  DispatchState:: M_fispreviouscontextasynchronouslyblocked-Datenmember  
 Gibt an, ob dieser Kontext eingegeben hat die `Dispatch` Methode, da der vorherigen Kontext asynchron blockiert. Dies ist nur für den UMS-Planungskontext verwendet und ist auf den Wert festgelegt `0` für andere Ausführungskontexte.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>  DispatchState:: M_reserved-Datenmember  
 Bits reserviert für zukünftige Informationen.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
