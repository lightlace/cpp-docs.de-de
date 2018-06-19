---
title: Rename_namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51114787dde2f858a8409538083282ef292d599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839390"
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