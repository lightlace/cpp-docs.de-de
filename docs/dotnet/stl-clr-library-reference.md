---
title: Referenz zur STL/CLR-Bibliothek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aecb7c509fc1b072086a8772c3430c43b67350be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-library-reference"></a>Referenz zur STL/CLR-Bibliothek
Die STL/CLR-Bibliothek ist ein Paket für eine Teilmenge der C++-Standardbibliothek für die Verwendung mit C++ und die .NET Framework common Language Runtime (CLR). Mit STL/CLR können Sie alle Container, Iteratoren und Algorithmen der Standardbibliothek in einer verwalteten Umgebung verwenden.  
  
 Verwendung von STL/CLR:  
  
-   Schließen Sie Header aus der **Cliext** Unterverzeichnis anstelle der üblichen Entsprechungen von C++-Standardbibliothek enthalten.  
  
-   Qualifizieren Sie Bibliotheksnamen mit `cliext::` statt mit `std::`.  
  
 STL/CLR macht die generischen Typen und Schnittstellen, die in den assemblyübergreifenden Szenarien in der .NET-Assembly verwendet **Microsoft.VisualC.STLCLR.dll**. Diese DLL ist in .NET Framework 3.5 enthalten. Wenn Sie eine Anwendung neu verteilen, die STL/CLR verwendet, müssen Sie .NET Framework 3.5 sowie alle anderen Visual C++-Bibliotheken, die das Projekt verwendet, im Abhängigkeitenabschnitt des Setup-Projekts einschließen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [cliext-Namespace](../dotnet/cliext-namespace.md)  
 Erläutert den Namespace, der alle Typen der STL/CLR-Bibliothek enthält.  
  
 [STL/CLR-Container](../dotnet/stl-clr-containers.md)  
 Bietet eine Übersicht über die Container, die in der C++-Standardbibliothek, die Anforderungen für Containerelemente, Typen von Elementen, die eingefügt werden können, und den Besitzprobleme gefunden werden.  
  
 [Anforderungen für STL/CLR-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md)  
 Beschreibt Mindestanforderungen für alle Referenztypen, die in C++-Standardbibliothek Container eingefügt werden.  
  
 [Vorgehensweise: Umwandeln einer .Net-Auflistung in einen STL/CLR-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 Beschreibt, wie eine .NET-Auflistung in einen STL/CLR-Container konvertiert wird.  
  
 [Vorgehensweise: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 Beschreibt, wie ein STL/CLR-Container in eine .NET-Auflistung konvertiert wird.  
  
 [Vorgehensweise: Einen STL/CLR-Container einer Assembly verfügbar machen](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 Erläutert, wie die Elemente einiger STL/CLR-Container aus einer C++-Assembly anzeigt werden.  
  
 Außerdem beschreibt dieser Abschnitt die folgenden STL/CLR-Komponenten:  
  
|||  
|-|-|  
|[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)|  
|[deque (STL/CLR)](../dotnet/deque-stl-clr.md)|[for each in](../dotnet/for-each-in.md)|  
|[functional (STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)|  
|[hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|  
|[hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list (STL/CLR)](../dotnet/list-stl-clr.md)|  
|[map (STL/CLR)](../dotnet/map-stl-clr.md)|[multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)|  
|[multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)|  
|[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue (STL/CLR)](../dotnet/queue-stl-clr.md)|  
|[set (STL/CLR)](../dotnet/set-stl-clr.md)|[stack (STL/CLR)](../dotnet/stack-stl-clr.md)|  
|[utility (STL/CLR)](../dotnet/utility-stl-clr.md)|[vector (STL/CLR)](../dotnet/vector-stl-clr.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)