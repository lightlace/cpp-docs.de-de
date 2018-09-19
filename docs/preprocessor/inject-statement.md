---
title: Inject_statement | Microsoft-Dokumentation
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
ms.openlocfilehash: eb4142b742ae6c2a758c2a2fb5e09c604959433f
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42543129"
---
# <a name="injectstatement"></a>inject_statement
**C++-spezifisch**  
  
Fügt das Argument als Quelltext in den Header der Typbibliothek ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
inject_statement("source_text")  
```  
  
### <a name="parameters"></a>Parameter  
*source_text*  
In die Headerdatei der Typbibliothek einzufügender Quelltext.  
  
## <a name="remarks"></a>Hinweise  
 
Der Text wird am Anfang der Namespacedeklaration platziert, die den Typbibliotheksinhalt in der Headerdatei umschließt.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)