---
title: "Visual C++-Handbuch: Portieren und Aktualisieren"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
caps.latest.revision: 8
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++-Handbuch: Portieren und Aktualisieren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält eine Anleitung zum Aktualisieren von Visual C\+\+\-Code.  Dazu gehört dafür zu sorgen, dass der Code in einer neueren Version der Tools fehlerfrei kompiliert und ausgeführt wird, und dass die Vorteile neuer Sprach\- und Visual Studio\-Features genutzt werden.  Dieses Thema enthält außerdem Informationen zum Migrieren von Legacy\-Apps zu moderneren Plattformen.  
  
## Gründe für ein Upgrade von Visual C\+\+\-Code  
 Eine Codeupgrade bietet die folgenden Vorteile:  
  
-   Schnellerer Code aufgrund verbesserter Compileroptimierungen.  
  
-   Schnellere Builds aufgrund von Leistungsverbesserungen im Compiler selbst.  
  
-   Sprachfeatures.  In Visual C\+\+ sind jetzt viele Features aus den neueren C\+\+\-Standards implementiert.  
  
-   Bessere Sicherheit.  Sicherheitsfeatures wie Wächterüberprüfung.  
  
### Portieren von Code  
 Betrachten Sie bei einem Upgrade zunächst den Code und die Projekte Ihrer Anwendung.  Wurde die Anwendung mit Visual Studio erstellt?  Wenn ja, identifizieren Sie die betroffenen Projekte.  Verfügen Sie über benutzerdefinierte Buildskripts?  Wenn Sie benutzerdefinierte Buildskripts anstelle des Buildsystems von Visual Studio verwenden, ist das Upgrade mit größerem Aufwand verbunden, da Sie Ihre Projektdateien und Buildeinstellungen nicht automatisch von Visual Studio aktualisieren lassen und dadurch Zeit sparen können.  
  
 Das Buildsystem\- und Projektdateiformat in Visual Studio wurde von „vcbuild“ in Versionen bis Visual Studio 2008 in „MSBuild“ in Versionen ab Visual Studio 2010 geändert.  Bei einem Upgrade von einer Version vor 2010 und einem stark angepassten Buildsystem erfordert das Upgrade möglicherweise mehr Arbeit.  Bei einem Upgrade von Visual Studio 2010 oder höher verwenden Ihre Projekte bereits MSBuild, daher ist ein Upgrade des Projekts und Builds für Ihre Anwendung einfacher.  
  
 Wenn Sie nicht das Buildsystem von Visual Studio verwenden, sollten Sie erwägen, ein Upgrade auf MSBuild durchzuführen.  Wenn Sie auf MSBuild aktualisieren, sind zukünftige Upgrades eventuell weniger aufwendig, und Dienste wie z. B. Visual Studio Online können einfacher verwendet werden.  MSBuild unterstützt alle von Visual Studio unterstützten Zielplattformen.  
  
### Portieren von Visual Studio\-Projekten  
 Bei größeren Projekten empfiehlt es sich, jeweils nur eine Visual Studio\-Version zu aktualisieren, da andernfalls möglicherweise nur schwer feststellbar ist, in welcher Version eine bestimmte wichtige Änderung eingeführt wurde, die sich auf Ihren Code ausgewirkt hat.  
  
 Um mit dem Upgrade eines Projekts oder einer Projektmappe zu beginnen, öffnen Sie einfach die Projektmappe in der neuen Visual Studio\-Version, und folgen Sie den Anweisungen zum Starten des Upgrades.  Wenn Sie ein Projekt aktualisieren, erhalten Sie einen Upgradebericht, der auch als „UpgradeLog.htm“ in Ihrem Projektordner gespeichert wird.  Der Upgradebericht enthält eine Zusammenfassung der während des Upgradevorgangs aufgetretenen Probleme sowie einige Informationen über vorgenommene Änderungen oder Probleme, die nicht automatisch behoben werden konnten.  
  
1.  Projekteigenschaften  
  
2.  Includedateien  
  
3.  Code, der aufgrund von geänderter Compilerkonformität nicht mehr fehlerfrei kompiliert wird  
  
4.  Code, der sich auf Visual Studio\- oder Windows\-Features stützt, die nicht mehr verfügbar sind, oder Headerdateien, die entweder in einer Standardinstallation von Visual Studio nicht enthalten sind oder aus dem Produkt entfernt wurden  
  
5.  Code, der aufgrund von Änderungen an APIs nicht mehr kompiliert wird, wie z. B. umbenannte APIs, geänderte Funktionssignaturen oder veraltete Funktionen  
  
6.  Code, der aufgrund von Änderungen bei der Diagnose nicht mehr kompiliert wird, wie z. B. Warnungen, die jetzt Fehler sind  
  
7.  Linkerfehler aufgrund von geänderten Bibliotheken, insbesondere bei Verwendung von \/NODEFAULTLIB  
  
8.  Laufzeitfehler oder unerwartete Ergebnisse aufgrund von Verhaltensänderungen  
  
9. Fehler aufgrund von Fehlern, die in den Tools eingeführt wurden  Wenn ein Problem auftritt, melden Sie dies dem Visual C\+\+\-Team über die normalen Supportkanäle oder mithilfe des [Visual Studio Feedback Centers](http://connect.microsoft.com/VisualStudio/Feedback).  
  
 Zusätzlich zu Änderungen, die Sie aufgrund von Compilerfehlern nicht vermeiden können, sind einige Änderungen bei einem Upgrade optional, wie z. B.:  
  
1.  Neue Warnungen können bedeuten, dass Sie Ihren Code bereinigen müssen.  Je nach der spezifischen Diagnose können hierdurch die Portabilität, die Einhaltung von Standards und die Sicherheit des Codes verbessert werden.  
  
2.  Sie können auch neue Compilerfeatures nutzen, wie z. B. die Compileroption [\/guard:cf \(Ablaufsteuerungsschutz aktivieren\)](../build/reference/guard-enable-control-flow-guard.md), die Prüfungen für nicht autorisierte Codeausführung hinzugefügt.  
  
3.  Sie können Code aktualisieren, um neue Sprachfeatures zu nutzen, die den Code vereinfachen oder die Leistung Ihrer Programme verbessern. Sie können Code auch aktualisieren, um moderne Bibliotheken zu verwenden und modernen Standards und bewährten Methoden zu entsprechen.  
  
 Sobald Sie das Projekt aktualisiert \(und getestet\) haben, können Sie den Code noch weiter verbessern oder die zukünftige Ausrichtung des Code planen oder sogar die Architektur des Projekts überdenken.  Muss Ihr Code auch auf anderen Plattformen ausgeführt werden können?  Wenn ja, welche Plattformen sind dies?  C\+\+ ist eine standardisierte Sprache, die speziell für Portabilität und plattformübergreifende Entwicklung konzipiert wurde, und doch ist der Code für viele Windows\-Anwendungen eng an die Windows\-Plattform gebunden.  Möchten Sie Ihren Code umgestalten, um die Bestandteile herauszutrennen, die enger an die Windows\-Plattform gebunden sind?  
  
 Was ist mit der Benutzeroberfläche?  Wenn Sie MFC verwenden, empfiehlt sich ggf. eine Aktualisierung der Benutzeroberfläche.  Verwenden Sie eines der neueren MFC\-Features, die in 2008 als Feature Pack eingeführt wurden?  Wenn Sie einfach nur das Erscheinungsbild Ihrer App moderner gestalten möchten, ohne die gesamte App neu zu schreiben, verwenden Sie die Menüband\-APIs in MFC oder einige der neuen Features von MFC.  
  
 Um eine neue Windows\-Desktopbenutzeroberfläche hinzuzufügen, können Sie C\+\+\/CX \(Komponentenerweiterungen\) verwenden oder verwalteten Code in C\# und eine Interoperabilitätsebene in C\+\+\/CLI hinzufügen, um C\# mit Ihrem systemeigenen Code zu verbinden.  
  
 Vielleicht haben sich auch Ihre Anforderungen geändert, oder Sie können absehen, dass Sie zukünftig auch Code für andere Zielplattformen als Windows\-Desktop entwickeln müssen, wie z. B. Windows Phone\- oder Android\-Geräte.  Sie können den Code Ihrer Benutzeroberfläche in eine plattformübergreifende Benutzeroberflächenbibliothek portieren.  Mit diesen Benutzeroberflächen\-Frameworks können Sie Code für mehrere Zielgeräte schreiben und trotzdem weiterhin Visual Studio und den Visual Studio\-Debugger als Entwicklungsumgebung verwenden.  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Aktualisieren von Projekten von früheren Versionen von Visual C\+\+](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)|Erläutert, wie in früheren Versionen von Visual C\+\+ erstellte Projekte verwendet werden.|  
|[Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)|Eine Liste von Änderungen in den Visual C\+\+\-Bibliotheken und \-Buildtools, die eventuell Änderungen an Ihrem Code erfordern.|  
|[Portieren und Aktualisieren: Beispiele und Fallstudien](../porting/porting-and-upgrading-examples-and-case-studies.md)|Für diesen Abschnitt wurden mehrere Beispiele und Anwendungen portiert und aktualisiert und die Erfahrungen und Ergebnisse dieses Vorgangs erläutert.  Dieser Abschnitt soll Ihnen eine Vorstellung davon vermitteln, mit welchen Aufgaben und Problemen Sie beim Portieren und Aktualisieren rechnen müssen.  Im Verlauf des Vorgangs werden immer wieder Tipps und Tricks für das Upgrade gegeben und erläutert, wie bestimmte Fehler korrigiert wurden.|  
|[Portieren auf die universelle Windows\-Plattform](../porting/porting-to-the-universal-windows-platform-cpp.md)|Enthält Informationen zum Portieren von Code für Windows 10|  
|[Einführung in Visual C\+\+ für UNIX\-Benutzer](../porting/introduction-to-visual-cpp-for-unix-users.md)|Enthält Informationen für UNIX\-Benutzer, die noch keine Erfahrungen mit [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sammeln konnten und die Anwendung produktiv einsetzen möchten.|  
|[Portieren von UNIX auf Win32](../porting/porting-from-unix-to-win32.md)|Erläutert die Optionen zum Migrieren von UNIX\-Anwendungen zu Windows.|  
|[Einführung in die C\+\+\/CLI\-Migration](../dotnet/cpp-cli-migration-primer.md)|Erläutert ausführlich das Upgrade der Managed Extensions for C\+\+\-Syntax auf die neue Syntax.  Weitere Informationen finden Sie unter [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).|  
  
## Siehe auch  
 [Wichtige Änderungen in Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)