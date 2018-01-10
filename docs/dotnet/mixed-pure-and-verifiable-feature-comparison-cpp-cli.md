---
title: "Featurevergleich zwischen \"gemischte, reine und überprüfbare\" (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3ee9fbed3fd82fd450fd179683fd119cb1630034
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Funktionsvergleich zwischen „gemischt“, „rein“ und „überprüfbar“ (C++/CLI)
In diesem Thema werden die Funktionen zwischen den verschiedenen verglichen **"/ CLR"** Kompilierung Modi. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
## <a name="feature-comparison"></a>Featurevergleich zwischen "  
  
|Funktion|Gemischt (/clr)|Rein (/clr:pure)|Safe (/ CLR: safe)|Verwandte Informationen|  
|-------------|---------------------|-------------------------|-------------------------|-------------------------|  
|CRT-Bibliothek|Unterstützt|Unterstützt||[Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC/ATL|Unterstützt|||[MFC-Desktopanwendungen](../mfc/mfc-desktop-applications.md) &#124; [Klassenübersicht](../atl/atl-class-overview.md)|  
|Nicht verwaltete Funktionen|Unterstützt|||[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)|  
|Nicht verwaltete Daten|Unterstützt|Unterstützt||[Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|Aus nicht verwalteten Funktionen aufgerufen werden kann|Unterstützt|||[Vorgehensweise: Migrieren auf/CLR: pure (C + c++ / CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)|  
|Unterstützt das Aufrufen von nicht verwalteter Funktionen|Unterstützt|Nur die Funktionen der C-Format|P/Invoke aufrufen nur|[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|Unterstützt die Reflektion|Nur DLLs|Unterstützt|Unterstützt|[Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)