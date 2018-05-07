---
title: Compilerfehler C2346 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9459d7330738180e92776e93fcba9a07bfd39640
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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