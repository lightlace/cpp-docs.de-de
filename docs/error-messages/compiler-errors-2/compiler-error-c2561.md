---
title: "Compilerfehler C2561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2561"
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Funktion muss einen Wert zurückgeben  
  
 Die Funktion wurde mit Rückgabetyp deklariert, die Funktionsdefinition enthält jedoch keine `return`\-Anweisung.  
  
 Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden:  
  
1.  Wenn die Funktion keinen Wert zurückgibt, muss sie mit dem Rückgabetyp [void](../../cpp/void-cpp.md) deklariert werden.  
  
2.  Stellen Sie sicher, dass alle möglichen Ebenen der Funktion einen Wert zurückgeben, dessen Typ mit dem im Prototyp deklarierten Typ übereinstimmt.  
  
3.  C\+\+\-Funktionen mit Inlineassemblerroutinen, in denen der Rückgabewert im `AX`\-Register gespeichert wird, erfordern möglicherweise eine `return`\-Anweisung.  Kopieren Sie den in `AX` enthaltenen Wert in eine temporäre Variable, und lassen Sie diese Variable von der Funktion zurückgeben.  
  
 Im folgenden Beispiel wird C2561 generiert:  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```