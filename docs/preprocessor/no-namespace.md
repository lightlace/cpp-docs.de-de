---
title: No_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6528ce33689dc05fa037bdd6bc110e5e6a0de9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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