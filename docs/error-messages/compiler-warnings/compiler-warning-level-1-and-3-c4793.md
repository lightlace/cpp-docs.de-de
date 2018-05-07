---
title: Compilerwarnung (Stufe 1 und 3) C4793 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56b60a028f3fa1a847d4242c0768f8082d6a686e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Compilerwarnung (Stufe 1 und 3) C4793
'Funktion': Funktion wird als systemeigener Code kompiliert: 'Grund'  
  
 Der Compiler kann nicht kompiliert werden *Funktion* in verwaltetem Code, obwohl die ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption angegeben ist. Stattdessen der Compiler ausgibt, Warnung C4793 und erläuternden Fortsetzung Nachricht und wird dann kompiliert *Funktion* in systemeigenen Code. Die Fortsetzung Nachricht enthält die *Grund* Text, der erläutert, warum *Funktion* kann nicht kompiliert werden, um `MSIL`.  
  
 Dies ist eine Warnung der Stufe 1, bei der Angabe der `/clr:pure` -Compileroption.  Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Die folgende Tabelle enthält alle möglichen Anhaltens Nachrichten.  
  
|Grund Nachricht|Hinweise|  
|--------------------|-------------|  
|Ausgerichtete Datentypen werden in verwaltetem Code nicht unterstützt.|Die CLR Lage sein, Daten bei Bedarf zu reservieren der unter Umständen nicht möglich, wenn die Daten mit Deklarationen, z. B. ausgerichtet ist [__m128](../../cpp/m128.md) oder [ausrichten](../../cpp/align-cpp.md).|  
|Funktionen, die verwenden "__ImageBase" werden in verwaltetem Code nicht unterstützt.|`__ImageBase` ist eine spezielle Linkersymbol, das in der Regel nur von systemeigenem Code auf niedriger Ebene verwendet wird, eine DLL geladen.|  
|VarArgs werden nicht unterstützt, indem Sie die "/ Clr" (Compileroption)|Systemeigene Funktionen können nicht verwaltete Funktionen aufzurufen, die über [Argumentlisten variabler Länge](../../cpp/functions-with-variable-argument-lists-cpp.md) (Varargs) Schreibberechtigung Funktionen anderen Stapel Layout Anforderungen. Allerdings bei der Angabe der `/clr:pure` Compileroption, mit Variablen Argumentlisten, die Listen werden unterstützt, da die Assembly nur verwaltete Funktionen enthalten kann. Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|  
|Die 64-Bit-CLR unterstützt keine Daten, die mit dem __ptr32-Modifizierer deklariert werden.|Ein Zeiger muss die gleiche Größe wie einen systemeigenen Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Die 32-Bit-CLR unterstützt keine Daten, die mit dem __ptr64-Modifizierer deklariert werden.|Ein Zeiger muss die gleiche Größe wie einen systemeigenen Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|  
|Eine oder mehrere systeminterne Funktionen werden in verwaltetem Code nicht unterstützt.|Der Name der systeminternen Funktion ist nicht verfügbar, zu dem Zeitpunkt, den die Meldung ausgegeben wird. Systeminterne Funktion, die diese Nachricht in der Regel führt dazu, dass stellt jedoch eine Low-Level Computer-Anweisung.|  
|Systemeigene Inlineassembly ("__asm") wird in verwaltetem Code nicht unterstützt.|[Inline-Assemblycode](../../assembler/inline/asm.md) darf beliebige systemeigenen Code, der verwaltet werden kann.|  
|Thunk virtuelle Funktion, die nicht __clrcall muss kompiliert werden als systemeigene.|Nicht[__clrcall](../../cpp/clrcall.md) Thunk virtuelle Funktion muss eine nicht verwaltete Adresse verwendet.|  
|Eine Funktion, die mit "_setjmp" muss als systemeigene kompiliert werden|Die CLR muss Ausführung des Programms steuern können. Allerdings die [Setjmp](../../cpp/using-setjmp-longjmp.md) Funktion umgeht den normalen programmausführung speichern und Wiederherstellen von Low-Level Informationen wie z. B. Register und den Ausführungszustand.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4793 generiert.  
  
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
 Im folgenden Beispiel wird C4793 generiert.  
  
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