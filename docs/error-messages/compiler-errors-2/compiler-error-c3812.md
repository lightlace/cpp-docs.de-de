---
title: "Compilerfehler C3812 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3812"
ms.assetid: 326ac706-9a5f-4851-b9d2-b90c64c75532
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\_\_property" muss das erste Token in einer Eigenschaftendeklaration sein  
  
 Bei der Deklaration einer Eigenschaft muss das Schlüsselwort [\_\_property](../../misc/property.md) das erste Token in der Zeile sein.  
  
 C3812 ist nur mit **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3812 generiert:  
  
```  
// C3812.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc class X {  
   static __property int get_Size() { // C3812, remove static specifier  
      return 0;  
   }  
};  
```