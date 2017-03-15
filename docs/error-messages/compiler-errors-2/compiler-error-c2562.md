---
title: "Compilerfehler C2562 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2562"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2562"
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2562
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': 'void'\-Funktion gibt einen Wert zurück  
  
 Die Funktion ist zwar als `void` deklariert, gibt aber einen Wert zurück.  
  
 Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden.  
  
 Dieser Fehler wird möglicherweise behoben, wenn Sie den Rückgabetyp in der Funktionsdeklaration angeben.  
  
 Im folgenden Beispiel wird C2562 generiert:  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```