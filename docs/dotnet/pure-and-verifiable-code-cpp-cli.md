---
title: Reiner und überprüfbarer Code (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 66f3b5a33791d20297cde6e6223ba65189a99682
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743831"
---
# <a name="pure-and-verifiable-code-ccli"></a>Reiner und überprüfbarer Code (C++ / CLI)

Bei der .NET-Programmierung unterstützt Visual C++ in Visual Studio 2017 die Erstellung von gemischten Assemblys mithilfe der [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption. Die **/CLR: pure** und **CLR: safe** Optionen sind in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt. Wenn Ihr Code sicher oder überprüfbar sein muss, und es wird empfohlen, dass Sie es zum Portieren C#.

## <a name="mixed-clr"></a>Gemischt (/clr)

Gemischte Assemblys (kompiliert mit **"/ CLR"**) enthalten sowohl unverwaltete als auch verwaltete Teile, sodass es möglich, dass sie .NET-Funktionen verwenden jedoch immer noch systemeigenen Code. Dadurch können Anwendungen und Komponenten für die Verwendung von .NET-Funktionen aktualisiert werden, ohne dass das gesamte Projekt neu geschrieben werden muss. Mithilfe von Visual C++ zum Mischen von verwaltetem und nativem Code auf diese Weise wird die C++-Interop aufgerufen. Weitere Informationen finden Sie unter [gemischte (Native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md) und [Native und .NET Interoperabilität](../dotnet/native-and-dotnet-interoperability.md).

Aufrufe aus verwalteten Assemblys systemeigener DLLs über P/Invoke werden kompiliert, aber Sie können zur Laufzeit je nach Sicherheitseinstellungen fehlschlagen.

Es gibt eine Codekonstellation, die kompiliert wird, obwohl dies eine unüberprüfbare Assembly zu Folge hat: Aufruf einer virtuellen Funktion durch eine Objektinstanz mit dem Bereichsauflösungsoperator.  Beispiel: `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>Siehe auch

- [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
