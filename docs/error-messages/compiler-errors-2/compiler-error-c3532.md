---
title: "Compilerfehler C3532"
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
  - "C3532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3532"
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": falsche Verwendung von "Auto"  
  
 Der angegebene Typ kann nicht mit dem `auto`\-Schlüsselwort deklariert werden.  Beispielsweise können Sie das `auto`\-Schlüsselwort nicht verwenden, um ein Array oder einen Methodenrückgabetyp zu deklarieren.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Initialisierungsausdruck einen gültigen Typ ergibt.  
  
2.  Stellen Sie sicher, dass Sie kein Array und keinen Methodenrückgabetyp deklarieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C3532 erzeugt, da das `auto`\-Schlüsselwort keinen Methodenrückgabetyp deklarieren kann.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3532 erzeugt, da das `auto`\-Schlüsselwort kein Array deklarieren kann.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)