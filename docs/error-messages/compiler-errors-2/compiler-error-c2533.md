---
title: "Compilerfehler C2533 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2533"
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Ergebnistyp für Konstruktoren nicht zulässig  
  
 Ein Konstruktor kann keinen Rückgabetyp haben \(auch keinen `void`\-Rückgabetyp\).  
  
 Eine häufige Ursache für diesen Fehler ist ein fehlendes Semikolon zwischen dem Ende einer Klassendefinition und der ersten Konstruktorimplementierung.  Der Compiler erkennt die Klasse als Definition des Rückgabetyps für die Konstruktorfunktion und generiert C2533.  
  
 Im folgenden Beispiel wird C2533 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```