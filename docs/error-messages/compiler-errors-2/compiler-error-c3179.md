---
title: "Compilerfehler C3179"
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
  - "C3179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3179"
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein unbenannter verwalteter oder WinRT\-Typ ist nicht zulässig.  
  
 Alle CLR\- und WinRT\-Klassen und \-Strukturen müssen Namen haben.  
  
 Im folgenden Beispiel wird C3179 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  
  
 Im folgenden Beispiel wird C3179 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3179b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
typedef __value struct {   // C3179  
// try the following line instead  
// typedef __value struct MyStruct {  
   int i;  
} V;  
```