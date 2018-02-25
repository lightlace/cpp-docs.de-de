---
title: Zeichenoperator (#@) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6521322e7a71d8e76b657fb8580157c036e881b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="charizing-operator-"></a>Zeichenoperator (#@)
**Microsoft-spezifisch**  
  
 Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden. Wenn  **#@**  steht vor einem formalen Parameter in der Definition des Makros, das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird, wenn das Makro erweitert wird. Zum Beispiel:  
  
```  
#define makechar(x)  #@x  
```  
  
 führt dazu, dass die Anweisung  
  
```  
a = makechar(b);  
```  
  
 erweitert wird auf  
  
```  
a = 'b';  
```  
  
 Das einfache Anführungszeichen kann nicht mit dem Zeichenoperator verwendet werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)