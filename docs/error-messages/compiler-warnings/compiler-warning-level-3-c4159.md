---
title: "Compilerwarnung (Stufe 3) C4159 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4159"
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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