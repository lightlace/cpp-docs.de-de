---
title: "Compilerfehler C2004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2004"
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"defined\(id\)" erwartet  
  
 Ein Bezeichner muss in den Klammern hinter dem Präprozessorschlüsselwort angegeben werden.  
  
 Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual Visual Studio .NET 2003 auftreten: fehlende Klammer in Präprozessordirektive. Wenn die schließende Klammer in einer Präprozessordirektive fehlt, generiert der Compiler einen Fehler.  
  
## Beispiel  
 Im folgenden Beispiel wird C2004 generiert.  
  
```  
// C2004.cpp // compile with: /DDEBUG #include <stdio.h> int main() { #if defined(DEBUG   // C2004 printf_s("DEBUG defined\n"); #endif }  
```  
  
## Beispiel  
 Mögliche Lösung:  
  
```  
// C2004b.cpp // compile with: /DDEBUG #include <stdio.h> int main() { #if defined(DEBUG) printf_s("DEBUG defined\n"); #endif }  
```