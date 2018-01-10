---
title: '&lt;atomic&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: "11"
helpviewer_keywords: std::memory_order
manager: ghogen
ms.openlocfilehash: 4d0c60a908d795d8bf9fa7643471c6c9f29cc1cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltatomicgt-enums"></a>&lt;atomic&gt;-Enumerationen
  
##  <a name="memory_order_enum"></a> memory_order-Enumeration  
 Stellt symbolische Namen für Synchronisierungsvorgänge auf Speicheradressen bereit. Diese Vorgänge wirken sich auf das Sichtbarwerden der Zuweisung eines Thread in einem anderen aus.  
  
```
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```  
  
### <a name="remarks"></a>Hinweise  
  
|||  
|-|-|  
|`memory_order_relaxed`|Keine Reihenfolge erforderlich.|  
|`memory_order_consume`|Ein Ladevorgang fungiert als Nutzungsvorgang auf der Speicheradresse.|  
|`memory_order_acquire`|Ein Ladevorgang fungiert als Abrufvorgang auf der Speicheradresse.|  
|`memory_order_release`|Ein Speichervorgang fungiert als eine Befreiungsaktion auf der Speicheradresse.|  
|`memory_order_acq_rel`|Kombiniert `memory_order_acquire` und `memory_order_release`.|  
|`memory_order_seq_cst`|Kombiniert `memory_order_acquire` und `memory_order_release`. Als `memory_order_seq_cst` gekennzeichnete Speicherzugriffe müssen nacheinander konsistent sein.|  
  
## <a name="see-also"></a>Siehe auch  
 [\<atomic>](../standard-library/atomic.md)



