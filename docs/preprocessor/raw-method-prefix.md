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
ms.openlocfilehash: fc2a37f587d3b5ac2b695171f5620db6521693d2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439678"
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
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)