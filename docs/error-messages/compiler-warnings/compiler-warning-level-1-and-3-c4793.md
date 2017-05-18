---
title: Compilerwarnung (Stufe 1 und 3) C4793 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4793
dev_langs:
- C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: a217d2074affa1598aef93882fb299c6fcdef5a6
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Compilerwarnung (Stufe 1 und 3) C4793
'Funktion': Funktion wird als systemeigener Code kompiliert: 'Grund'  
  
 Der Compiler kann nicht kompiliert werden *Funktion* in verwalteten Code, obwohl die [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption angegeben wird. Stattdessen der Compiler gibt Warnung C4793 und eine Nachricht erläuternden Fortsetzung und kompiliert dann *Funktion* in systemeigenen Code. Die Fortsetzung-Nachricht enthält die *Grund* Erklärung, warum *Funktion* kann nicht kompiliert werden, um `MSIL`.  
  
 Dies ist eine Warnung der Stufe 1, bei der Angabe der `/clr:pure` (Compileroption).  Die **/CLR: pure** -Compileroption in Visual Studio 2015 veraltet ist.  
  
 Die folgende Tabelle listet alle möglichen Anhaltens Nachrichten.  
  
|Meldung mit Grund|Hinweise|  
|--------------------|-------------|  
|Ausgerichtete Datentypen werden in verwaltetem Code nicht unterstützt.|Die CLR muss Daten zuordnen, bei Bedarf können die unter Umständen nicht möglich, wenn die Daten mit Deklarationen, wie z. B. ausgerichtet ist [__m128](../../cpp/m128.md) oder [ausrichten](../../cpp/align-cpp.md).|  
|Funktionen, die mithilfe von "__ImageBase" werden in verwaltetem Code nicht unterstützt.|`__ImageBase`ist ein spezieller Linkersymbol, das in der Regel nur von systemeigenem Code auf niedriger Ebene zum Laden einer DLL verwendet wird.|  
|VarArgs werden nicht unterstützt, durch die "/ Clr" (Compileroption)|Systemeigene Funktionen können nicht verwaltete Funktionen aufrufen, [Variablenargumentlisten](../../cpp/functions-with-variable-argument-lists-cpp.md) (Varargs), da die Funktionen anderen Stapel layoutanforderungen haben. Jedoch die Angabe der `/clr:pure` -Compileroption Variablenargumentlisten unterstützt, da die Assembly nur verwaltete Funktionen enthalten kann. Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|  
|Daten, die mit dem Modifizierer __ptr32 deklariert unterstützt die 64-Bit-CLR nicht.|Ein Zeiger muss die gleiche Größe wie ein systemeigener Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Daten, die mit dem Modifizierer __ptr64 deklariert unterstützt die 32-Bit-CLR nicht.|Ein Zeiger muss die gleiche Größe wie ein systemeigener Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Eine oder mehrere systeminterne Funktionen werden in verwaltetem Code nicht unterstützt.|Der Name der systeminternen Funktion ist zum Zeitpunkt, den Ausgabe der Meldung, nicht verfügbar. Systeminterne Funktion, die diese Nachricht in der Regel verursacht jedoch stellt eine Maschine Low-Level-Anweisung.|  
|Systemeigene Inlineassemblys ('__asm') ist in verwaltetem Code nicht unterstützt.|[Inline-Assemblycode](../../assembler/inline/asm.md) darf beliebige systemeigenen Code, der verwaltet werden kann.|  
|Thunk virtuelle Funktion, die nicht __clrcall muss als systemeigen kompiliert werden.|Nicht[__clrcall](../../cpp/clrcall.md) virtuelle Funktionsthunk muss eine nicht verwaltete Adresse verwenden.|  
|Eine Funktion mithilfe von "_setjmp" muss als systemeigen kompiliert werden|Die CLR muss Ausführung des Programms steuern können. Allerdings die [Setjmp](../../cpp/using-setjmp-longjmp.md) Funktion umgeht die regelmäßige Ausführung von speichern und Wiederherstellen von Low-Level-Informationen, z. B. Register und Ausführungsstatus.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4793 generiert.  
  
```  
// C4793.cpp  
// compile with: /c /clr /W3   
// processor: x86  
int asmfunc(void) {   // C4793, compiled as unmanaged, native code  
   __asm {  
      mov eax, 0  
   }  
}  
```  
  
```Output  
warning C4793: 'asmfunc' : function is compiled as native code:  
        Inline native assembly ('__asm') is not supported in managed code  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4793 generiert.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
```Output  
warning C4793: 'f' : function is compiled as native code:  
        A function using '_setjmp' must be compiled as native  
```
