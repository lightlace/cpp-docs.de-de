---
title: Featurevergleich zwischen "gemischte, reine und überprüfbare" (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cb1b2ba71277415fd1ba5124f6120cc2f2c995d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704710"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Featurevergleich zwischen "gemischte, reine und überprüfbare" (C + c++ / CLI)

In diesem Thema werden die Funktionen zwischen den verschiedenen verglichen **"/ CLR"** Kompilierung Modi. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).

> [!IMPORTANT]
> Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="feature-comparison"></a>Featurevergleich zwischen "

|Feature|Gemischt (/clr)|Rein (/clr:pure)|Safe (/ CLR: safe)|Verwandte Informationen|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|CRT-Bibliothek|Unterstützt|deprecated||[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)|
|MFC/ATL|Unterstützt|||[MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md) &#124; [Klassenübersicht](../atl/atl-class-overview.md)|
|Nicht verwaltete Funktionen|Unterstützt|||[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)|
|Nicht verwaltete Daten|Unterstützt|deprecated||[Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|Aus nicht verwalteten Funktionen aufgerufen werden kann|Unterstützt||||
|Unterstützt das Aufrufen von nicht verwalteter Funktionen|Unterstützt|deprecated|deprecated|[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|Unterstützt die Reflektion|Nur DLLs|deprecated|deprecated|[Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>Siehe auch

- [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)