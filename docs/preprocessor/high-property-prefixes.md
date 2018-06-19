---
title: High_property_prefixes | Microsoft Docs
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
ms.openlocfilehash: 7269301fed3892fbf4b7cf6427bacb82d9712ef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849388"
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