---
title: "Compilerfehler C3195 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3195"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3195"
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3195
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator" : ist reserviert und kann nicht als Member einer Verweisklasse oder eines Werttyps verwendet werden.CLR\- oder WinRT\-Operatoren müssen mit dem Schlüsselwort "operator" definiert werden.  
  
 Der Compiler hat eine Operatordefinition gefunden, in der die Managed Extensions for C\+\+\-Syntax verwendet wird.  
  
 Verwenden Sie entweder die neue C\+\+\-Syntax, oder verwenden Sie die **\/clr:oldSyntax**\-Compileroption, um die Managed Extensions for C\+\+\-Syntax zu erlauben.  
  
 Im folgenden Beispiel wird C3195 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```