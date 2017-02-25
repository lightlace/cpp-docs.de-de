---
title: "Bibliotheksunterst&#252;tzung f&#252;r verschiedene Assemblys | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bibliotheken [C++], Gemischte Assemblys"
  - "Gemischte Assemblys [C++], Bibliotheksunterstützung"
  - "msvcm90[d].dll"
  - "msvcmrt[d].lib"
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Bibliotheksunterst&#252;tzung f&#252;r verschiedene Assemblys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ unterstützt die Verwendung der C\+\+\-Standardbibliothek, der CRT \(Common RunTime\)\-Bibliothek und ATL sowie MFC für Anwendungen, die mit [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md) kompiliert wurden.  Dadurch können auch vorhandene Anwendungen .NET Framework\-Features verwenden, die mit diesen Bibliotheken arbeiten.  
  
 Die folgenden neuen DLLs und Importbibliotheken werden unterstützt:  
  
-   Msvcmrt\[d\].lib, wenn mit \/clr kompiliert wird.  Gemischte Assemblys können mit dieser Importbibliothek verknüpft werden.  
  
-   Msvcm90\[d\].dll und Msvcurt\[d\].lib, wenn mit \/clr:pure kompiliert wird.  Die DLL stellt eine gemischte Assembly dar, die verwalteten CRT\-Support bietet und als Teil einer verwalteten Assembly im globalen Assemblycache \(GAC\) installiert ist.  Reine Assemblys werden mit dieser Importbibliothek verknüpft und an Msvcm90.dll. gebunden.  
  
 Diese Unterstützung bietet mehrere Vorteile:  
  
-   Die CRT\- und C\+\+\-Standardbibliothek stehen sowohl gemischtem als auch reinem Code zur Verfügung.  Die CRT\- und C\+\+\-Standardbibliotheken sind nicht überprüfbar. Die Aufrufe werden nach wie vor an dieselben CRT\- und C\+\+\-Standardbibliotheken weitergeleitet, die auch vom systemeigenen Code verwendet werden.  
  
-   Korrekte, einheitliche Ausnahmebehandlung in reinen und gemischten Programmabbildern.  
  
-   Statische Initialisierung der C\+\+\-Variablen in reinen und gemischten Programmabbildern.  
  
-   Unterstützung für pro\-AppDomain\- und pro\-Prozess\-Variablen in verwaltetem Code.  
  
-   Behebt die Probleme mit der Ladeprogrammsperre, die in gemischten DLLs in Visual C\+\+ .NET und Visual C\+\+ .NET 2003 auftraten.  
  
 Diese Unterstützung hat die folgenden Einschränkungen:  
  
-   Es wird nur das CRT\-DLL\-Modell unterstützt \(gleichgültig, ob mit \/clr oder \/clr:pure kompiliert wird\).  
  
-   Reine und gemischte Objekte können nicht in einem einzigen Programmabbild kombiniert werden, wenn diese Objekte die Visual C\+\+\-Bibliotheken verwenden \(da alle Objekte in einem reinen Programmabbild rein sein müssen\).  Andernfalls werden Link\-Time\-Fehler ausgegeben.  
  
 Sie sollten die Common Language Runtime \(CLR\) auf die aktuelle Version aktualisieren, da die Funktionsweise mit früheren Versionen nicht gewährleistet ist.  Code, der mit diesen Änderungen erstellt wurde, kann nicht mit CLR in der Version 1.x ausgeführt werden.  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)