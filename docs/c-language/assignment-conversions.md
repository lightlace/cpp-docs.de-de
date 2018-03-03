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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94087d5e07765b1052404a4c3e51f37db2a31e3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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