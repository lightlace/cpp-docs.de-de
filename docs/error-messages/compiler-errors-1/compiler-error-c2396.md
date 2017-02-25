---
title: "Compiler Error C2396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2396"
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compiler Error C2396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'your\_type::operator'type' : Die CLR\- oder benutzerdefinierte WinRT\-Konvertierungsfunktion ist ungültig.Muss die Konvertierung von oder zu ausführen: 'T^', 'T^%', 'T^&', wobei T \= 'Ihr\_Typ' ist  
  
 Eine Konvertierungsfunktion in einem Windows\-Runtime\- oder verwalteten Typ wies nicht einmal einen Parameter auf, dessen Typ dem Typ entspricht, der die Konvertierungsfunktion aufweist.  
  
 Im folgenden Beispiel wird C2396 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```