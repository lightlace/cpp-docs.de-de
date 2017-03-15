---
title: "Compilerwarnung (Stufen 1 und 4) C4112 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4112"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4112"
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufen 1 und 4) C4112
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line erfordert eine Ganzzahl zwischen 1 und Zahl  
  
 Die [\#line](../../preprocessor/hash-line-directive-c-cpp.md)\-Direktive gibt einen ganzzahligen Parameter an, der außerhalb des zulässigen Bereichs liegt.  
  
 Wenn der angegebene Parameter kleiner als 1 ist, wird der Zeilenzähler auf 1 zurückgesetzt. Wenn der angegebene Parameter größer als *Anzahl* ist, der vom Compiler definierte Grenzwert, bleibt der Zeilenzähler unverändert. Dies ist eine Warnung der Stufe 1 unter ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) und eine Warnung der Stufe 4 gemäß Microsoft\-Extensions \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
 Im folgenden Beispiel wird C4112 generiert:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```