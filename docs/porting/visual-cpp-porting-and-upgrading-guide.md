---
title: Leitfaden C++ zum Portieren und Aktualisieren von Microsoft
description: Aktualisieren Sie C++ Microsoft-Code auf die neueste Version von Visual Studio.
ms.date: 10/29/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: d67c2665574242a46d697f6e9f24321556146958
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625679"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Leitfaden C++ zum Portieren und Aktualisieren von Microsoft

Dieses Thema enthält eine Anleitung zum Aktualisieren von C++ Microsoft-Code auf die neueste Version von Visual Studio. Wenn Sie ein Upgrade von einem Projekt durchführen, das in Visual Studio 2008 oder einer früheren Version erstellt wurde, müssen Sie zunächst Visual Studio 2010 verwenden, um das Projekt in das MSBuild-Format zu konvertieren. Öffnen Sie dann das Projekt in Visual Studio 2019. Für Projekte, die in Visual Studio 2010 bis 2015 erstellt wurden, öffnen Sie einfach das Projekt in Visual Studio 2019. Umfassende Anweisungen finden Sie unter [aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

Die Toolsets in Visual Studio 2015, Visual Studio 2017 und Visual Studio 2019 sind binär kompatibel, sodass Sie auf eine neuere Version des Compilers aktualisieren können, ohne Bibliotheksabhängigkeiten aktualisieren zu müssen. Weitere Informationen finden [ C++ Sie unter binäre Kompatibilität zwischen 2015 und 2019](binary-compat-2015-2017.md).

Wenn Sie Projekte aktualisieren, die Open Source-Bibliotheken verwenden oder auf mehreren Plattformen ausgeführt werden sollen, empfiehlt es sich, zu einem cmake-basierten Projekt zu migrieren. Weitere Informationen finden Sie unter [cmake-Projekte in Visual Studio](../build/cmake-projects-in-visual-studio.md) .

## <a name="reasons-to-upgrade-c-code"></a>Gründe für UpgradeCode C++

Wenn eine Legacy Anwendung in einer sicheren Umgebung zufriedenstellend ausgeführt wird und sich nicht in der aktiven Entwicklung befindet, ist es möglicherweise nicht sinnvoll, ein Upgrade durchzuführen. Wenn eine Anwendung jedoch eine laufende Wartung oder eine neue Featureentwicklung, einschließlich Leistungs-oder Sicherheitsverbesserungen, erfordert, sollten Sie in Erwägung gezogen, den Code aus einem der folgenden Gründe zu aktualisieren:

- Der gleiche Code kann aufgrund verbesserter Compileroptimierungen schneller ausgeführt werden.

- Dank C++ moderner Features und Programmierverfahren werden viele häufige Fehler Fehler vermieden, und es ist weitaus einfacher, diese älteren Ausdrücke im C-Stil zu verwalten.

- Buildzeiten sind aufgrund von Leistungsverbesserungen im Compiler und Linker erheblich schneller.

- Bessere Einhaltung von Standards. Mit der [/permissive-](../build/reference/permissive-standards-conformance.md) -Compileroption können Sie Code identifizieren, der zuvor vom Microsoft C++ -Compiler zugelassen wurde, jedoch nicht dem C++ aktuellen Standard entspricht.

- Bessere Lauf Zeit Sicherheit, einschließlich sichereren Funktionen der [C-Lauf Zeit Bibliothek]() und Compilerfunktionen wie [Wächter Überprüfung](../build/reference/guard-enable-guard-checks.md) und Adress bertizer (Visual Studio 2019 Version 16,4).

## <a name="multitargeting-vs-upgrading"></a>Multiadressieren und Upgrade

Wenn das Upgrade Ihrer Codebasis auf ein neues Toolset nicht möglich ist, können Sie weiterhin eine aktuelle Version von Visual Studio verwenden, um Projekte zu erstellen und zu bearbeiten, die mit älteren Toolsets und Bibliotheken kompiliert werden. In Visual Studio 2019 können Sie Features wie die folgenden nutzen:

- moderne Statische Analysetools, einschließlich der C++ wichtigsten Leitfäden und clang-bereinigen, um potenzielle Probleme im Quellcode zu identifizieren.

- die automatische Formatierung gemäß ihrer Wahl moderner Stile kann dazu beitragen, dass Legacy Code viel besser lesbar wird.

Weitere Informationen finden Sie unter [Use native multi-targeting in Visual Studio to build old projects (Verwenden der nativen Festlegung von Zielversionen in Visual Studio, um alte Projekte zu erstellen)](use-native-multi-targeting.md).

## <a name="in-this-section"></a>In diesem Abschnitt

|Titel|Beschreibung|
|-----------|-----------------|
|[Aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Aktualisieren Ihrer Codebasis auf Visual Studio 2019 und v142 des Compilers.|
|[C++Binäre Kompatibilität zwischen 2015 und 2019](binary-compat-2015-2017.md)|Verwenden Sie V140-Bibliotheken unverändert von v142-Projekten.|
|[Verwenden von nativen Zielversionen in Visual Studio, um alte Projekte zu erstellen](use-native-multi-targeting.md)|Verwenden Sie Visual Studio 2019 mit älteren Compilern und Bibliotheken.|
|[Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md)|Eine Liste aller Änderungen in den Microsoft C++ -Bibliotheken und-Buildtools von Visual Studio 2003 bis 2015, die möglicherweise Änderungen im Code erfordern.|
|[Visual C++: Neuerungen von 2003 bis 2015](visual-cpp-what-s-new-2003-through-2015.md)|Alle neuen Informationen zu Microsoft C++ von Visual Studio 2003 bis Visual Studio 2015.|
|[Portieren und Aktualisieren: Beispiele und Fallstudien](porting-and-upgrading-examples-and-case-studies.md)|Für diesen Abschnitt wurden mehrere Beispiele und Anwendungen portiert und aktualisiert und die Erfahrungen und Ergebnisse dieses Vorgangs erläutert. Dieser Abschnitt soll Ihnen eine Vorstellung davon vermitteln, mit welchen Aufgaben und Problemen Sie beim Portieren und Aktualisieren rechnen müssen. Im Verlauf des Vorgangs werden immer wieder Tipps und Tricks für das Upgrade gegeben und erläutert, wie bestimmte Fehler korrigiert wurden.|
|[Portieren auf die universelle Windows-Plattform](porting-to-the-universal-windows-platform-cpp.md)|Enthält Informationen zum Portieren von Code für Windows 10|
|[Einführung in Visual C++ für UNIX-Benutzer](introduction-to-visual-cpp-for-unix-users.md)|Enthält Informationen für UNIX-Benutzer, die noch keine Erfahrungen mit Visual C++ sammeln konnten und die Anwendung produktiv einsetzen möchten.|
|[Ausführen von Linux-Programmen unter Windows](porting-from-unix-to-win32.md)|Erläutert die Optionen zum Migrieren von UNIX-Anwendungen zu Windows.|

## <a name="see-also"></a>Siehe auch

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[Neuerungen beim C++-Compiler in Visual Studio](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Verbesserungen der C++-Konformität in Visual Studio](../overview/cpp-conformance-improvements.md)<br/>
