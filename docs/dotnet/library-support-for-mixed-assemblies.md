---
title: Bibliotheksunterstützung für gemischte Assemblys | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9fbb660d3f62c255ab81c7e77fef6c5d042efb12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="library-support-for-mixed-assemblies"></a>Bibliotheksunterstützung für verschiedene Assemblys
Visual C++ unterstützt die Verwendung von C++-Standardbibliothek, die allgemeine-Laufzeitbibliothek (CRT), ATL und MFC für Anwendungen mit kompiliert [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md). Dadurch können vorhandene Anwendungen, die diese Bibliotheken verwenden, um als auch .NET Framework-Funktionen zu verwenden.  
  
 Diese Unterstützung stellt die folgenden neuen DLLs und Bibliotheken:  
  
-   Msvcmrt [d] lib, wenn Sie mit "/ CLR" kompiliert. Gemischte Assemblys ist mit dieser Importbibliothek verknüpft.  
  
 Diese Unterstützung bietet mehrere Vorteile beziehen:  
  
-   Die CRT- und C++-Standardbibliothek sind für gemischten und reinen Code verfügbar. Die CRT- und C++-Standardbibliothek, die bereitgestellt sind nicht überprüfbar. Ihre Aufrufe werden letztlich weiterhin auf dem CRT- und C++-Standardbibliothek weitergeleitet, wie Sie von systemeigenem Code verwenden.  
  
-   Beheben Sie einheitliche Ausnahmebehandlung in reinen und gemischten Bildern.  
  
-   Statischen Initialisierung der C++-Variablen in reinen und gemischten Bildern.  
  
-   Unterstützung für pro-AppDomain- und pro-Prozess-Variablen in verwaltetem Code.  
  
-   Aufgelöst Loader Sperre Probleme, die in gemischten DLLs kompiliert in Visual Studio 2003 und früher angewendet wird.  
  
 Diese Unterstützung stellt darüber hinaus die folgenden Einschränkungen:  
  
-   Für Code, der mit "/ CLR" kompiliert wird nur das CRT-DLL-Modell unterstützt.  
  
 Sie sollten die common Language Runtime (CLR) auf die aktuelle Version aktualisieren, da nicht gewährleistet ist, arbeiten mit früheren Versionen. Mit diesen Änderungen erstellte Code wird nicht ausgeführt, in CLR-Version 1.x.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)