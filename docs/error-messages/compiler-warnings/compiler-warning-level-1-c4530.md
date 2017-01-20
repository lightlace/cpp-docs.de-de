---
title: "Compilerwarnung (Stufe 1) C4530"
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
  - "C4530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4530"
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Ausnahmehandler verwendet, aber Entladesemantik ist nicht aktiviert.Geben Sie \/EHsc an  
  
 Die C\+\+\-Ausnahmebehandlung wurde verwendet, ohne dass [\/EHsc](../../build/reference/eh-exception-handling-model.md) aktiviert war.  
  
 Wenn die **\/EHsc**\-Option nicht aktiviert ist, wird ein Objekt mit automatischer Speicherung im Rahmen zwischen der Funktion, die das `throw` ausführt, und der Funktion, die das `throw` auffängt, nicht gelöscht.  Ein Objekt, das mit automatischer Speicherung in einem **try**\-Block oder **catch**\-Block erstellt wurde, wird jedoch gelöscht.  
  
 Im folgenden Beispiel wird C4530 generiert:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Kompilieren Sie das Beispiel mit \/EHsc, um die Warnung zu vermeiden.