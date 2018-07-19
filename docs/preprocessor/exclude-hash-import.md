---
title: Ausschließen (#import) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cbc9d6f5ae0dcb1f82264ff07d3ea93a71cab60
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33954127"
---
# <a name="exclude-import"></a>exclude (#import)
**C++-spezifisch**  
  
 Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### <a name="parameters"></a>Parameter  
 `Name1`  
 Erstes auszuschließendes Element.  
  
 `Name2`  
 Zweites auszuschließendes Element (falls erforderlich).  
  
## <a name="remarks"></a>Hinweise  
 Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. Dieses Attribut kann eine beliebige Anzahl von Argumenten annehmen, die jeweils ein auszuschließendes Typbibliothekelement der höchsten Ebene sind.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)