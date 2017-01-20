---
title: "Compilerfehler C2534"
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
  - "C2534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2534"
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Konstruktor kann keinen Wert zurückgeben  
  
 Ein Konstruktor kann keinen Wert zurückgeben bzw. keinen Rückgabetyp aufweisen \(auch nicht den Rückgabetyp `void`\).  
  
 Dieser Fehler kann ggf. durch Entfernen der `return`\-Anweisung aus der Konstruktordefinition behoben werden.  
  
 Im folgenden Beispiel wird C2534 generiert:  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```