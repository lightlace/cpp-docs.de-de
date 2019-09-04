---
title: managed- bzw. unmanaged-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.unmanaged
- managed_CPP
- unmanaged_CPP
- vc-pragma.managed
helpviewer_keywords:
- managed pragma
- pragmas, unmanaged
- pragmas, managed
- unmanaged pragma
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
ms.openlocfilehash: 4c13155d1c84966a593df11baf525a0c3539f02c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218807"
---
# <a name="managed-unmanaged-pragmas"></a>managed- bzw. unmanaged-Pragma

Aktivieren Sie das Steuerelement auf Funktionsebene, um Funktionen als verwaltet oder nicht verwaltet zu kompilieren.

## <a name="syntax"></a>Syntax

> **#pragma verwaltet**\
> **nicht verwaltet #Pragma**\
> **#pragma verwaltet (** [ **Push,** ] { **on** | **Off** } **)** \
> **#pragma verwaltet (Pop)**

## <a name="remarks"></a>Hinweise

Mit der [/CLR](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption wird das Steuerelement auf Modulebene für das Kompilieren von Funktionen als verwaltet oder nicht verwaltet bereitstellt.

Eine nicht verwaltete Funktion wird für die Native Plattform kompiliert. Die Ausführung dieses Teils des Programms wird vom Common Language Runtime an die Native Plattform übermittelt.

Funktionen werden standardmäßig als verwaltet kompiliert, wenn `/clr` verwendet wird.

Beim Anwenden dieser Pragmas:

- Fügen Sie das Pragma vor einer Funktion hinzu, jedoch nicht innerhalb eines Funktions Texts.

- Fügen Sie das Pragma nach `#include`-Anweisungen hinzu. Verwenden Sie diese Pragmas nicht `#include` vor-Anweisungen.

Der Compiler ignoriert die **verwalteten** und **nicht verwalteten** Pragmas, `/clr` wenn nicht in der Kompilierung verwendet wird.

Wenn eine Vorlagen Funktion instanziiert wird, bestimmt der pragma-Zustand, wenn die Vorlage definiert ist, ob Sie verwaltet oder nicht verwaltet wird.

Weitere Informationen finden Sie unter [Initialisierung gemischter](../dotnet/initialization-of-mixed-assemblies.md)Assemblys.

## <a name="example"></a>Beispiel

```cpp
// pragma_directives_managed_unmanaged.cpp
// compile with: /clr
#include <stdio.h>

// func1 is managed
void func1() {
   System::Console::WriteLine("In managed function.");
}

// #pragma unmanaged
// push managed state on to stack and set unmanaged state
#pragma managed(push, off)

// func2 is unmanaged
void func2() {
   printf("In unmanaged function.\n");
}

// #pragma managed
#pragma managed(pop)

// main is managed
int main() {
   func1();
   func2();
}
```

```Output
In managed function.
In unmanaged function.
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
