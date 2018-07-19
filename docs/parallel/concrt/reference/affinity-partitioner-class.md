---
title: Affinity_partitioner-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2242346bda717117e2b43ba108d86fd2a77a3b58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691130"
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
|[~ Affinity_partitioner-Destruktor](#dtor)|Zerstört ein `affinity_partitioner` Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a> ~ Affinity_partitioner 

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
