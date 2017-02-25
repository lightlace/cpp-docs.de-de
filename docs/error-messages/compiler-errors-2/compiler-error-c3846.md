---
title: "Compilerfehler C3846 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3846"
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Symbol": Das Symbol kann nicht aus "Assembly2" importiert werden: "Symbol" wurde bereits aus einer anderen Assembly "Assembly1" importiert  
  
 Ein Symbol konnte nicht aus einer referenzierten Assembly importiert werden, da es zuvor bereits aus einer referenzierten Assembly importiert wurde.  
  
 Im folgenden Beispiel wird C3846 generiert:  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Kompilieren Sie anschließend folgenden Code:  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
  
 Im folgenden Beispiel wird C3846 generiert:  
  
```  
// C3846c.cpp  
// compile with: /LD /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc struct G  
{  
};  
```  
  
 Kompilieren Sie anschließend folgenden Code:  
  
```  
// C3846d.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
#using "c3846c.dll"  
#using "c3846c.obj"   // C3846  
  
int main()  
{  
}  
```