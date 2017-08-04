---
title: Zuweisungskonvertierungen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 44b9b5ede24d3b6e44813de46e7507f5d943a78f
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="assignment-conversions"></a>Zuweisungskonvertierungen
Bei Zuweisungsvorgängen wird der Typ des zugewiesenen Werts in den Typ der Variablen konvertiert, die die Zuweisung empfängt. C lässt Konvertierungen durch Zuweisung zwischen Ganzzahl- und Gleitkommatypen zu, auch wenn Informationen in der Konvertierung verloren gehen. Die verwendete Konvertierungsmethode hängt von den Typen ab, die an der Zuweisung beteiligt sind, wie unter [Übliche arithmetische Konvertierungen](../c-language/usual-arithmetic-conversions.md) und in den folgenden Abschnitten beschrieben:  
  
-   [Konvertierungen von ganzzahligen Typen mit Vorzeichen](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Konvertierungen von ganzzahligen Typen ohne Vorzeichen](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Konvertierungen von Gleitkommatypen](../c-language/conversions-from-floating-point-types.md)  
  
-   [Konvertierungen in und aus Zeigertypen](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Konvertierungen von anderen Typen](../c-language/conversions-from-other-types.md)  
  
 Typqualifizierer wirken sich nicht auf die Zulässigkeit der Konvertierung aus, obwohl der I-Wert **const** nicht auf der linken Seite der Zuweisung verwendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Typkonvertierungen](../c-language/type-conversions-c.md)
