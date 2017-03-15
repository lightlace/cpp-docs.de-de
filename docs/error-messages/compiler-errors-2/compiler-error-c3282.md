---
title: "Compiler Error C3282 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3282"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3282"
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compiler Error C3282
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generische Parameterlisten können nur in verwalteten oder WinRT\-Klassen, \-Strukturen oder \-Funktionen vorkommen.  
  
 Eine generische Parameterliste wurde falsch verwendet.  Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3282 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C3282.cpp  
// compile with: /clr /c  
generic <typename T> int x;   // C3282  
  
ref struct GC0 {  
   generic <typename T> int x;   // C3282  
};  
  
// OK  
generic <typename T>  
ref class M {};  
```