---
title: "Compilerwarnung (Stufe 4) C4204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4204"
ms.assetid: 298d2880-6737-448e-b711-15572d540200
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Initialisierer für zusammengesetzten Typ ist keine Konstante  
  
 Bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\) können Sie Aggregattypen \(Arrays, Strukturen, Unions und Klassen\) mit Werten initialisieren, die keine Konstanten sind.  
  
## Beispiel  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 Derartige Initialisierungen sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.