---
title: __clrcall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __clrcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4012eac44f376ccdeeb57227e562c672f6ba7ffe
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704580"
---
# <a name="clrcall"></a>__clrcall

**Microsoft-spezifisch**

Gibt an, dass eine Funktion nur aus verwaltetem Code aufgerufen werden kann.  Verwenden Sie `__clrcall` für alle virtuellen Funktionen, die nur aus verwaltetem Code aufgerufen werden. Allerdings kann diese Aufrufkonvention nicht für Funktionen verwendet werden, die vom nativem Code aufgerufen werden.

Verwenden Sie `__clrcall`, um die Leistung zu verbessern, wenn aus einer verwalteten Funktion eine virtuelle verwaltete Funktion oder aber aus einer verwalteten Funktion ein verwalteter Funktionszeiger aufgerufen wird.

Einstiegspunkte sind separate, vom Compiler generierte Funktionen. Wenn eine Funktion sowohl über die systemeigenen als auch über verwaltete Einstiegspunkte verfügt, ist eine von ihnen die tatsächliche Funktion mit der Funktionsimplementierung. Die andere Funktion ist eine separate Funktion (ein Thunk), welche die tatsächliche Funktion aufruft und die Common Language Runtime PInvoke ausführen lässt. Wenn Sie eine Funktion als `__clrcall` markieren, geben Sie an, dass die Funktionsimplementierung MSIL sein muss und dass die systemeigene Einstiegspunktfunktion nicht generiert wird.

Wenn `__clrcall` nicht angegeben ist und die Adresse einer systemeigenen Funktion verwendet wird, verwendet der Compiler den systemeigenen Einstiegspunkt. `__clrcall` gibt an, dass die Funktion verwaltet wird und keine Notwendigkeit besteht, den Übergang von verwaltet zu systemeigen zu durchlaufen. In diesem Fall verwendet der Compiler den verwalteten Einstiegspunkt.

Wenn **"/ CLR"** (nicht **/CLR: pure** oder **/CLR: safe**) wird verwendet, und `__clrcall` ist nicht verwendet wird, gibt die Adresse des systemeigenen Eintrags zurück Übernahme der Adresse einer Funktion immer Zeigen Sie die Funktion. Wenn `__clrcall` verwendet wird, wird der Einstiegspunkt der systemeigenen Funktion nicht erstellt. Daher wird die Adresse der verwalteten Funktion und keine Einstiegspunkt-Thunkfunktion zurückgegeben. Weitere Informationen finden Sie unter [doppeltes Thunking](../dotnet/double-thunking-cpp.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

[/ CLR (common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) impliziert, dass alle Funktionen Funktionszeiger und `__clrcall` und der Compiler nicht gestattet, eine Funktion innerhalb der Kompiliereinheit alles außer gekennzeichnet werden `__clrcall`. Wenn **/CLR: pure** verwendet wird, `__clrcall` kann nur für Funktionszeiger und externe Deklarationen angegeben werden.

Sie können direkt aufrufen `__clrcall` Funktionen von vorhandenem C++-Code, der kompiliert wurde **"/ CLR"** solange diese Funktion eine MSIL-Implementierung verfügt. `__clrcall` Funktionen können nicht direkt über Funktionen, die Inline-Asm haben, und rufen Sie die CPU-spezifische Intrinisics, z. B. aufgerufen werden, auch wenn diese Funktionen mit kompiliert werden, **"/ CLR"**.

`__clrcall`-Funktionszeiger sollen nur in der Anwendungsdomäne verwendet werden, in der sie erstellt wurden.  Anstatt `__clrcall`-Funktionszeiger über Anwendungsdomänen hinweg zu übergeben, verwenden Sie <xref:System.CrossAppDomainDelegate>. Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Beispiel

Beachten Sie, dass Code nach Bedarf generiert wird, wenn eine Funktion mit `__clrcall` deklariert wird. Dies ist beispielsweise der Fall, wenn eine Funktion aufgerufen wird.

```cpp
// clrcall2.cpp
// compile with: /clr
using namespace System;
int __clrcall Func1() {
   Console::WriteLine("in Func1");
   return 0;
}

// Func1 hasn't been used at this point (code has not been generated),
// so runtime returns the adddress of a stub to the function
int (__clrcall *pf)() = &Func1;

// code calls the function, code generated at difference address
int i = pf();   // comment this line and comparison will pass

int main() {
   if (&Func1 == pf)
      Console::WriteLine("&Func1 == pf, comparison succeeds");
   else
      Console::WriteLine("&Func1 != pf, comparison fails");

   // even though comparison fails, stub and function call are correct
   pf();
   Func1();
}
```

```Output
in Func1
&Func1 != pf, comparison fails
in Func1
in Func1
```

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie ein Funktionszeiger so definiert werden kann, dass deklariert wird, dass der Funktionszeiger nur von verwaltetem Code aufgerufen wird. Dies ermöglicht es dem Compiler, die verwaltete Funktion direkt aufzurufen und den systemeigenen Einstiegspunkt (doppeltes Thunk-Problem) zu vermeiden.

```cpp
// clrcall3.cpp
// compile with: /clr
void Test() {
   System::Console::WriteLine("in Test");
}

int main() {
   void (*pTest)() = &Test;
   (*pTest)();

   void (__clrcall *pTest2)() = &Test;
   (*pTest2)();
}
```

## <a name="see-also"></a>Siehe auch

- [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)
- [Schlüsselwörter](../cpp/keywords-cpp.md)
