---
title: Simple_partitioner-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
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
ms.openlocfilehash: 08d378c841fd9181fe9a2cf918bde9fe3ebbdc32
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="simplepartitioner-class"></a>simple_partitioner-Klasse
Die `simple_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[simple_partitioner](#ctor)|Erstellt ein `simple_partitioner`-Objekt.|  
|[~ Simple_partitioner-Destruktor](#dtor)|Zerstört ein `simple_partitioner`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `simple_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a>~ Simple_partitioner 

 Zerstört ein `simple_partitioner`-Objekt.  
  
```
~simple_partitioner();
```  
  
##  <a name="ctor"></a>simple_partitioner 

 Erstellt ein `simple_partitioner`-Objekt.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Parameter  
 `_Chunk_size`  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
