---
title: Zeichenoperator (#@) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9e0c0d140d937b7359ff3abf9c0eae145a89210
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912731"
---
# <a name="charizing-operator-"></a>Zeichenoperator (#@)
**Microsoft-spezifisch**  
  
 Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden. Wenn **#@** steht vor einem formalen Parameter in der Definition des Makros, das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird, wenn das Makro erweitert wird. Zum Beispiel:  
  
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