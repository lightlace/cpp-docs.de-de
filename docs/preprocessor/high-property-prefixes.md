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
ms.openlocfilehash: 2ce21958dbb928a29debe21fb7cfaed4b9036141
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541593"
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
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)