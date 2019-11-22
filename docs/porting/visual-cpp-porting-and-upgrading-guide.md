---
title: Leitfaden C++ zum Portieren und Aktualisieren von Microsoft
description: Aktualisieren Sie C++ Microsoft-Code auf die neueste Version von Visual Studio.
ms.date: 11/18/2019
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.topic: overview
ms.openlocfilehash: 723879ad03b9b66c7490804e890f07d6d55e9dae
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303342"
---
# <a name="microsoft-c-porting-and-upgrading-guide"></a>Leitfaden C++ zum Portieren und Aktualisieren von Microsoft

Dieser Artikel enthält eine Anleitung zum Aktualisieren von C++ Microsoft-Code auf die neueste Version von Visual Studio. Für Projekte, die in Visual Studio 2010 bis 2015 erstellt wurden, öffnen Sie einfach das Projekt in Visual Studio 2019. Sie können ein Visual Studio 2008-Projekt oder ein früheres Projekt in zwei Schritten aktualisieren. Verwenden Sie Visual Studio 2010, um das Projekt zuerst in das MSBuild-Format zu konvertieren. Öffnen Sie dann das Projekt in Visual Studio 2019. Umfassende Anweisungen finden Sie unter [aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md).

Die Toolsets in Visual Studio 2015, Visual Studio 2017 und Visual Studio 2019 sind binär kompatibel. Jetzt können Sie auf eine neuere Version des Compilers aktualisieren, ohne die Bibliotheksabhängigkeiten aktualisieren zu müssen. Weitere Informationen finden [ C++ Sie unter binäre Kompatibilität 2015-2019](binary-compat-2015-2017.md).

Wenn Sie Projekte aktualisieren, die Open Source-Bibliotheken verwenden oder auf mehreren Plattformen ausgeführt werden sollen, empfiehlt es sich, zu einem cmake-basierten Projekt zu migrieren. Weitere Informationen finden Sie unter [cmake-Projekte in Visual Studio](../build/cmake-projects-in-visual-studio.md) .

## <a name="reasons-to-upgrade-c-code"></a>Gründe für UpgradeCode C++

Wenn eine Legacy Anwendung in einer sicheren Umgebung zufriedenstellend ausgeführt wird und nicht aktiv ist, ist es möglicherweise nicht sinnvoll, ein Upgrade durchzuführen. In diesen Fällen sollten Sie jedoch ein Upgrade in Erwägung gezogen haben: für Ihre Anwendung ist eine laufende Wartung erforderlich. Oder Sie erstellen eine neue Featureentwicklung oder nehmen Leistungs-oder Sicherheitsverbesserungen vor. Ein Upgrade bietet folgende Vorteile:

- Der gleiche Code kann schneller ausgeführt werden, da wir die Compileroptimierungen verbessert haben.

- Dank C++ moderner Features und Programmierverfahren werden viele häufige Fehler Fehler vermieden und Code erzeugt, der wesentlich einfacher zu verwalten ist als ältere Idiome im C-Stil.

- Buildzeiten sind aufgrund von Leistungsverbesserungen im Compiler und Linker schneller.

- Bessere Einhaltung von Standards. Mit der [/permissive-](../build/reference/permissive-standards-conformance.md) -Compileroption können Sie Code identifizieren, der nicht C++ dem aktuellen Standard entspricht.

- Bessere Lauf Zeit Sicherheit, einschließlich sichereren Funktionen der [C-Lauf Zeit Bibliothek](../c-runtime-library/security-features-in-the-crt.md) . Und, Compilerfunktionen wie [Wächter Überprüfung](../build/reference/guard-enable-guard-checks.md) und Adress bertizer (neu in Visual Studio 2019 Version 16,4).

## <a name="multitargeting-vs-upgrading"></a>Multiadressieren und Upgrade

Möglicherweise ist ein Upgrade Ihrer Codebasis auf ein neues Toolset keine Option für Sie. Sie können weiterhin das neueste Visual Studio zum Erstellen und Bearbeiten von Projekten verwenden, die ältere Toolsets und Bibliotheken verwenden. In Visual Studio 2019 können Sie Features wie die folgenden nutzen:

- moderne Statische Analysetools, einschließlich der C++ wichtigsten Leitfäden und clang-bereinigen, um potenzielle Probleme im Quellcode zu identifizieren.

- die automatische Formatierung gemäß ihrer Wahl moderner Stile kann dazu beitragen, dass Legacy Code viel besser lesbar wird.

Weitere Informationen finden Sie unter [Use native multi-targeting in Visual Studio to build old projects (Verwenden der nativen Festlegung von Zielversionen in Visual Studio, um alte Projekte zu erstellen)](use-native-multi-targeting.md).

## <a name="in-this-section"></a>In diesem Abschnitt

|Titel|Beschreibung|
|-----------|-----------------|
|[Aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Aktualisieren Ihrer Codebasis auf Visual Studio 2019 und v142 des Compilers.|
|[IDE-Tools für C++ die Aktualisierung von Code](ide-tools-for-upgrading-code.md)|Nützliche IDE-Features, die den Upgradeprozess unterstützen.|
|[C++binäre Kompatibilität 2015-2019](binary-compat-2015-2017.md)|Verwenden Sie V140-und v141-Bibliotheken unverändert aus v142-Projekten.|
|[Verwenden von nativen Zielversionen in Visual Studio, um alte Projekte zu erstellen](use-native-multi-targeting.md)|Verwenden Sie Visual Studio 2019 mit älteren Compilern und Bibliotheken.|
|[Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md)|Eine Liste aller Änderungen in den Microsoft C++ -Bibliotheken und-Buildtools von Visual Studio 2003 bis 2015, die möglicherweise Änderungen im Code erfordern.|
|[Visual C++: Neuerungen von 2003 bis 2015](visual-cpp-what-s-new-2003-through-2015.md)|Alle neuen Informationen zu Microsoft C++ von Visual Studio 2003 bis Visual Studio 2015.|
|[Portieren und Aktualisieren: Beispiele und Fallstudien](porting-and-upgrading-examples-and-case-studies.md)|Für diesen Abschnitt wurden mehrere Beispiele und Anwendungen portiert und aktualisiert und die Erfahrungen und Ergebnisse dieses Vorgangs erläutert. Diese Artikel vermitteln Ihnen einen Eindruck davon, was mit dem portieren und Upgradeprozess verbunden ist. Im Verlauf des Vorgangs werden immer wieder Tipps und Tricks für das Upgrade gegeben und erläutert, wie bestimmte Fehler korrigiert wurden.|
|[Portieren auf die universelle Windows-Plattform](porting-to-the-universal-windows-platform-cpp.md)|Enthält Informationen zum Portieren von Code für Windows 10|
|[Einführung in Visual C++ für UNIX-Benutzer](introduction-to-visual-cpp-for-unix-users.md)|Enthält Informationen für UNIX-Benutzer, die noch keine Erfahrungen mit Visual C++ sammeln konnten und die Anwendung produktiv einsetzen möchten.|
|[Ausführen von Linux-Programmen unter Windows](porting-from-unix-to-win32.md)|Erläutert die Optionen zum Migrieren von UNIX-Anwendungen zu Windows.|

## <a name="see-also"></a>Siehe auch

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[Neuerungen beim C++-Compiler in Visual Studio](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Verbesserungen der C++-Konformität in Visual Studio](../overview/cpp-conformance-improvements.md)<br/>
