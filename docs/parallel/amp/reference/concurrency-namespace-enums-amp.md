---
title: Concurrency-Namespace Enumerationen (EVA) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9555023e01cb765ca943fcaaf785cdc2b4e2d0d
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency-Namespace Enumerationen (AMP)
|||  
|-|-|  
|[Access_type-Enumeration](#access_type)|[Queuing_mode-Enumeration](#queuing_mode)|  
  
##  <a name="a-nameaccesstypea--accesstype-enumeration"></a><a name="access_type"></a>Access_type-Enumeration  
 Enumerationstyp wurde verwendet, um die verschiedenen Datenzugriffstypen anzugeben.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`access_type_auto`|Wählen Sie automatisch das beste `access_type`-Objekt für die Zugriffstaste aus.|  
|`access_type_none`|Dediziert. Auf die Speicherbelegung kann nur auf der Zugriffstaste und nicht auf der CPU zugegriffen werden.|  
|`access_type_read`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU lesbar.|  
|`access_type_read_write`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU schreibbar.|  
|`access_type_write`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU les- und schreibbar.|  

  
##  <a name="a-namequeuingmodea--queuingmode-enumeration"></a><a name="queuing_mode"></a>Queuing_mode-Enumeration  
 Gibt die Modi für das Hinzufügen zur Warteschlange an, die auf dem Beschleuniger unterstützt werden.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`queuing_mode_immediate`|Ein queuingmodus, der angibt, dass jede Befehle, z. B. [Parallel_for_each-Funktion (C++-AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), werden an das entsprechende zugriffstastengerät gesendet, sobald sie an den Aufrufer zurückgegeben.|  
|`queuing_mode_automatic`|Ein queuingmodus, der angibt, dass Befehle in einer Befehlswarteschlange in die Warteschlange gestellt werden, das entspricht, der [Accelerator_view](accelerator-view-class.md) Objekt. Befehle an das Gerät gesendet werden beim [accelerator_view:: Flush](accelerator-view-class.md#flush) aufgerufen wird.|   
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

