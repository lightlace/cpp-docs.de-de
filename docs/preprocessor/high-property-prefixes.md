---
title: High_property_prefixes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f188cd833551542e636e764e76784635ae2ccf2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422765"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C++-spezifisch**  
  
Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## <a name="syntax"></a>Syntax  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Parameter  
*GetPrefix*  
Präfix für zu verwendende der `propget` Methoden.  
  
*PutPrefix*  
Präfix für zu verwendende der `propput` Methoden.  
  
*PutRefPrefix*  
Präfix für zu verwendende der `propputref` Methoden.  
  
## <a name="remarks"></a>Hinweise  
 
In der Standardeinstellung auf hoher Ebene für die Fehlerbehandlung `propget`, `propput`, und `propputref` Methoden verfügbar gemacht werden, durch die Memberfunktionen, die mit dem Namen mit Präfixen `Get`, `Put`, und `PutRef`bzw.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)