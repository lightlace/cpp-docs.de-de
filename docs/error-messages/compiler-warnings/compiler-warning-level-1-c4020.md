---
title: "Compilerwarnung (Stufe 1) C4020"
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
  - "C4020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4020"
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Zu viele übergebene Parameter  
  
 Die Anzahl der tatsächlich in einem Funktionsaufruf enthaltenen Parameter überschreitet die Anzahl der formalen Parameter im Funktionsprototyp oder in der Funktionsdefinition.  Die zusätzlich übergebenen Parameter werden entsprechend der für die Funktion geltenden Aufrufkonventionen vom Compiler übergeben.  
  
 Im folgenden Beispiel wird C4020 generiert:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```