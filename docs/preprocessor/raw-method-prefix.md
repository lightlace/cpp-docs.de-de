---
title: Raw_method_prefix | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb9178bc315385bab97cea473430745ad66d973
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539214"
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C++-spezifisch**  
  
Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_method_prefix("Prefix")  
```  
  
### <a name="parameters"></a>Parameter  
*Prefix*  
Das zu verwendende Präfix.  
  
## <a name="remarks"></a>Hinweise  
 
Low-Level-Eigenschaften und Methoden sind verfügbar, durch die Memberfunktionen, die mit dem Namen, mit dem Standardpräfix **Raw_** so Namenskonflikte mit den allgemeinen Fehlerbehandlung Memberfunktionen zu vermeiden.  
  
> [!NOTE]
> Die Auswirkungen der **Raw_method_prefix** Attribut wird nicht geändert werden, durch das Vorhandensein der [Raw_interfaces_only](#_predir_raw_interfaces_only) Attribut. Die **Raw_method_prefix** immer Vorrang `raw_interfaces_only` beim Angeben eines Präfix. Wenn beide Attribute, in der gleichen verwendet werden `#import` -Anweisung, und klicken Sie dann auf das Präfix, das gemäß der **Raw_method_prefix** Attribut wird verwendet.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)