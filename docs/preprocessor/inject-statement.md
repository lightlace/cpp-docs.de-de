---
title: Inject_statement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dacc2867b767495c608789b9efbe23bf7aa7110
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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