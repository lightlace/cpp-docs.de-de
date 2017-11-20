---
title: Compilerfehler Warnung (Stufe 1) C4731 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4731
dev_langs: C++
helpviewer_keywords: C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bfddf524678da34d514c32bfe86b98b32e87d195
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4731"></a>Compilerwarnung (Stufe 1) C4731
"Zeiger": Framezeigerregister "registrieren" von Inline-Assemblycode geändert  
  
 Ein Framezeigerregister wurde geändert. Sie speichern und Wiederherstellen der Register in Ihre Inline Assembly Block oder der Zielframe, Variablen (lokales oder Parameter, abhängig von der geänderten Register) müssen, oder Code möglicherweise nicht ordnungsgemäß ausgeführt.  
  
 Im folgenden Beispiel wird C4731 generiert:  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP ist der Framezeiger (FPO ist nicht zulässig), und es geändert wird. Wenn `p` liegt, auf die verwiesen wird, verweist auf relativ zum `EBP`. Aber `EBP` wurde durch den Code überschrieben wurde, sodass das Programm nicht ordnungsgemäß funktioniert und kann sogar einen Fehler.