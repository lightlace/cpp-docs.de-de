---
title: Für Visual C++-Projekte erstellte Dateitypen
ms.date: 11/04/2016
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
ms.openlocfilehash: c05dd9da5dd17b0e06ace750d34f2c5abcf94380
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825838"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Für Visual Studio C++-Projekte erstellte Dateitypen

Dieses Thema beschreibt alle Typen von Dateien, die mit Visual Studio-Projekten für klassische desktopcomputeranwendungen verknüpft sind. Die in Ihrem Projekt tatsächlich enthaltenen Dateien sind vom Projekttyp und von Ihnen mithilfe eines Assistenten ausgewählten Optionen abhängig.

- [Projekt- und Projektmappendateien]()

- [CLR Projects (CLR-Projekte)](files-created-for-clr-projects.md)

- [ATL-Programm oder Steuern von Quell- und Headerdateien](atl-program-or-control-source-and-header-files.md)

- [MFC-Programm oder Steuern von Quell- und Headerdateien](mfc-program-or-control-source-and-header-files.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

- [Ressourcendateien](resource-files-cpp.md)

- [Hilfedateien (WinHelp)](help-files-winhelp.md)

- [Hinweisdateien](hint-files.md)

Wenn Sie Visual Studio-Projekt erstellen, erstellen Sie möglicherweise eine neue Projektmappe, oder Sie fügen möglicherweise ein Projekt zu einer Projektmappe. Nicht triviale Anwendungen werden häufig mit mehreren Projekten in einer Projektmappe entwickelt.

Projekte generieren für gewöhnlich entweder eine EXE- oder eine DLL-Datei. Projekte können voneinander abhängig sein; während des Buildprozesses überprüft Visual Studio-Umgebung Abhängigkeiten in und zwischen Projekten. Jedes Projekt verfügt über einen Hauptquellcode, und in Abhängigkeit der Projektart weist es möglicherweise viele andere Dateien auf, die verschieden Aspekte des Projekts enthalten. Die Inhalte dieser Dateien werden durch die Dateierweiterung angegeben. Die Visual Studio-Entwicklungsumgebung verwendet die Dateierweiterungen, um zu bestimmen, wie die Dateiinhalte während eines Builds verarbeitet werden.

In der folgende Tabelle wird gemeinsame Dateien in einem Visual Studio-Projekt, und sie mit der Dateierweiterung identifiziert.

|Dateierweiterung|Typ|Inhalt|
|--------------------|----------|--------------|
|.asmx|Quelle|Bereitstellungsdatei.|
|.asp|Source|Aktive Serverseitendatei|
|.atp|Projekt|Anwendungsvorlagen-Projektdatei.|
|.bmp, .dib, .gif, .jpg, .jpeg, .png|Ressource|Allgemeine Bilddateien.|
|.bsc|Kompilieren|Browsercodedatei.|
|.cpp; .c|Source|Haupt-Quellcodedateien für Ihre Anwendung.|
|.cur|Ressource|Cursorbitmap-Grafikdatei.|
|.dbp|Projekt|Datenbankprojektdatei.|
|.disco|Source|Dynamische Ermittlungsdokumentdatei. Verarbeitet die XML-Webdienstermittlung.|
|.exe, .dll|Projekt|Ausführbare oder Dynamic-Link Library-Dateien.|
|H|Source|Headerdatei (include).|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Ressource|Allgemeine Webdateien.|
|.HxC|Projekt|Hilfsprojektdatei.|
|.ico|Ressource|Symbolbitmap-Grafikdatei.|
|.idb|Kompilieren|Die die Abhängigkeitsinformationen zwischen den Quelldateien und Klassendefinitionen enthaltende Statusdatei, die durch den Compiler während der minimalen Neuerstellung und der inkrementellen Kompilierung verwendet werden kann. Verwenden Sie die Compileroption [/Fd](fd-program-database-file-name.md) zum Angeben des Namens der IDB-Datei. Weitere Informationen finden Sie unter [/Gm (Minimale Neuerstellung aktivieren)](gm-enable-minimal-rebuild.md) .|
|.idl|Kompilieren|Eine IDL-Datei. Weitere Informationen finden Sie im Windows SDK unter [Interface Definition (IDL) File (Schnittstellendefinitionsdatei)](/windows/desktop/Rpc/the-interface-definition-language-idl-file).|
|.ilk|Verknüpfen|Datei für inkrementelle Verknüpfung. Weitere Informationen finden Sie unter [/INCREMENTAL](incremental-link-incrementally.md) .|
|.map|Verknüpfen|Eine Textdatei mit Linkerinformationen. Verwenden Sie die Compileroption [/Fm](fm-name-mapfile.md) , um die MAP-Datei zu benennen. Weitere Informationen finden Sie unter [/MAP](map-generate-mapfile.md) .|
|.mfcribbon-ms|Ressource|Eine den die Schaltflächen, Steuerelemente und Attribute im Menüband definierenden XML-Code enthaltende Ressourcendatei. Weitere Informationen finden Sie unter [Ribbon Designer (MFC)](../../mfc/ribbon-designer-mfc.md).|
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
|.vcxitems|Projekt|Ein Projekt mit freigegebenen Elementen zum Freigeben von Codedateien zwischen mehreren C++-Projekten. Weitere Informationen finden Sie unter [Projektdateien und Makefiles]() .|
|.vcxproj|Projekt|Die Visual Studio-Projektdatei. Weitere Informationen finden Sie unter [Projektdateien und Makefiles]() .|
|.vcxproj.filters|Projekt|Wenn der Projektmappen-Explorer verwendet wird, um einem Projekt eine Datei hinzuzufügen, definiert die Filterdatei auf Grundlage der entsprechenden Dateinamenserweiterung, wo in der Projektmappen-Explorer-Gesamtstrukturansicht die Datei hinzugefügt wird.|
|.vdproj|Projekt|Die Visual Studio-Bereitstellungsprojektdatei.|
|.vmx|Projekt|Die Makro-Projektdatei.|
|.vup|Projekt|Der Hilfsprogramm-Projektdatei.|

Weitere Informationen über andere mit Visual Studio verknüpfte Dateien finden Sie unter [Dateitypen und Dateierweiterungen in Visual Studio .NET](/visualstudio/ide/reference/project-and-solution-file-types).

Projektdateien sind in Ordnern im Projektmappen-Explorer organisiert. Visual Studio erstellt einen Ordner für Quelldateien, Headerdateien und Ressourcendateien, aber Sie können diese Ordner neu zu organisieren oder neu erstellen. Sie können Ordner verwenden, um logische Cluster von Dateien innerhalb der Hierarchie eines Projekts explizit zu organisieren. Beispielsweise können Sie Ordner so erstellen, dass sie alle Ihre Benutzeroberflächen-Quelldateien oder Spezifikationen, Dokumentationen oder Testsammlungen enthalten. Alle Dateiordnernamen sollten eindeutig sein.

Wenn Sie einem Projekt ein Element hinzufügen, fügen Sie das Element zu allen Konfigurationen für dieses Projekt hinzu, unabhängig davon, ob das Element erstellt werden kann. Wenn Sie beispielsweise über ein Projekt mit dem Namen „MeinProjekt“ verfügen, wird das Element durch das Hinzufügen zu den Debug- und Release-Projektkonfigurationen hinzugefügt.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwalten von Visual Studio C++-Projekte](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++-Projekttypen](visual-cpp-project-types.md)<br>