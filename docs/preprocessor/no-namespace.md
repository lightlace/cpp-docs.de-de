---
title: No_namespace | Microsoft-Dokumentation
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
ms.openlocfilehash: a02919e1e96717c1accc6343ecff32a66968cbcc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378816"
---
# <a name="nonamespace"></a>no_namespace
**C++-spezifisch**  
  
Gibt an, dass der Name des Namespaces nicht vom Compiler generiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>Hinweise  
 
Der Inhalt der Typbibliothek in der `#import`-Headerdatei wird normalerweise in einem Namespace definiert. Der Namespacename wird angegeben, der `library` -Anweisung der ursprünglichen IDL-Datei. Wenn die **No_namespace** -Attribut angegeben ist, wird dieser Namespace wird nicht vom Compiler generiert.  
  
Wenn Sie einen anderen Namespacenamen verwenden möchten, verwenden Sie die [Rename_namespace](../preprocessor/rename-namespace.md) Attribut.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)