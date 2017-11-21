---
title: 'Vorgehensweise: Migrieren zu - Clr: pure (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /clr compiler option [C++], migrating to /clr:pure
- migration [C++], pure MSIL
- pure MSIL [C++], porting to
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebff4ae1ac304ee0af073de49f4ee988922247d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-migrate-to-clrpure-ccli"></a>Gewusst wie: Migrieren auf /clr:pure (C++/CLI)
Dieses Thema behandelt Probleme, die auftreten können, bei der Migration auf reine MSIL unter Verwendung von **/CLR: pure** (finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen). In diesem Thema wird davon ausgegangen, dass der Code, der zu migrierenden derzeit gemischten Assembly unter Verwendung ist die **"/ CLR"** option, da der Migrationspfad von nicht verwaltetem Code auf reine MSIL nicht direkt. Nicht verwaltetem Code finden Sie unter [Vorgehensweise: Migrieren auf/CLR](../dotnet/how-to-migrate-to-clr.md) vor dem Migrieren auf reine MSIL.  
  
## <a name="basic-changes"></a>Grundlegende Änderungen  
 Reines MSIL besteht MSIL-Anweisungen, damit verhindert Kompilierung Code mit Funktionen, die MSIL ausgedrückt werden können. Dazu gehören auch Funktionen als mit Aufrufkonventionen außer [__clrcall](../cpp/clrcall.md). (Nicht __clrcall-Funktionen können werden in einer reinen MSIL-Komponente aufgerufen, aber nicht definiert.)  
  
 Damit werden keine Laufzeitfehler, sollten Sie die C4412-Warnung aktivieren. C4412 hinzufügen können `#pragma warning (default : 4412)` auf jede Kompiliereinheit, die beim Kompilieren mit **/CLR: pure** C++-Typen an und von IJW übergeben (**"/ CLR")** oder systemeigenem Code. Finden Sie unter [Compilerwarnung (Stufe 2) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) für Weitere Informationen.  
  
## <a name="architectural-considerations"></a>Architekturunterschieden  
 Einige der Einschränkungen von reine MSIL-Assemblys aufgeführt, die [reiner und überprüfbarer Code (C + c++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) auf hoher Ebene Auswirkungen auf Entwurf und die Migration Strategie für die Anwendung haben. Im Gegensatz zu gemischten Assemblys profitieren nicht reine MSIL-Assemblys vor allem Kontrollvorgänge vollständige Kompatibilität mit nicht verwalteten Modulen.  
  
 Reine MSIL-Assemblys können nicht verwaltete Funktionen aufrufen, aber nicht vom nicht verwalteten Funktionen aufgerufen werden. Reines MSIL ist daher eine bessere Kandidat für Clientcode, der nicht verwalteten Funktionen verwendet, als es für Servercode handelt, die von nicht verwalteten Funktionen verwendet wird. Wenn die Funktionalität, die in einer reinen MSIL-Assembly enthalten ist, die von nicht verwalteten Funktionen verwendet werden, muss eine gemischte Assembly als Schnittstellenebene verwendet werden.  
  
 Anwendungen, die verwenden ATL bzw. MFC, sind nicht gute Kandidaten für die Migration zu reine MSIL, da diese Bibliotheken in dieser Version nicht unterstützt werden. Entsprechend der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] enthält Headerdateien, die nicht unter Kompilieren **/CLR: pure**.  
  
 Reine MSIL-Assemblys nicht verwaltete Funktionen aufrufen, ist diese Fähigkeit, einfache Funktionen der C-Format beschränkt. Die Verwendung von komplexeren nicht verwaltete APIs wird voraussichtlich benötigt die nicht verwaltete Funktionen verfügbar gemacht werden, in Form einer COM-Schnittstelle oder eine gemischte Assembly, die als Schnittstelle zwischen der reines MSIL und nicht verwalteten Komponenten bearbeiten können. Eine gemischte Assembly-Ebene verwenden, ist die einzige Möglichkeit verwendet nicht verwalteten Funktionen, die Fehlerrückruf-Funktionen, z. B. akzeptieren eine reine Assembly keine systemeigene aufrufbare Funktion für die Verwendung als einen Rückruf bereitstellen.  
  
## <a name="application-domains-and-calling-conventions"></a>Anwendungsdomänen und Aufrufkonventionen  
 Obwohl es möglich ist für reine MSIL-Assemblys verwenden nicht verwalteter Funktionen, Funktionen und statische Daten anders behandelt werden. In reine Assemblys Funktionen implementiert werden, mit der [__clrcall](../cpp/clrcall.md) Aufrufkonvention und statische Daten pro Anwendungsdomäne gespeichert ist. Dies unterscheidet sich von der Standard für nicht verwalteten und gemischten Assemblys ab, bei denen Verwendung der [__cdecl](../cpp/cdecl.md) -Aufrufkonvention für Funktionen und statische Daten auf Basis eines pro-Prozess zu speichern.  
  
 Im Kontext der reines MSIL (und mit/clr: safe kompiliertem Code) sind diese Standards transparent, als [__clrcall](../cpp/clrcall.md) ist die Standardaufrufkonvention der CLR und Anwendungsdomänen sind der systemeigene Bereich für statische und globale Daten in .NET-Anwendungen. Allerdings kann bei nicht verwalteten oder gemischten Komponenten anbinden, müssen, die unterschiedliche Behandlung von Funktionen und globalen Daten Probleme verursachen.  
  
 Ist eine reine MSIL-Komponente Funktionen in einer nicht verwalteten oder gemischten DLL aufrufen, wird beispielsweise eine Headerdatei für die DLL verwendet werden, die reine Assembly zu kompilieren. Jedoch, es sei denn, die Aufrufkonvention für die einzelnen Funktionen im Header explizit angegeben ist, sie werden angenommen werden [__clrcall](../cpp/clrcall.md). Dies wird später Runtime zu Fehlern führen, wie diese Funktionen sind mit implementiert die [__cdecl](../cpp/cdecl.md) Konvention. Die Funktionen in der nicht verwalteten Headerdatei können explizit markiert sein [__cdecl](../cpp/cdecl.md), oder der gesamte DLL-Quellcode muss neu kompiliert werden, unter **/CLR: pure**.  
  
 Auf ähnliche Weise Funktionszeiger wird angenommen, dass es auf [__clrcall](../cpp/clrcall.md) Funktionen unter **/CLR: pure** Kompilierung. Diese müssen zu explizit mit der richtigen Aufrufkonvention angemerkt werden.  
  
 Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C++](../dotnet/application-domains-and-visual-cpp.md).  
  
## <a name="linking-limitations"></a>Einschränkungen für Verknüpfungen  
 Der Visual C++-Linker wird nicht versucht, gemischte und reine OBJ-Dateien, verknüpfen, wie der Speicher und die Aufrufkonventionen unterschiedlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)