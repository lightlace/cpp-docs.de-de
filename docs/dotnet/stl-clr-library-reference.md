---
title: "Referenz zur STL/CLR-Bibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Clientverzeichnis"
  - "STL/CLR-Bibliothek"
  - "STL/CLR, Verteilung"
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Referenz zur STL/CLR-Bibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die STL\/CLR\-Bibliothek ist ein Paket der Standard Template Library \(STL\), einer Teilmenge der C\+\+\-Standardbibliothek, die mit C\+\+ und der Common Language Runtime \(CLR\) von .NET Framework eingesetzt werden kann.  Mit STL\/CLR können Sie alle Container, Iteratoren und Algorithmen der STL in einer verwalteten Umgebung verwenden.  
  
 Verwendung von STL\/CLR:  
  
-   Schließen Sie Header aus dem Unterverzeichnis **cliext** ein statt der üblichen Äquivalente aus der Standard C\+\+Standardbibliothek.  
  
-   Qualifizieren Sie Bibliotheksnamen mit `cliext::` statt mit `std::`.  
  
 STL\/CLR macht die generischen Typen und Schnittstellen verfügbar, die in den assemblyübergreifenden Szenarien in der .NET\-Assembly **Microsoft.VisualC.STLCLR.dll** verwendet werden.  Diese DLL ist in .NET Framework 3.5 enthalten.  Wenn Sie eine Anwendung neu verteilen, die STL\/CLR verwendet, müssen Sie .NET Framework 3.5 sowie alle anderen Visual C\+\+\-Bibliotheken, die das Projekt verwendet, im Abhängigkeitenabschnitt des Setup\-Projekts einschließen.  
  
## In diesem Abschnitt  
 [cliext\-Namespace](../dotnet/cliext-namespace.md)  
 Erläutert den Namespace, der alle Typen der STL\/CLR\-Bibliothek enthält.  
  
 [STL\/CLR\-Container](../dotnet/stl-clr-containers.md)  
 Bietet eine Übersicht über die Container in der C\+\+\-Standardbibliothek, über die Anforderungen für Containerelemente, über die Typen von Elementen, die eingefügt werden können, und über Probleme mit Besitzverhältnissen.  
  
 [Anforderungen für STL\/CLR\-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md)  
 Beschreibt Mindestanforderungen für alle Referenztypen, die in STL\-Container eingefügt werden.  
  
 [Gewusst wie: Umwandeln einer .Net\-Auflistung in einen STL\/CLR\-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Beschreibt, wie eine .NET\-Auflistung in einen STL\/CLR\-Container konvertiert wird.  
  
 [Gewusst wie: Umwandeln eines STL\/CLR\-Containers in eine .NET\-Auflistung](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 Beschreibt, wie ein STL\/CLR\-Container in eine .NET\-Auflistung konvertiert wird.  
  
 [Gewusst wie: Einen STL\/CLR\-Container einer Assembly verfügbar machen](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Erläutert, wie die Elemente einiger STL\/CLR\-Container aus einer C\+\+\-Assembly anzeigt werden.  
  
 Außerdem beschreibt dieser Abschnitt die folgenden STL\/CLR\-Komponenten:  
  
|||  
|-|-|  
|[adapter](../dotnet/adapter-stl-clr.md)|[algorithm](../dotnet/algorithm-stl-clr.md)|  
|[deque](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional](../dotnet/functional-stl-clr.md)|[hash\_map](../dotnet/hash-map-stl-clr.md)|  
|[hash\_multimap](../dotnet/hash-multimap-stl-clr.md)|[hash\_multiset](../dotnet/hash-multiset-stl-clr.md)|  
|[hash\_set](../dotnet/hash-set-stl-clr.md)|[list](../dotnet/list-stl-clr.md)|  
|[map](../dotnet/map-stl-clr.md)|[multimap](../dotnet/multimap-stl-clr.md)|  
|[multiset](../dotnet/multiset-stl-clr.md)|[numeric](../dotnet/numeric-stl-clr.md)|  
|[priority\_queue](../dotnet/priority-queue-stl-clr.md)|[queue](../dotnet/queue-stl-clr.md)|  
|[set](../dotnet/set-stl-clr.md)|[Stapel](../dotnet/stack-stl-clr.md)|  
|[utility](../dotnet/utility-stl-clr.md)|[Vektor](../dotnet/vector-stl-clr.md)|  
  
## Siehe auch  
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)