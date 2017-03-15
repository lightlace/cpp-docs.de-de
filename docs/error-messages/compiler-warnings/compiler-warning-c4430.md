---
title: "Compilerwarnung C4430 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4430"
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung C4430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlender Typspezifizierer \- int wird angenommen.Hinweis: default\-int wird von C\+\+ nicht unterstützt  
  
 Dieser Fehler kann aus einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 resultieren: Alle Deklarationen müssen eine explizite Typangabe enthalten, da "int" nicht mehr als Standardtyp angenommen wird.  
  
 C4430 wird immer als Fehler ausgegeben.  Sie können diese Warnung mit `#pragma warning` oder **\/wd** deaktivieren. Weitere Informationen finden Sie unter [warning](../../preprocessor/warning.md) oder [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Warnstufe\)](../../build/reference/compiler-option-warning-level.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4430 generiert.  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```