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
- concrtrm/concurrency::ITopologyExecutionResource
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: cc54beb4790c9d2ea5bfcb2c8ffd4bca7dca399e
ms.lasthandoff: 02/24/2017

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
|[Itopologyexecutionresource:: GetID-Methode](#getid)|Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.|  
|[Itopologyexecutionresource:: GetNext-Methode](#getnext)|Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, als vom Ressourcen-Manager überwacht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namegetida--itopologyexecutionresourcegetid-method"></a><a name="getid"></a>Itopologyexecutionresource:: GetID-Methode  
 Gibt die Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.  
  
##  <a name="a-namegetnexta--itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>Itopologyexecutionresource:: GetNext-Methode  
 Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge zurück.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge. Wenn die Reihenfolge des Knotens, zu dem diese Ausführungsressource gehört, keine weiteren Knoten vorhanden sind, wird diese Methode den Wert zurück `NULL`.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

