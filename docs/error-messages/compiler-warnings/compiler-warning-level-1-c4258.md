---
title: "Compilerwarnung (Stufe 1) C4258"
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
  - "C4258"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4258"
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4258
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Die Definition in der for\-Schleife wurde ignoriert. Es wurde die Definition des übergeordneten Gültigkeitsbereichs verwendet  
  
 Gemäß [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) und [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) verlassen in einer [for](../../cpp/for-statement-cpp.md)\-Schleife definierte Variablen den Gültigkeitsbereich, nachdem die **for**\-Schleife beendet wurde.  Diese Warnung wird ausgegeben, wenn eine Variable, die denselben Namen wie die Schleifenvariable hat, jedoch in der übergeordneten Schleife definiert ist, erneut im Gültigkeitsbereich verwendet wird, in dem die **for**\-Schleife enthalten ist.  Beispiel:  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```