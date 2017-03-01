---
title: Static_partitioner-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: f36b1e1dcc68d94bdebd8b7b10f4fec735ce9fb5
ms.lasthandoff: 02/24/2017

---
# <a name="staticpartitioner-class"></a>static_partitioner-Klasse
Die `static_partitioner`-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird. Mit dem Partitionierer wird der Bereich in so viele Blöcke unterteilt, wie Worker für den zugrunde liegenden Planer verfügbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Static_partitioner-Konstruktor](#ctor)|Erstellt ein `static_partitioner`-Objekt.|  
|[~ Static_partitioner-Destruktor](#dtor)|Zerstört ein `static_partitioner`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `static_partitioner`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namedtora-staticpartitioner"></a><a name="dtor"></a>~ Static_partitioner 

 Zerstört ein `static_partitioner`-Objekt.  
  
```
~static_partitioner();
```  
  
##  <a name="a-namectora-staticpartitioner"></a><a name="ctor"></a>static_partitioner 

 Erstellt ein `static_partitioner`-Objekt.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

