---
title: "Compilerfehler C3382"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3382"
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"sizeof" wird von \/clr:safe nicht unterstützt.  
  
 Die Ausgabedatei einer **\/clr:safe**\-Kompilierung ist eine überprüfbar typsichere Datei, und „sizeof“ wird nicht unterstützt, weil der Rückgabewert des sizeof\-Operators „size\_t“ lautet und seine Größe je nach Betriebssystem variiert.  
  
 Weitere Informationen finden Sie unter  
  
-   [sizeof\-Operator](../../cpp/sizeof-operator.md)  
  
-   [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Häufig auftretende 64\-Bit\-Migrationsprobleme bei Visual C\+\+](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Beispiel  
 Im folgenden Beispiel wird C3382 generiert:  
  
```  
// C3382.cpp // compile with: /clr:safe int main() { sizeof( char );   // C3382 }  
```