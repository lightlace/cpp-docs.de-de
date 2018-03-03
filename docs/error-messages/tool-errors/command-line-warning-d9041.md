---
title: Befehlszeilenwarnung D9041 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 307d290bb525ee879f29853c6823d5b9565aba4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9041"></a>Befehlszeilenwarnung D9041
Ungültiger Wert "Value" für "/ option"; Wenn 'Value'; Fügen Sie "/ Analyse" den Befehlszeilenoptionen, wenn Sie diese Warnung angeben.  
  
 Eine Nummer der codeanalysewarnung wurde hinzugefügt, um die **/WD**, **/we**, **/wo**, oder **/WL** -Befehlszeilenoption, ohne dass auch die **/ analyze** -Befehlszeilenoption. Um diesen Fehler zu beheben, fügen Sie entweder die **/ analyze** -Befehlszeilenoption, oder entfernen Sie die ungültige Warnungsnummer aus der entsprechenden **/w** -Befehlszeilenoption.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Befehlszeilenbeispiel wird der Warnung D9041 generiert:  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Um die Warnung zu beheben, fügen die **/ analyze** -Befehlszeilenoption. Wenn **/ analyze** wird auf Ihrer Version des Compilers nicht unterstützt, entfernen Sie die ungültige Warnungsnummer aus der **/WD** Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlszeilenfehler D8000 bis D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)