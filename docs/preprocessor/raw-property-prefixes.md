---
title: Raw_property_prefixes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_property_prefixes
dev_langs: C++
helpviewer_keywords: raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aec8daa33e5fc734168bcb3096c4111536250c68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes
**C++-spezifisch**  
  
 Gibt alternative Präfixe für drei Eigenschaftenmethoden an.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>Parameter  
 `GetPrefix`  
 Präfix für die **Propget** Methoden.  
  
 `PutPrefix`  
 Präfix für die **Propput** Methoden.  
  
 `PutRefPrefix`  
 Präfix für die **Propputref** Methoden.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig auf niedriger Ebene **Propget**, **Propput**, und **Propputref** Methoden sind Namen mit Präfixen von Memberfunktionen verfügbar **Get_**, **Put_**, und **Putref_** bzw.. Diese Präfixe sind kompatibel mit den Namen, die in den Headerdateien verwendet werden, die von MIDL generiert werden.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)