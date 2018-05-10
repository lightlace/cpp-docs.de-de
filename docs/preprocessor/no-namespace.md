---
title: No_namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d4558b0fd6a4014bc9601d5260882af444f87e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="nonamespace"></a>no_namespace
**C++-spezifisch**  
  
 Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Inhalt der Typbibliothek in der `#import`-Headerdatei wird normalerweise in einem Namespace definiert. Der Name des Namespaces wird angegeben, der **Bibliothek** -Anweisung der ursprünglichen IDL-Datei. Wenn das `no_namespace`-Attribut angegeben ist, wird dieser Namespace nicht vom Compiler generiert.  
  
 Wenn Sie einen anderen Namespace-Namen verwenden möchten, verwenden Sie die [Rename_namespace](../preprocessor/rename-namespace.md) Attribut.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)