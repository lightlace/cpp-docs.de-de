---
title: '&lt;atomic&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 
helpviewer_keywords:
- std::memory_order
manager: ghogen
ms.openlocfilehash: 5f5c286375699d233d1bc9dadd3f44992309fa0a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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



