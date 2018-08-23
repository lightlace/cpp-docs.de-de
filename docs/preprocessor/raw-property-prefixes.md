---
title: Raw_property_prefixes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 423a66b698f4e421ff29e6ac3dfddd11fa11c58f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541585"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C++-spezifisch**  
  
Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
### <a name="parameters"></a>Parameter  
*GetPrefix*  
Präfix für zu verwendende der `propget` Methoden.  
  
*PutPrefix*  
Präfix für zu verwendende der `propput` Methoden.  
  
*PutRefPrefix*  
Präfix für zu verwendende der `propputref` Methoden.  
  
## <a name="remarks"></a>Hinweise  
 
In der Standardeinstellung auf niedriger Ebene `propget`, `propput`, und `propputref` Methoden von Namen mit Präfixen von Memberfunktionen verfügbar gemacht werden **Get_**, **Put_**, und **Putref_** bzw. Diese Präfixe sind kompatibel mit den Namen, die in den Headerdateien verwendet werden, die von MIDL generiert werden.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)