---
title: High_property_prefixes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- high_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7df4ef6cded98c19ead86160aa772e349ebfd37
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C++-spezifisch**  
  
 Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## <a name="syntax"></a>Syntax  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Parameter  
 `GetPrefix`  
 Präfix für die **Propget** Methoden.  
  
 `PutPrefix`  
 Präfix für die **Propput** Methoden.  
  
 `PutRefPrefix`  
 Präfix für die **Propputref** Methoden.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig Fehlerbehandlung **Propget**, **Propput**, und **Propputref** Methoden mit dem Namen mit Präfixen Memberfunktionen verfügbar gemacht werden **abrufen** , `Put`, und **PutRef**zugeordnet.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)