---
title: Raw_method_prefix | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_method_prefix
dev_langs:
- C++
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc80d1468d3ac33bf7506aab98945b9c2e610e51
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C++-spezifisch**  
  
 Gibt ein anderes Präfix an, um Namenskonflikte zu vermeiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>Parameter  
 `Prefix`  
 Das zu verwendende Präfix.  
  
## <a name="remarks"></a>Hinweise  
 Low-Level-Eigenschaften und Methoden verfügbar gemacht werden mit dem Namen mit einem Standardpräfix von Memberfunktionen **Raw_** um Namenskonflikte mit den allgemeinen Fehlerbehandlungs-Memberfunktionen zu vermeiden.  
  
> [!NOTE]
>  Die Auswirkungen der `raw_method_prefix` Attribut wird nicht geändert werden, durch das Vorhandensein der [Raw_interfaces_only](#_predir_raw_interfaces_only) Attribut. `raw_method_prefix` hat beim Angeben eines Präfix immer Vorrang vor `raw_interfaces_only`. Wenn beide Attribute in derselben `#import`-Anweisung verwendet werden, wird das Präfix verwendet, das vom `raw_method_prefix`-Attribut angegeben wird.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)