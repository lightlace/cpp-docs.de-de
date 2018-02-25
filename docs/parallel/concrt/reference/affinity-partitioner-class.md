---
title: Affinity_partitioner-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ecc7e20947eee2491bf806f225178724b268ace
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="affinitypartitioner-class"></a>affinity_partitioner-Klasse
Die `affinity_partitioner`-Klasse ist der `static_partitioner`-Klasse ähnlich, allerdings wird die Cacheaffinität dank der Auswahl, den Arbeitsthreads Unterbereiche zuzuordnen, verbessert. Sie kann die Leistung, bei erneutem Ausführen einer Schleife über dem gleichen Dataset, und wenn die Daten im Cache gespeichert werden können, erheblich verbessern. Beachten Sie, dass das gleiche `affinity_partitioner`-Objekt mit nachfolgenden Iterationen einer parallelen Schleife verwendet werden muss, die für ein bestimmtes Dataset ausgeführt wird, um vom Datenort zu profitieren.  
  
## <a name="syntax"></a>Syntax  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[affinity_partitioner](#ctor)|Erstellt ein `affinity_partitioner`-Objekt.|  
|[~affinity_partitioner Destructor](#dtor)|Zerstört ein `affinity_partitioner` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a> ~affinity_partitioner 

 Zerstört ein `affinity_partitioner` Objekt.  
  
```
~affinity_partitioner();
```  
  
##  <a name="ctor"></a> affinity_partitioner 

 Erstellt ein `affinity_partitioner`-Objekt.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
