---
title: Compilerwarnung (Stufe 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 4126a1267b41cdf9c0161c7e85a9057b2a301d77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578463"
---
# <a name="compiler-warning-level-3-c4398"></a>Compilerwarnung (Stufe 3) C4398

> "*Variable*": Prozessspezifische globale Objekte möglicherweise funktionieren nicht ordnungsgemäß bei mehreren Anwendungsdomänen; verwenden Sie ggf. __declspec(appdomain)

## <a name="remarks"></a>Hinweise

Eine virtuelle Funktion mit [__clrcall](../../cpp/clrcall.md) Aufrufkonvention in einem systemeigenen Typ bewirkt die Erstellung einer anwendungsdomänenspezifischen vtable. Eine solche Variable möglicherweise nicht ordnungsgemäß behoben, bei der Verwendung in mehreren Anwendungsdomänen.

Sie können diese Warnung beheben, indem Sie explizite Markierung der Variablen `__declspec(appdomain)`. In Versionen von Visual Studio vor Visual Studio 2017 können Sie diese Warnung beheben, durch die Kompilierung mit **/CLR: pure**, wodurch globale Variablen pro Anwendungsdomäne standardmäßig. Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Weitere Informationen finden Sie unter [Appdomain](../../cpp/appdomain.md) und [Anwendungsdomänen und Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4398 generiert.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```