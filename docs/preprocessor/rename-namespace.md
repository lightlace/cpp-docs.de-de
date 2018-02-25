---
title: Rename_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="renamenamespace"></a>rename_namespace
**C++-spezifisch**  
  
 Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.  
  
## <a name="syntax"></a>Syntax  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>Parameter  
 `NewName`  
 Der neue Name des neuen Namespace.  
  
## <a name="remarks"></a>Hinweise  
 Es akzeptiert ein einzelnes Argument *NewName*, die den neuen Namen für den Namespace angibt.  
  
 Verwenden Sie zum Entfernen des Namespaces der [No_namespace](../preprocessor/no-namespace.md) Attribut.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)