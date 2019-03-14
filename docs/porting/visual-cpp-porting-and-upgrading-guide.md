---
title: 'Visual C++-Handbuch: Portieren und Aktualisieren'
ms.date: 09/18/2018
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.openlocfilehash: 1b3f7142b5240d8b4a94040d5cda7d033e50e39d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57752427"
---
# <a name="visual-c-porting-and-upgrading-guide"></a>Visual C++-Handbuch: Portieren und Aktualisieren

Dieses Thema enthält eine Anleitung zum Aktualisieren von Visual C++-Code. Dazu gehört dafür zu sorgen, dass der Code in einer neueren Version der Tools fehlerfrei kompiliert und ausgeführt wird, und dass die Vorteile neuer Sprach- und Visual Studio-Features genutzt werden. Dieses Thema enthält außerdem Informationen zum Migrieren von Legacy-Apps zu moderneren Plattformen.

## <a name="reasons-to-upgrade-visual-c-code"></a>Gründe für ein Upgrade von Visual C++-Code

Eine Codeupgrade bietet die folgenden Vorteile:

- Schnellerer Code aufgrund verbesserter Compileroptimierungen.

- Schnellere Builds aufgrund von Leistungsverbesserungen im Compiler selbst.

- Verbesserte Übereinstimmung mit Standards. In Visual C++ sind jetzt viele Funktionen aus den neuesten C++-Standards implementiert.

- Bessere Sicherheit. Sicherheitsfunktionen wie Wächterüberprüfung.

### <a name="porting-your-code"></a>Portieren von Code

Betrachten Sie bei einem Upgrade zunächst den Code und die Projekte Ihrer Anwendung. Wurde die Anwendung mit Visual Studio erstellt? Wenn ja, identifizieren Sie die betroffenen Projekte.  Verfügen Sie über benutzerdefinierte Buildskripts? Wenn Sie benutzerdefinierte Buildskripts anstelle des Buildsystems von Visual Studio verwenden, ist das Upgrade mit größerem Aufwand verbunden, da Sie Ihre Projektdateien und Buildeinstellungen nicht automatisch von Visual Studio aktualisieren lassen und dadurch Zeit sparen können.

Das Buildsystem- und Projektdateiformat in Visual Studio wurde von „vcbuild“ in Versionen bis Visual Studio 2008 in „MSBuild“ in Versionen ab Visual Studio 2010 geändert. Bei einem Upgrade von einer Version vor 2010 und einem stark angepassten Buildsystem erfordert das Upgrade möglicherweise mehr Arbeit. Bei einem Upgrade von Visual Studio 2010 oder höher verwenden Ihre Projekte bereits MSBuild, daher ist ein Upgrade des Projekts und Builds für Ihre Anwendung einfacher.

Wenn Sie nicht das Buildsystem von Visual Studio verwenden, sollten Sie erwägen, ein Upgrade auf MSBuild durchzuführen. Wenn Sie auf MSBuild aktualisieren, sind zukünftige Upgrades eventuell weniger aufwendig, und Dienste wie z. B. Visual Studio Online können einfacher verwendet werden. MSBuild unterstützt alle von Visual Studio unterstützten Zielplattformen.

### <a name="porting-visual-studio-projects"></a>Portieren von Visual Studio-Projekten

Um mit dem Upgrade eines Projekts oder einer Projektmappe zu beginnen, öffnen Sie einfach die Projektmappe in der neuen Visual Studio-Version, und folgen Sie den Anweisungen zum Starten des Upgrades.  Wenn Sie ein Projekt aktualisieren, erhalten Sie einen Upgradebericht, der auch als „UpgradeLog.htm“ in Ihrem Projektordner gespeichert wird. Der Upgradebericht enthält eine Zusammenfassung der während des Upgradevorgangs aufgetretenen Probleme sowie einige Informationen über vorgenommene Änderungen oder Probleme, die nicht automatisch behoben werden konnten.

1. Projekteigenschaften

2. Includedateien

3. Code, der aufgrund von verbesserter Compilerkonformität oder Änderungen am Standard nicht mehr fehlerfrei kompiliert wird

4. Code, der sich auf Visual Studio- oder Windows-Funktionen stützt, die nicht mehr verfügbar sind, oder Headerdateien, die entweder in einer Standardinstallation von Visual Studio nicht enthalten sind oder aus dem Produkt entfernt wurden

5. Code, der aufgrund von Änderungen an APIs nicht mehr kompiliert wird, wie z. B. umbenannte APIs, geänderte Funktionssignaturen oder veraltete Funktionen

6. Code, der aufgrund von Änderungen bei der Diagnose nicht mehr kompiliert wird, wie z. B. Warnungen, die jetzt Fehler sind

7. Linkerfehler aufgrund von geänderten Bibliotheken, insbesondere bei Verwendung von /NODEFAULTLIB

8. Laufzeitfehler oder unerwartete Ergebnisse aufgrund von Verhaltensänderungen

9. Fehler aufgrund von Fehlern, die in den Tools eingeführt wurden Wenn ein Problem auftritt, melden Sie dies dem Visual C++-Team über die normalen Supportkanäle oder das [Visual Studio Feedback Center](http://connect.microsoft.com/VisualStudio/Feedback).

Zusätzlich zu Änderungen, die Sie aufgrund von Compilerfehlern nicht vermeiden können, sind einige Änderungen bei einem Upgrade optional, wie z. B.:

1. Neue Warnungen können bedeuten, dass Sie Ihren Code bereinigen müssen. Je nach der spezifischen Diagnose können hierdurch die Portabilität, die Einhaltung von Standards und die Sicherheit des Codes verbessert werden.

2. Sie können auch neue Compilerfunktionen nutzen, wie z.B. die Compileroption [/guard:cf (Ablaufsteuerungsschutz aktivieren)](../build/reference/guard-enable-control-flow-guard.md), die Prüfungen für nicht autorisierte Codeausführung hinzugefügt.

3. Sie können Code aktualisieren, um neue Sprachfunktionen zu nutzen, die den Code vereinfachen oder die Leistung Ihrer Programme verbessern. Sie können Code auch aktualisieren, um moderne Bibliotheken zu verwenden und modernen Standards und bewährten Methoden zu entsprechen.

Sobald Sie das Projekt aktualisiert und getestet haben, können Sie den Code noch weiter verbessern oder die künftige Ausrichtung des Codes planen oder sogar die Architektur des Projekts überdenken. Fallen dafür fortlaufende Entwicklungsaufgaben an? Muss Ihr Code auch auf anderen Plattformen ausgeführt werden können?  Wenn ja, welche Plattformen sind dies?  C++ ist eine standardisierte Sprache, die speziell für Portabilität und plattformübergreifende Entwicklung konzipiert wurde, und doch ist der Code für viele Windows-Anwendungen eng an die Windows-Plattform gebunden. Möchten Sie Ihren Code umgestalten, um die Bestandteile herauszutrennen, die enger an die Windows-Plattform gebunden sind?

Was ist mit der Benutzeroberfläche? Wenn Sie MFC verwenden, empfiehlt sich ggf. eine Aktualisierung der Benutzeroberfläche. Verwenden Sie eines der neueren MFC-Features, die in 2008 als Feature Pack eingeführt wurden? Wenn Sie einfach nur das Erscheinungsbild Ihrer App moderner gestalten möchten, ohne die gesamte App neu zu schreiben, verwenden Sie die Menüband-APIs in MFC oder einige der neuen Funktionen von MFC.

Wenn Sie Ihr Programm mit einer XAML-Benutzeroberfläche versehen, jedoch keine UWP-App erstellen möchten, können Sie C# mit WPF einsetzen, um die UI-Ebene zu erstellen und Ihre standardmäßige C++-Logik in DLLs umzugestalten. Erstellen Sie eine Interoperabilitätsebene in C++/CLI, um C# mit Ihrem nativen Code zu verbinden. Eine weitere Option ist die Erstellung einer UWP-App mithilfe von [C++/CX](https://msdn.microsoft.com/library/windows/apps/xaml/hh699871.aspx) oder [C++/WinRT](https://github.com/microsoft/cppwinrt). Unter Windows 10 können Sie den [Desktop App Converter](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) nutzen, um Ihre vorhandene Desktopanwendung als UWP-App zu packen, ohne Code ändern zu müssen.

Vielleicht haben sich auch Ihre Anforderungen geändert, oder Sie können absehen, dass Sie zukünftig auch Code für andere Zielplattformen als Windows-Desktop entwickeln müssen, wie z. B. Windows Phone- oder Android-Geräte. Sie können den Code Ihrer Benutzeroberfläche in eine plattformübergreifende Benutzeroberflächenbibliothek portieren. Mit diesen Benutzeroberflächen-Frameworks können Sie Code für mehrere Zielgeräte schreiben und trotzdem weiterhin Visual Studio und den Visual Studio-Debugger als Entwicklungsumgebung verwenden.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Aktualisieren von Projekten von früheren Versionen von Visual C++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Erläutert, wie in früheren Versionen von Visual C++ erstellte Projekte verwendet werden.|
|[Neuerungen beim Visual C++-Compiler in Visual Studio 2017 RC](../what-s-new-for-visual-cpp-in-visual-studio.md)|Änderungen an IDE und Tools zwischen Visual Studio 2015 und Visual Studio 2017|
|[Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual C++ 2017](../cpp-conformance-improvements-2017.md)|Verbesserungen bei der Übereinstimmung mit Standards zwischen Visual Studio 2015 und Visual Studio 2017|
|[Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md)|Eine Liste aller Änderungen an den Visual C++-Bibliotheken und -Buildtools von Visual Studio 2003 bis 2015, die eventuell Änderungen an Ihrem Code erfordern.|
|[Visual C++: Neuerungen von 2003 bis 2015](visual-cpp-what-s-new-2003-through-2015.md)|Alle Informationen zu Neuerungen bei Visual C++ von Visual Studio 2003 bis Visual Studio 2015.|
|[Portieren von Drittanbieterbibliotheken](porting-third-party-libraries.md)|Verwenden des Befehlszeilentools **vcpkg** zum Portieren älterer Open-Source-Bibliotheken zu Versionen, die mit neueren Visual C++-Toolsets kompiliert wurde.|
|[Portieren und Aktualisieren: Beispiele und Fallstudien](porting-and-upgrading-examples-and-case-studies.md)|Für diesen Abschnitt wurden mehrere Beispiele und Anwendungen portiert und aktualisiert und die Erfahrungen und Ergebnisse dieses Vorgangs erläutert. Dieser Abschnitt soll Ihnen eine Vorstellung davon vermitteln, mit welchen Aufgaben und Problemen Sie beim Portieren und Aktualisieren rechnen müssen. Im Verlauf des Vorgangs werden immer wieder Tipps und Tricks für das Upgrade gegeben und erläutert, wie bestimmte Fehler korrigiert wurden.|
|[Portieren auf die universelle Windows-Plattform](porting-to-the-universal-windows-platform-cpp.md)|Enthält Informationen zum Portieren von Code für Windows 10|
|[Einführung in Visual C++ für UNIX-Benutzer](introduction-to-visual-cpp-for-unix-users.md)|Enthält Informationen für UNIX-Benutzer, die noch keine Erfahrungen mit Visual C++ sammeln konnten und die Anwendung produktiv einsetzen möchten.|
|[Portieren von UNIX auf Win32](porting-from-unix-to-win32.md)|Erläutert die Optionen zum Migrieren von UNIX-Anwendungen zu Windows.|

## <a name="see-also"></a>Siehe auch

[Visual C++](../visual-cpp-in-visual-studio.md)
