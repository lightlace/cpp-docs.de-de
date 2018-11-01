---
title: Funktionsvergleich zwischen "gemischte, reine und überprüfbare" (C++ / CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
ms.openlocfilehash: 81fcf986ee68f5f8f64c8070bb992fa1cda1683b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482071"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Funktionsvergleich zwischen "gemischte, reine und überprüfbare" (C++ / CLI)

Dieses Thema vergleicht die Funktionen zwischen den verschiedenen **"/ CLR"** Kompilierung Modi. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).

> [!IMPORTANT]
> Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="feature-comparison"></a>Funktionsvergleich

|Feature|Gemischt (/clr)|Rein (/clr:pure)|Sichere (/ CLR: safe)|Verwandte Informationen|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|CRT-Bibliothek|Unterstützt|deprecated||[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)|
|MFC/ATL|Unterstützt|||[MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md) &#124; [Klassenübersicht](../atl/atl-class-overview.md)|
|Nicht verwaltete Funktionen|Unterstützt|||[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)|
|Nicht verwaltete Daten|Unterstützt|deprecated||[Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|Von nicht verwalteten Funktionen|Unterstützt||||
|Das Aufrufen von nicht verwalteter Funktionen|Unterstützt|deprecated|deprecated|[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|Unterstützt die Reflektion|Nur die DLLs|deprecated|deprecated|[Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>Siehe auch

- [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)