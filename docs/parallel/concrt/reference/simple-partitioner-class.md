---
title: Simple_partitioner-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4b4b92e3ad6324b3f25862c81892fde8f2c1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="simplepartitioner-class"></a>simple_partitioner-Klasse
Die `simple_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[simple_partitioner](#ctor)|Erstellt ein `simple_partitioner`-Objekt.|  
|[~simple_partitioner Destructor](#dtor)|Zerstört ein `simple_partitioner`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `simple_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a> ~simple_partitioner 

 Zerstört ein `simple_partitioner`-Objekt.  
  
```
~simple_partitioner();
```  
  
##  <a name="ctor"></a> simple_partitioner 

 Erstellt ein `simple_partitioner`-Objekt.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Parameter  
 `_Chunk_size`  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
