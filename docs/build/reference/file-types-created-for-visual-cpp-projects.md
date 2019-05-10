---
title: Für Visual Studio-Datei erstellt C++ Projekte
ms.date: 04/08/2019
helpviewer_keywords:
- header files [C++], Visual Studio projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual Studio C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
ms.openlocfilehash: 42040854b7a038ebe32d67e305c947d095d5391a
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446288"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Für Visual Studio C++-Projekte erstellte Dateitypen

Viele Arten von Dateien sind mit Visual Studio-Projekten für klassische desktopcomputeranwendungen verknüpft. Die in Ihrem Projekt tatsächlich enthaltenen Dateien sind vom Projekttyp und von Ihnen mithilfe eines Assistenten ausgewählten Optionen abhängig.

- [Projekt- und Projektmappendateien](project-and-solution-files.md)

- [CLR Projects (CLR-Projekte)](files-created-for-clr-projects.md)

- [ATL-Programm oder Steuern von Quell- und Headerdateien](atl-program-or-control-source-and-header-files.md)

- [MFC-Programm oder Steuern von Quell- und Headerdateien](mfc-program-or-control-source-and-header-files.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

- [Ressourcendateien](resource-files-cpp.md)

- [Hilfedateien (WinHelp)](help-files-winhelp.md)

- [Hinweisdateien](hint-files.md)

Wenn Sie Visual Studio-Projekt erstellen, können Sie ihn in eine neue Projektmappe erstellen oder Sie können ein Projekt zu einer vorhandenen Projektmappe hinzufügen. Nicht triviale Anwendungen werden häufig mit mehreren Projekten in einer Projektmappe entwickelt.

Projekte generieren für gewöhnlich entweder eine EXE- oder eine DLL-Datei. Projekte können voneinander abhängig sein; während des Buildprozesses überprüft Visual Studio-Umgebung Abhängigkeiten in und zwischen Projekten. Jedes Projekt hat in der Regel die Core-Quellcodes. Je nach Art des Projekts kann es viele andere Dateien, die verschieden Aspekte des Projekts verfügen. Die Inhalte dieser Dateien werden durch die Dateierweiterung angegeben. Die Visual Studio-Entwicklungsumgebung verwendet die Dateierweiterungen, um zu bestimmen, wie die Dateiinhalte während eines Builds verarbeitet werden.

In der folgende Tabelle wird gemeinsame Dateien in einem Visual Studio-Projekt, und sie mit der Dateierweiterung identifiziert.

|Dateierweiterung|Typ|Inhalt|
|--------------------|----------|--------------|
|.asmx|Quelle|Bereitstellungsdatei.|
|.asp|Source|Aktive Serverseitendatei|
|.atp|Projekt|Anwendungsvorlagen-Projektdatei.|
|.bmp, .dib, .gif, .jpg, .jpeg, .png|Ressource|Allgemeine Bilddateien.|
|.bsc|Kompilieren|Browsercodedatei.|
|.cpp, .c|Source|Haupt-Quellcodedateien für Ihre Anwendung.|
|.cur|Ressource|Cursorbitmap-Grafikdatei.|
|.dbp|Projekt|Datenbankprojektdatei.|
|.disco|Source|Dynamische Ermittlungsdokumentdatei. Verarbeitet die XML-Webdienstermittlung.|
|.exe, .dll|Projekt|Ausführbare oder Dynamic-Link Library-Dateien.|
|H|Source|Headerdatei (include).|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Ressource|Allgemeine Webdateien.|
|.HxC|Projekt|Hilfsprojektdatei.|
|.ico|Ressource|Symbolbitmap-Grafikdatei.|
|.idb|Kompilieren|Die enthaltende Statusdatei Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen. Es kann vom Compiler während der inkrementellen Kompilierung verwendet werden. Verwenden Sie die Compileroption [/Fd](fd-program-database-file-name.md) zum Angeben des Namens der IDB-Datei.|
|.idl|Kompilieren|Eine IDL-Datei. Weitere Informationen finden Sie im Windows SDK unter [Interface Definition (IDL) File (Schnittstellendefinitionsdatei)](/windows/desktop/Rpc/the-interface-definition-language-idl-file).|
|.ilk|Verknüpfen|Datei für inkrementelle Verknüpfung. Weitere Informationen finden Sie unter [/INCREMENTAL](incremental-link-incrementally.md).|
|.map|Verknüpfen|Eine Textdatei mit Linkerinformationen. Verwenden Sie die Compileroption [/Fm](fm-name-mapfile.md) , um die MAP-Datei zu benennen. Weitere Informationen finden Sie unter [/MAP](map-generate-mapfile.md).|
|.mfcribbon-ms|Ressource|Eine Ressourcendatei, die den XML-Code enthält, der die MFC-Schaltflächen, Steuerelemente und Attribute im Menüband definiert. Weitere Informationen finden Sie unter [Ribbon Designer](../../mfc/ribbon-designer-mfc.md).|
|.obj, .o||Objektdateien, kompiliert, aber nicht verknüpft.|
|.pch|Debug|Vorkompilierte Headerdatei.|
|.rc, .rc2|Ressource|[Ressourcenskriptdateien](../../windows/working-with-resource-files.md) zum Generieren von Ressourcen.|
|.sbr|Kompilieren|Zwischendatei des Quellbrowsers. Die Eingabedatei für [BSCMAKE](bscmake-options.md).|
|.sln|Lösung|Die [Projektmappen](/visualstudio/ide/solutions-and-projects-in-visual-studio) datei.|
|.suo|Lösung|Die Datei mit den Projektmappenoptionen.|
|.txt|Ressource|Eine Textdatei, in der Regel die Infodatei.|
|.vap|Projekt|Eine Visual Studio Analyzer-Projektdatei.|
|.vbg|Lösung|Eine kompatible Projektgruppendatei.|
|.vbp, .vip, .vbproj|Projekt|Die Visual Basic-Projektdatei.|
|.vcxitems|Projekt|Ein Projekt mit freigegebenen Elementen zum Freigeben von Codedateien zwischen mehreren C++-Projekten. Weitere Informationen finden Sie unter [Projekt- und Projektmappendateien](project-and-solution-files.md).|
|.vcxproj|Projekt|Die Visual Studio-Projektdatei. Weitere Informationen finden Sie unter [Projekt- und Projektmappendateien](project-and-solution-files.md).|
|.vcxproj.filters|Projekt|Verwendet, wenn Sie Projektmappen-Explorer verwenden, um eine Datei zu einem Projekt hinzuzufügen. Die Filterdatei definiert die Position in der Strukturansicht der Projektmappen-Explorer die Datei, die anhand der Dateierweiterung hinzugefügt.|
|.vdproj|Projekt|Die Visual Studio-Bereitstellungsprojektdatei.|
|.vmx|Projekt|Die Makro-Projektdatei.|
|.vup|Projekt|Der Hilfsprogramm-Projektdatei.|

Weitere Informationen über andere mit Visual Studio verknüpfte Dateien finden Sie unter [Dateitypen und Dateierweiterungen in Visual Studio .NET](/visualstudio/ide/reference/project-and-solution-file-types).

Projektdateien sind in Ordnern im Projektmappen-Explorer organisiert. Visual Studio erstellt einen Ordner für Quelldateien, Headerdateien und Ressourcendateien, aber Sie können diese Ordner neu zu organisieren oder neu erstellen. Sie können Ordner verwenden, um logische Cluster von Dateien innerhalb der Hierarchie eines Projekts explizit zu organisieren. Beispielsweise können Sie Ordner, um alle Ihre Benutzeroberflächen-Quelldateien enthalten erstellen. Oder Ordner für die Spezifikationen, Dokumentation oder Testsammlungen. Alle Dateiordnernamen sollten eindeutig sein.

Wenn Sie ein Element zu einem Projekt hinzufügen, fügen Sie das Element für alle Konfigurationen für das betreffende Projekt. Das Element wird hinzugefügt, ob es oder nicht erstellt werden kann. Wenn Sie beispielsweise über ein Projekt mit dem Namen „MeinProjekt“ verfügen, wird das Element durch das Hinzufügen zu den Debug- und Release-Projektkonfigurationen hinzugefügt.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwalten von Visual Studio C++-Projekte](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++-Projekttypen](visual-cpp-project-types.md)<br>