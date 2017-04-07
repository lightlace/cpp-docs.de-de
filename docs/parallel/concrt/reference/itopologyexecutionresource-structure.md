---
title: ITopologyExecutionResource-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d9671dbf84a1104bc3b6f3a6f9d383aac167759c
ms.lasthandoff: 03/17/2017

---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource-Struktur
Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Itopologyexecutionresource:: GetID](#getid)|Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.|  
|[Itopologyexecutionresource:: GetNext](#getnext)|Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, als vom Ressourcen-Manager überwacht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getid"></a>Itopologyexecutionresource:: GetID-Methode  
 Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
##  <a name="getnext"></a>Itopologyexecutionresource:: GetNext-Methode  
 Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge zurück.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge. Wenn die Reihenfolge des Knotens, zu dem diese Ausführungsressource gehört, keine weiteren Knoten vorhanden sind, wird diese Methode den Wert zurück `NULL`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

