---
title: "Compilerfehler C2084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2084"
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktion 'Funktion' hat bereits einen Funktionstext  
  
 Die Funktion wurde bereits definiert.  
  
 In früheren Versionen von Visual C\+\+  
  
-   akzeptierte der Compiler mehrere Vorlagenspezialisierungen, die in denselben tatsächlichen Typ aufgelöst wurden, obwohl die zusätzlichen Definitionen zu keinem Zeitpunkt verfügbar waren.  Diese mehrfachen Definitionen werden nun vom Compiler erkannt.  
  
-   \_\_int32 und int wurden als separate Typen behandelt.  Der Compiler behandelt \_\_int32 jetzt als Synonym zu int.  Dies bedeutet, dass der Compiler mehrfache Definitionen erkennt, wenn eine Funktion sowohl für \_\_int32 als auch für int überladen wird, und einen Fehler ausgibt.  
  
 Im folgenden Beispiel wird C2084 generiert:  
  
```  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
 Mögliche Lösung:  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```