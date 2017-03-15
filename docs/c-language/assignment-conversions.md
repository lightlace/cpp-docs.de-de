---
title: "Zuweisungskonvertierungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zuweisungskonvertierungen"
  - "Konvertierungen, Zuweisung"
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Zuweisungskonvertierungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Zuweisungsvorgängen wird der Typ des zugewiesenen Werts in den Typ der Variablen konvertiert, die die Zuweisung empfängt.  C lässt Konvertierungen durch Zuweisung zwischen Ganzzahl\- und Gleitkommatypen zu, auch wenn Informationen in der Konvertierung verloren gehen.  Die verwendete Konvertierungsmethode hängt von den Typen ab, die an der Zuweisung beteiligt sind, wie unter [Übliche arithmetische Konvertierungen](../c-language/usual-arithmetic-conversions.md) und in den folgenden Abschnitten beschrieben:  
  
-   [Konvertierungen von ganzzahligen Typen mit Vorzeichen](../c-language/conversions-from-signed-integral-types.md)  
  
-   [Konvertierungen von ganzzahligen Typen ohne Vorzeichen](../c-language/conversions-from-unsigned-integral-types.md)  
  
-   [Konvertierungen von Gleitkommatypen](../c-language/conversions-from-floating-point-types.md)  
  
-   [Konvertierungen in und aus Zeigertypen](../c-language/conversions-to-and-from-pointer-types.md)  
  
-   [Konvertierungen von anderen Typen](../c-language/conversions-from-other-types.md)  
  
 Typqualifizierer wirken sich nicht auf die Zulässigkeit der Konvertierung aus, obwohl der I\-Wert **const** nicht auf der linken Seite der Zuweisung verwendet werden kann.  
  
## Siehe auch  
 [Typkonvertierungen](../c-language/type-conversions-c.md)