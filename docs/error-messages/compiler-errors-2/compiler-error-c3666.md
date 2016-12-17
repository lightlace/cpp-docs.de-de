---
title: "Compilerfehler C3666"
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
  - "C3666"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3666"
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3666
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstruktor' : Eine Überschreibung des Spezifizierers 'Schlüsselwort' ist bei einem Konstruktor nicht zulässig  
  
 Ein Überschreibungsspezifizierer wurde bei einem Konstruktor verwendet. Dies ist nicht zulässig.  Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3666 generiert.  
  
```  
// C3666.cpp  
// compile with: /clr /c  
ref struct R {  
   R() new {}   // C3666  
   R(int i) {}   // OK  
};  
```