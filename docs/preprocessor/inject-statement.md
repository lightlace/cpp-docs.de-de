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
ms.openlocfilehash: bb3bdc2b4e00cd9e2167adeb0ad7d3023af9eb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384207"
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
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)