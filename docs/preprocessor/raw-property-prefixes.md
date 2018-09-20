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
ms.openlocfilehash: 3ae69e26077692188b8e013e949592df26d7701a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420399"
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
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)