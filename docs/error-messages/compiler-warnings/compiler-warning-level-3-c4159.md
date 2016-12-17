---
title: "Compilerwarnung (Stufe 3) C4159"
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
  - "C4159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4159"
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pragma\(pop,...\) : Hat den zuvor mit push abgelegten Bezeichner 'Bezeichner' per pop ausgelesen  
  
 Der Quellcode enthält eine **push**\-Anweisung mit einem Bezeichner für ein Pragma, gefolgt von einer **pop**\-Anweisung ohne Bezeichner.  Daher wird ***Bezeichner*** per pop ausgelesen, und nachfolgende Verwendungen von ***Bezeichner*** können ein unerwartetes Verhalten zeigen.  
  
 Um diese Warnung zu vermeiden, geben Sie in der **pop**\-Anweisung einen Bezeichner an.  Beispiel:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```