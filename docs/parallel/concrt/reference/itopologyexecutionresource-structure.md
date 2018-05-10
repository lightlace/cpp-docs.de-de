---
title: ITopologyExecutionResource-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: adb456315b2c6d15b7a3696df9a6845a2bd2b899
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
|[ITopologyExecutionResource::GetNext](#getnext)|Gibt eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist in der Regel verwendet, um die Topologie des Systems zu durchlaufen, als vom Ressourcen-Manager überwacht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="getid"></a>  Itopologyexecutionresource:: GetID-Methode  
 Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
##  <a name="getnext"></a>  Itopologyexecutionresource:: GetNext-Methode  
 Gibt eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge zurück.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schnittstelle auf die nächste Ausführungsressource Reihenfolge. Wenn in der Reihenfolge der Knoten, zu dem diese Ausführungsressource gehört, Enumeration keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert zurück `NULL`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
