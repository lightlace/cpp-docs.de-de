---
title: Compilerfehler C2346 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2346
dev_langs: C++
helpviewer_keywords: C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 769d5addc47ead8ffb338d5fbef313cd46735d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2346"></a>Compilerfehler C2346
'Funktion' kann nicht als systemeigene kompiliert werden: Grund  
  
 Der Compiler konnte eine Funktion in MSIL kompiliert werden.  
  
 Weitere Informationen finden Sie unter [verwaltete, unverwaltete](../../preprocessor/managed-unmanaged.md) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den Code in der Funktion, die in MSIL kompiliert werden kann.  
  
2.  Führen Sie entweder nicht kompilieren Sie das Modul mit **"/ CLR"**, oder markieren Sie die Funktion als nicht verwaltet, mit dem unmanaged-Pragma.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2346 generiert.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```