---
title: "Gewusst wie: Migrieren auf /clr:pure (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Migrieren zu /clr:pure"
  - "Migration [C++], Reine MSIL"
  - "Reine MSIL [C++], Portieren auf"
ms.assetid: 5ffb1184-2095-4ade-84aa-4fa6324bc764
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Migrieren auf /clr:pure (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt werden mögliche Probleme erläutert, die beim Migrieren auf reine MSIL unter Verwendung von **\/clr:pure** auftreten können \(weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md)\).  In diesem Abschnitt wird davon ausgegangen, dass der zu migrierende Code einer gemischten Assembly unter Verwendung der Option **\/clr** entspricht, da der Migrationspfad von nicht verwaltetem Code auf reine MSIL nicht direkt ist.  Beachten Sie den Abschnitt [Gewusst wie: Migrieren zu \/clr](../dotnet/how-to-migrate-to-clr.md), bevor Sie eine Migration von nicht verwaltetem Code auf reine MSIL durchführen.  
  
## Grundlegende Änderungen  
 Reine MSIL besteht aus MSIL\-Anweisungen, daher wird bei Code mit Funktionen, die nicht in MSIL ausgedrückt werden können, eine Kompilierung verhindert.  Dazu gehören auch Funktionen, die andere Aufrufkonventionen als [\_\_clrcall](../cpp/clrcall.md) verwenden. \(Funktionen, die nicht \_\_clrcall verwenden, können in einer reinen MSIL\-Komponente aufgerufen, aber nicht definiert werden.\)  
  
 Um Laufzeitfehler auszuschließen, sollten Sie die C4412\-Warnung aktivieren.  Aktivieren Sie C4412 durch Hinzufügen von `#pragma warning (default : 4412)` zu jeder mit **\/clr:pure** kompilierten Kompiliereinheit, bei der C\+\+\-Typen an und von IJW \(**\/clr\)** oder systemeigenen Code übergeben werden.  Weitere Informationen finden Sie unter [Compilerwarnung \(Stufe 2\) C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md).  
  
## Überlegungen zur Architektur  
 Einige Einschränkungen der in [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md) aufgeführten reinen MSIL\-Assemblys wirken sich auf höheren Ebenen auf das Anwendungsdesign und die Migrationsstrategie aus.  Besonders berücksichtigt werden sollte, dass reine MSIL\-Assemblys im Gegensatz zu gemischten Assemblys über keine volle Kompatibilität mit nicht verwalteten Modulen verfügen.  
  
 Reine MSIL\-Assemblys können nicht verwaltete Funktionen aufrufen, jedoch nicht von diesen aufgerufen werden.  Daher eignet sich reine MSIL besser für Clientcode, der nicht verwaltete Funktionen verwendet, als für Servercode, der von nicht verwalteten Funktionen verwendet wird.  Wenn die Funktionalität einer reinen MSIL\-Assembly von nicht verwalteten Funktionen verwendet werden soll, muss eine gemischte Assembly als Schnittstellenebene verwendet werden.  
  
 Anwendungen, die ATL oder MFC verwenden, sind keine guten Kandidaten für eine Migration auf reine MSIL, da diese Bibliotheken in der vorliegenden Version nicht unterstützt werden.  Desgleichen enthält das [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] Headerdateien, die unter **\/clr:pure** nicht kompiliert werden.  
  
 Auch wenn reine MSIL\-Assemblys nicht verwaltete Funktionen aufrufen können, ist diese Möglichkeit auf einfache Funktionen in C\-Format beschränkt.  Bei Verwendung komplexerer APIs müssen die nicht verwalteten Funktionen wahrscheinlich in Form einer COM\-Schnittstelle oder einer gemischten Assembly verfügbar gemacht werden, die als Schnittstelle zwischen den reinen MSIL\-Komponenten und den nicht verwalteten Komponenten dienen können.  Das Verwenden einer gemischten Assembly\-Ebene ist beispielsweise die einzige Möglichkeit, nicht verwaltete Funktionen zu verwenden, die Rückruffunktionen akzeptieren, da eine pure\-Assembly keine systemeigene aufrufbare Funktion enthält, die als Rückruf verwendet werden kann.  
  
## Anwendungsdomänen und Aufrufkonventionen  
 In reine MSIL\-Assemblys können nicht verwaltete Funktionen zwar verwendet werden, doch werden Funktionen und statische Daten unterschiedlich behandelt.  In pure\-Assemblys werden Funktionen mit der [\_\_clrcall](../cpp/clrcall.md)\-Aufrufkonvention implementiert und statische Daten pro Anwendungsdomäne gespeichert.  Dies weicht von der Standardbehandlung bei nicht verwalteten und gemischten Assemblys ab, bei denen die [\_\_cdecl](../cpp/cdecl.md)\-Aufrufkonvention für Funktionen verwendet und statische Daten auf Prozessbasis gespeichert werden.  
  
 Im Kontext von reine MSIL \(und mit \/clr:safe kompiliertem Code\) sind diese Standards implizit, da [\_\_clrcall](../cpp/clrcall.md) die Standardaufrufkonvention von CLR ist und Anwendungsdomänen der systemeigene Bereich für statische und globale Daten in .NET\-Anwendungen sind.  Bei der Implementierung von Schnittstellen zu nicht verwalteten oder gemischten Komponenten kann die unterschiedliche Behandlung von Funktionen und globalen Daten jedoch Probleme verursachen.  
  
 Wenn z. B. eine reine MSIL\-Komponente Funktionen in einer nicht verwalteten oder gemischten DLL aufrufen soll, wird eine Headerdatei für die DLL zum Kompilieren der reinen Assembly verwendet.  Wenn die Aufrufkonvention für die einzelnen Funktionen im Header jedoch nicht explizit gekennzeichnet ist, wird [\_\_clrcall](../cpp/clrcall.md) als Aufrufkonvention angenommen.  Dies führt später zu Laufzeitfehlern, da diese Funktionen wahrscheinlich mit der [\_\_cdecl](../cpp/cdecl.md)\-Konvention implementiert werden.  Die Funktionen in der nicht verwalteten Headerdatei können explizit als [\_\_cdecl](../cpp/cdecl.md) gekennzeichnet werden, oder der gesamte DLL\-Quellcode muss unter **\/clr:pure** neu kompiliert werden.  
  
 Ebenso wird angenommen, dass unter der **\/clr:pure**\-Kompilierung Funktionszeiger auf [\_\_clrcall](../cpp/clrcall.md)\-Funktionen verweisen.  Diese müssen ebenfalls explizit mit der richtigen Aufrufkonvention gekennzeichnet werden.  
  
 Weitere Informationen finden Sie unter [Anwendungsdomänen und Visual C\+\+](../dotnet/application-domains-and-visual-cpp.md).  
  
## Einschränkungen für Verknüpfungen  
 Der Visual C\+\+\-Linker verknüpft keine gemischten und reinen OBJ\-Dateien, da der Speicherbereich und die Aufrufkonventionen unterschiedlich sind.  
  
## Siehe auch  
 [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)