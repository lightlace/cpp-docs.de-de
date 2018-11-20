---
title: Referenz zur STL/CLR-Bibliothek
ms.date: 09/18/2018"
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: 6914b61597e38c94a214089ecc3aeed17aec46d3
ms.sourcegitcommit: 984fb4814a2dd9bcea5ec88c9528707f17a7cffa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2018
ms.locfileid: "51949517"
---
# <a name="stlclr-library-reference"></a>Referenz zur STL/CLR-Bibliothek

Die STL/CLR-Bibliothek stellt eine Schnittstelle, die ähnlich wie die C++-Standardbibliothek-Container für die Verwendung mit C++ und die .NET Framework common Language Runtime (CLR). STL/CLR ist vollständig unabhängig von der Microsoft-Implementierung der C++-Standardbibliothek. STL/CLR wird für die Unterstützung älterer verwaltet, jedoch werden nicht auf dem neuesten Stand mit dem C++-Standard. Es wird dringend empfohlen, mithilfe der systemeigenen [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md) Container anstelle der STL/CLR, wann immer möglich.

Verwendung von STL/CLR:

- Schließen Sie Header aus der **Cliext** Unterverzeichnis anstelle der üblichen Entsprechungen von C++-Standardbibliothek enthalten.

- Qualifizieren Sie Bibliotheksnamen mit `cliext::` statt mit `std::`.

Die STL/CLR-Bibliothek stellt eine STL-ähnliche Schnittstelle für die Verwendung mit C++ und die .NET Framework common Language Runtime (CLR) bereit. Diese Bibliothek wird für die Unterstützung älterer verwaltet, jedoch bleibt nicht auf dem neuesten Stand mit dem C++-Standard. Es wird dringend empfohlen, mithilfe der systemeigenen [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md) Container anstelle der STL/CLR.

## <a name="in-this-section"></a>In diesem Abschnitt

[cliext-Namespace](../dotnet/cliext-namespace.md)<br/>
Erläutert den Namespace, der alle Typen der STL/CLR-Bibliothek enthält.

[STL/CLR-Container](../dotnet/stl-clr-containers.md)<br/>
Bietet eine Übersicht über die Container, die in der C++-Standardbibliothek, einschließlich der Anforderungen für Containerelemente, Typen von Elementen, die eingefügt werden können und Besitzprobleme gefunden werden.

[Anforderungen für STL/CLR-Containerelemente](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
Beschreibt die Mindestanforderungen für alle Verweistypen zulässig, die in C++-standardbibliothekscontainer eingefügt werden.

[Vorgehensweise: Umwandeln einer .Net-Auflistung in einen STL/CLR-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
Beschreibt, wie eine .NET-Auflistung in einen STL/CLR-Container konvertiert wird.

[Vorgehensweise: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
Beschreibt, wie ein STL/CLR-Container in eine .NET-Auflistung konvertiert wird.

[Vorgehensweise: Einen STL/CLR-Container einer Assembly verfügbar machen](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
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
