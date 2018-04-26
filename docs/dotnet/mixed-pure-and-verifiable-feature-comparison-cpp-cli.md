---
title: Featurevergleich zwischen "gemischte, reine und überprüfbare" (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4ac2356fbe12af53890e8159484b89150b60945
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Funktionsvergleich zwischen „gemischt“, „rein“ und „überprüfbar“ (C++/CLI)
In diesem Thema werden die Funktionen zwischen den verschiedenen verglichen **"/ CLR"** Kompilierung Modi. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
## <a name="feature-comparison"></a>Featurevergleich  
  
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
 [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)