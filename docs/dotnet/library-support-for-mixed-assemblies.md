---
title: "Bibliotheksunterstützung für gemischte Assemblys | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 497900112bedc9c16b88078ab2b682b0357eb9bd
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="library-support-for-mixed-assemblies"></a>Bibliotheksunterstützung für verschiedene Assemblys
Visual C++ unterstützt die Verwendung von C++-Standardbibliothek, die allgemeine-Laufzeitbibliothek (CRT), ATL und MFC für Anwendungen mit kompiliert [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md). Dadurch können vorhandene Anwendungen, die diese Bibliotheken verwenden, um als auch .NET Framework-Funktionen zu verwenden.  
  
 Diese Unterstützung stellt die folgenden neuen DLLs und Bibliotheken:  
  
-   Msvcmrt [d] lib, wenn Sie mit "/ CLR" kompiliert. Gemischte Assemblys ist mit dieser Importbibliothek verknüpft.  
  
-   Msvcm90 [d] .dll "und" Msvcurt [d] .lib beim Kompilieren mit/clr: pure. Die DLL ist eine gemischte Assembly Bereitstellen von verwalteten C ausführen Zeit (CRT)-Unterstützung und ist Teil einer verwalteten Assembly im globalen Assemblycache (GAC) installiert. Reine Assemblys Link Importbibliothek und am Ende an Msvcm90.dll gebunden.  
  
 Diese Unterstützung bietet mehrere Vorteile beziehen:  
  
-   Die CRT- und C++-Standardbibliothek sind für gemischten und reinen Code verfügbar. Die CRT- und C++-Standardbibliothek, die bereitgestellt sind nicht überprüfbar. Ihre Aufrufe werden letztlich weiterhin auf dem CRT- und C++-Standardbibliothek weitergeleitet, wie Sie von systemeigenem Code verwenden.  
  
-   Beheben Sie einheitliche Ausnahmebehandlung in reinen und gemischten Bildern.  
  
-   Statischen Initialisierung der C++-Variablen in reinen und gemischten Bildern.  
  
-   Unterstützung für pro-AppDomain- und pro-Prozess-Variablen in verwaltetem Code.  
  
-   Aufgelöst Loader Sperre Probleme, die in gemischten DLLs kompiliert in Visual Studio 2003 und früher angewendet wird.  
  
 Diese Unterstützung stellt darüber hinaus die folgenden Einschränkungen:  
  
-   Nur die CRT-DLL-Modell unterstützt wird (sowohl für Code, der mit "/ CLR" oder "/ CLR" kompiliert: pure).  
  
-   Sie können reinen und gemischten Objekte in ein einzelnes Bild nicht mischen, wenn diese Objekte weiterhin Visual C++-Bibliotheken verwenden (da alle Objekte in einem reinen Image rein sein müssen). Wenn Sie dies tun, erhalten Sie die Link-Time-Fehler.  
  
 Sie sollten die common Language Runtime (CLR) auf die aktuelle Version aktualisieren, da nicht gewährleistet ist, arbeiten mit früheren Versionen. Mit diesen Änderungen erstellte Code wird nicht ausgeführt, in CLR-Version 1.x.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)