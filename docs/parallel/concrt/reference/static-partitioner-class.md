---
title: Static_partitioner-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20dad961b694042c721f388c9a40e0bf99b9b77d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="staticpartitioner-class"></a>static_partitioner-Klasse
Die `static_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in so viele Blöcke unterteilt, wie Worker für den zugrunde liegenden Planer verfügbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[static_partitioner](#ctor)|Erstellt ein `static_partitioner`-Objekt.|  
|[~static_partitioner Destructor](#dtor)|Zerstört ein `static_partitioner`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `static_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a> ~static_partitioner 

 Zerstört ein `static_partitioner`-Objekt.  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a> static_partitioner 

 Erstellt ein `static_partitioner`-Objekt.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
