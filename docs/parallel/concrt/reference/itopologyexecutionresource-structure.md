---
title: ITopologyExecutionResource-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs: C++
helpviewer_keywords: ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: caf2cc77cd31df611f71d07c5a0a49f600767f81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource-Struktur
Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Itopologyexecutionresource:: GetID](#getid)|Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource zurück.|  
|[Itopologyexecutionresource:: GetNext](#getnext)|Gibt eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist in der Regel verwendet, um die Topologie des Systems zu durchlaufen, als vom Ressourcen-Manager überwacht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getid"></a>Itopologyexecutionresource:: GetID-Methode  
 Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
##  <a name="getnext"></a>Itopologyexecutionresource:: GetNext-Methode  
 Gibt eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge zurück.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge. Wenn in der Reihenfolge der Knoten, zu dem diese Ausführungsressource gehört, Enumeration keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert zurück `NULL`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
