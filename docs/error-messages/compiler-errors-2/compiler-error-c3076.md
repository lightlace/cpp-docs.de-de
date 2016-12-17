---
title: "Compilerfehler C3076"
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
  - "C3076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3076"
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Instanz': Sie können keine Instanz eines Referenztyps einbetten, 'Typ', in einem systemeigenen Typ  
  
 Ein systemeigener Typ kann keine Instanz eines CLR\-Typs enthalten.  
  
 Weitere Informationen finden Sie unter [C\+\+\-Stack\-Semantik für Referenztypen](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3076 generiert.  
  
```  
// C3076.cpp  
// compile with: /clr /c  
ref struct U {};  
  
struct V {  
   U y;   // C3076  
};  
  
ref struct W {  
   U y;   // OK  
};  
```