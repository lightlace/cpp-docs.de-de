---
title: Zeichenoperator (#@) | Microsoft-Dokumentation
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
ms.openlocfilehash: c6aa18936497f0415da331697aceb26f26345500
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539608"
---
# <a name="charizing-operator-"></a>Zeichenoperator (#@)
**Microsoft-spezifisch**  
  
Der Zeichenoperator kann nur mit Argumenten von Makros verwendet werden. Wenn `#@` steht einen formalen Parameter in der Definition des Makros ist das tatsächliche Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird, wenn das Makro erweitert wird. Zum Beispiel:  
  
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