---
title: "Compilerwarnung (Stufe 4) C4837"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4837"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4837"
ms.assetid: 9a3c7b6b-ffe4-443d-96af-43deb80d85b4
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4837
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Trigraph erkannt: "?? %c" ersetzt durch "%c"  
  
 Der erkannte Trigraph \(eine Kombination aus drei Schriftzeichen\) wird durch das angegebene Zeichen ersetzt.  
  
 Der Compiler übersetzt Trigraphen, bevor sonstige Verarbeitungsschritte abgeschlossen werden.  Verwenden Sie die Escapesequenz für Zeichen, `\?`, um die Fehlinterpretation von Zeichenfolgen zu verhindern, die einem Trigraphen ähneln.  Weitere Informationen zu Trigraphen finden Sie unter [Trigraphen](../../c-language/trigraphs.md).  Weitere Informationen zu Escapesequenzen finden Sie unter [Escapesequenzen](../../c-language/escape-sequences.md).  
  
 C4837 ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie im Quellcode anstelle eines der '?'\-Zeichen die Escapesequenz für Zeichen, `\?`.  
  
## Siehe auch  
 [Trigraphen](../../c-language/trigraphs.md)   
 [Escapesequenzen](../../c-language/escape-sequences.md)   
 [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md)