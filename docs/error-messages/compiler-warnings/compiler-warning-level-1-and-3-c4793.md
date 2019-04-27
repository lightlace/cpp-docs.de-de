---
title: Compilerwarnung (Stufe 1 und 3) C4793
ms.date: 11/04/2016
f1_keywords:
- C4793
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
ms.openlocfilehash: e7ca3b10e09b0d6818fbc7f5607ebc9c95c7f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280541"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Compilerwarnung (Stufe 1 und 3) C4793

> "*Funktion*': Funktion als systemeigener Code kompiliert wird:"*Grund*"

## <a name="remarks"></a>Hinweise

Der Compiler kann nicht kompiliert werden *Funktion* in verwaltetem Code, obwohl die ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) -Compileroption angegeben ist. Stattdessen der Compiler gibt Warnung C4793 und eine Nachricht erläuternde Fortsetzung aus, und klicken Sie dann kompiliert *Funktion* in systemeigenen Code. Die Fortsetzung-Nachricht enthält die *Grund* Text, die erklärt, warum *Funktion* kann nicht kompiliert werden, um `MSIL`.

Dies ist eine Warnung der Stufe 1, wenn Sie angeben, die **/CLR: pure** -Compileroption.  Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Die folgende Tabelle enthält alle möglichen Anhaltens Nachrichten.

|Grund-Nachricht|Hinweise|
|--------------------|-------------|
|Ausgerichtete Datentypen werden in verwaltetem Code nicht unterstützt.|Die CLR Lage sein, Daten bei Bedarf zuzuordnen, die eventuell nicht möglich, wenn die Daten mit Deklarationen, z. B. ausgerichtet ist [__m128](../../cpp/m128.md) oder [ausrichten](../../cpp/align-cpp.md).|
|Funktionen, mit denen "__ImageBase" werden in verwaltetem Code nicht unterstützt.|`__ImageBase` ist ein spezieller Linkersymbol, das in der Regel nur von systemeigenen Code auf niedriger Ebene verwendet wird, um eine DLL zu laden.|
|VarArgs werden nicht unterstützt, indem Sie die "/ Clr" (Compileroption)|Native Funktionen können nicht verwaltete Funktionen aufrufen [Variablenargumentlisten](../../cpp/functions-with-variable-argument-lists-cpp.md) (Varargs), da die Funktionen auf anderen Stapel layoutanforderungen haben. Jedoch bei Angabe der **/CLR: pure** Compileroption Variablenargument unterstützt, da die Assembly nur verwaltete Funktionen enthalten kann. Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|
|Daten, die mit dem __ptr32-Modifizierer deklariert wird von die 64-Bit-CLR nicht unterstützt.|Ein Zeiger, muss die gleiche Größe wie einen systemeigenen Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|Daten, die mit dem __ptr64-Modifizierer deklariert wird von die 32-Bit-CLR nicht unterstützt.|Ein Zeiger, muss die gleiche Größe wie einen systemeigenen Zeiger auf die aktuelle Plattform. Weitere Informationen finden Sie unter [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|Eine oder mehrere systeminterne Funktionen werden in verwaltetem Code nicht unterstützt.|Der Name der die systeminterne Funktion ist nicht verfügbar, zu dem Zeitpunkt, der die Meldung ausgegeben wird. Jedoch stellt eine systeminterne Funktion, die diese Nachricht in der Regel führt dazu, dass eine Low-Level-computeranweisung.|
|Systemeigene Inlineassemblys ("__asm") wird in verwaltetem Code nicht unterstützt.|[Inline-Assemblycode](../../assembler/inline/asm.md) darf beliebige, systemeigenen Code, der nicht verwaltet werden kann.|
|Ein Thunk der __clrcall-nicht virtuelle Funktion muss als systemeigen kompiliert werden.|Nicht[__clrcall](../../cpp/clrcall.md) virtuelle Funktionsthunk muss eine nicht verwaltete Adresse verwendet.|
|Eine Funktion mit "_setjmp" muss als systemeigen kompiliert werden|Die CLR muss Ausführung des Programms steuern können. Allerdings die [Setjmp](../../cpp/using-setjmp-longjmp.md) Funktion umgeht die normale programmausführung speichern und Wiederherstellen von Low-Level-Informationen wie z. B.-Register und Ausführungsstatus.|

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4793 generiert.

```cpp
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

Im folgende Beispiel wird die C4793 generiert.

```cpp
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