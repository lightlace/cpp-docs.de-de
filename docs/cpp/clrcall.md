---
title: __clrcall | Microsoft-Dokumentation
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
ms.openlocfilehash: 9631ac9beb0e6263ac1cf7e60e11e498aa4c7667
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019756"
---
# <a name="clrcall"></a>__clrcall

**Microsoft-spezifisch**

Gibt an, dass eine Funktion nur aus verwaltetem Code aufgerufen werden kann.  Verwendung **__clrcall** für alle virtuellen Funktionen, die nur aus verwaltetem Code aufgerufen wird. Allerdings kann diese Aufrufkonvention nicht für Funktionen verwendet werden, die vom nativem Code aufgerufen werden.

Verwendung **__clrcall** zur Verbesserung der Leistung beim Aufrufen von einer verwalteten Funktion für eine virtuelle verwaltete Funktion oder verwaltete Funktion mit verwalteter Funktionszeiger.

Einstiegspunkte sind separate, vom Compiler generierte Funktionen. Wenn eine Funktion sowohl über die systemeigenen als auch über verwaltete Einstiegspunkte verfügt, ist eine von ihnen die tatsächliche Funktion mit der Funktionsimplementierung. Die andere Funktion ist eine separate Funktion (ein Thunk), welche die tatsächliche Funktion aufruft und die Common Language Runtime PInvoke ausführen lässt. Wenn eine Funktion als markieren **__clrcall**, Sie geben die funktionsimplementierung MSIL sein muss und dass die systemeigene Einstiegspunktfunktion nicht generiert wird.

Wenn die Adresse einer systemeigenen Funktion Wenn **__clrcall** nicht angegeben ist, verwendet der Compiler den systemeigenen Einstiegspunkt. **__clrcall** gibt an, dass die Funktion verwaltet wird und es nicht erforderlich ist, durchlaufen den Übergang von verwaltet zu systemeigen. In diesem Fall verwendet der Compiler den verwalteten Einstiegspunkt.

Wenn `/clr` (nicht `/clr:pure` oder `/clr:safe`) wird verwendet, und **__clrcall** wird nicht verwendet wird, übernehmen die Adresse einer Funktion immer die Adresse die systemeigene Einstiegspunktfunktion zurückgegeben. Wenn **__clrcall** wird verwendet, die systemeigene Einstiegspunktfunktion wird nicht erstellt, damit Sie die Adresse der verwalteten Funktion keinen Einstiegspunkt-thunkfunktion abrufen. Weitere Informationen finden Sie unter [doppeltes Thunking](../dotnet/double-thunking-cpp.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

[/ CLR (common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) bedeutet, dass alle Funktionen Funktionszeiger und **__clrcall** und der Compiler nicht erlaubt, dass eine Funktion in der Kompiliereinheit etwas anderes als markiertwerden **__clrcall**. Wenn **/CLR: pure** verwendet wird, **__clrcall** kann nur für Funktionszeiger und externe Deklarationen angegeben werden.

Sie können direkt aufrufen **__clrcall** Funktionen aus vorhandenen C++-Code, die mithilfe von kompiliert wurde **"/ CLR"** solange diese Funktion eine MSIL-Implementierung verfügt. **__clrcall** Funktionen können nicht direkt über Funktionen, die Inline-Asm haben, und rufen die CPU-spezifische Intrinisics, z. B. nicht aufgerufen werden, auch wenn diese Funktionen mit kompiliert werden `/clr`.

**__clrcall** Funktionszeiger nur sollen in der Anwendungsdomäne verwendet werden, in dem sie erstellt wurden.  Statt der Übergabe von **__clrcall** -Funktionszeiger über Anwendungsdomänen hinweg, verwenden Sie <xref:System.CrossAppDomainDelegate>. Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Beispiel

Beachten Sie, dass, wenn eine Funktion deklariert wird, mit **__clrcall**, Code generiert werden, wenn erforderlich, z. B. Wenn Funktion aufgerufen wird.

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

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
