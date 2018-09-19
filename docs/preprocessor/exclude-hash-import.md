---
title: Ausschließen (#import) | Microsoft-Dokumentation
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
ms.openlocfilehash: d700f19235ac18af27fa958420aa4ed467807624
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538633"
---
# <a name="exclude-import"></a>exclude (#import)
**C++-spezifisch**  
  
Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
### <a name="parameters"></a>Parameter  
*Name1*  
Erstes auszuschließendes Element.  
  
*Name2*  
Zweites auszuschließendes Element (falls erforderlich).  
  
## <a name="remarks"></a>Hinweise  
 
Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. Dieses Attribut kann eine beliebige Anzahl von Argumenten annehmen, die jeweils ein auszuschließendes Typbibliothekelement der höchsten Ebene sind.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)