---
title: Raw_method_prefix | Microsoft Docs
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
ms.openlocfilehash: 236c9042393e4ff3de57bea83ad566c8b74d5d3b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839919"
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