---
title: Inject_statement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 115f5b3d7012ae3e9073d81e0c1005dcb513e045
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849339"
---
# <a name="injectstatement"></a>inject_statement
**C++-spezifisch**  
  
 Fügt das Argument als Quelltext in den Header der Typbibliothek ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>Parameter  
 `source_text`  
 In die Headerdatei der Typbibliothek einzufügender Quelltext.  
  
## <a name="remarks"></a>Hinweise  
 Der Text wird am Anfang der Namespacedeklaration platziert, die den Typbibliotheksinhalt in der Headerdatei umschließt.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)