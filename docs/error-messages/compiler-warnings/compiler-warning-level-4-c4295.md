---
title: "Compilerwarnung (Stufe 4) C4295"
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
  - "C4295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4295"
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***array* ': das Array ist zu klein, um ein abschließendes NULL\-Zeichen einzuschließen**  
  
 Ein Array wurde initialisiert, das letzte Zeichen im Array ist jedoch nicht NULL; beim Zugriff auf das Array kann ein unerwartetes Verhalten auftreten.  
  
 Im folgenden Beispiel wird C4295 generiert:  
  
```  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```