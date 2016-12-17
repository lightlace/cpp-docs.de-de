---
title: "Einf&#252;hrung in Visual&#160;C++ f&#252;r UNIX-Benutzer"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UNIX [C++]"
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Einf&#252;hrung in Visual&#160;C++ f&#252;r UNIX-Benutzer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema enthält Informationen für UNIX\-Benutzer, die noch keine Erfahrungen mit [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sammeln konnten und [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] produktiv einsetzen möchten.  
  
## Erste Schritte über die Befehlszeile  
 Sie können [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] von der Befehlszeile aus auf ähnliche Weise wie eine Befehlszeilenumgebung unter UNIX verwenden.  Die Kompilierung erfolgt über die Eingabeaufforderung mit dem C\/C\+\+\-Befehlszeilencompiler \(CL.EXE\) und weiteren Tools, darunter NMAKE.EXE, der Microsoft\-Version des UNIX\-Dienstprogramms Make.  
  
 Unter UNIX werden Befehle in einem gemeinsam genutzten Ordner, z. B. \/usr\/bin, installiert.  In [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] werden die Befehlszeilentools im Installationsverzeichnis unter VC\\bin installiert \(bei einer typischen Installation unter Programme\\Microsoft Visual Studio 8\\VC\\bin\).  Um die Befehlszeilentools zu verwenden, führen Sie vsvars32.bat aus. Diese Datei befindet sich im Installationsverzeichnis unter Common7\\Tools.  Dadurch wird das Verzeichnis „bin“ zum Pfad hinzugefügt, und es werden weitere Pfade eingerichtet, die zum Kompilieren von Visual C\+\+\-Programmen über die Befehlszeile erforderlich sind.  
  
> [!NOTE]
>  Beim Öffnen einer Eingabeaufforderung über den Menüpunkt **Visual Studio\-Eingabeaufforderung** im Menü **Start** wird vsvars32.bat automatisch ausgeführt.  
  
 Um die Vorteile der leistungsfähigeren Features wie des Debuggers und der Anweisungsvervollständigung nutzen zu können, müssen Sie die Entwicklungsumgebung verwenden.  Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile](../build/building-on-the-command-line.md) und [Exemplarische Vorgehensweise: Kompilieren eines systemeigenen C\+\+\-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## Debuggen von Code  
 Wenn Sie die Befehlszeile verwenden und die Anwendungen auf der Entwicklungsarbeitsstation ausführen, wird ein Dialogfeld zur Ausführung des [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Debuggers angezeigt, sobald im Code eine Speicherzugriffsverletzung, eine nicht behandelte Ausnahme oder ein anderer nicht behebbarer Fehler auftritt.  Wenn Sie auf **OK** klicken, wird die Entwicklungsumgebung von Visual Studio gestartet, und der Debugger wird an dem Punkt geöffnet, an dem der Fehler auftrat.  Sie können Anwendungen auf diese Weise debuggen. Der Quellcode steht jedoch nur dann zur Verfügung, wenn beim Kompilieren der [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../build/reference/z7-zi-zi-debug-information-format.md)\-Schalter verwendet wurde.  Weitere Informationen finden Sie unter [Debuggen von systemeigenem Code](../Topic/Debugging%20Native%20Code.md) und [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## Verwenden der Entwicklungsumgebung  
 Die Verwendung der Entwicklungsumgebung vereinfacht das Bearbeiten und Erstellen von Quellcode in einem *Projekt* beträchtlich.  Ein Projekt ist eine Auflistung von Quelldateien und zugehörigen Dateien, die zu einer Einheit, z. B. einer Bibliothek oder einer ausführbaren Datei, kompiliert werden.  Ein Projekt enthält außerdem Informationen darüber, wie die Dateien erstellt werden sollen.  Die Projektinformationen werden in einer Projektdatei mit der Erweiterung PJR gespeichert.  
  
 Eine Anwendung, die aus mehreren Bibliotheken und ausführbaren Dateien besteht, von denen möglicherweise jede mit einem anderen Satz von Compileroptionen oder sogar in einer anderen Sprache erstellt wurde, wird in mehreren Projekten gespeichert, die Teil einer einzigen *Projektmappe* sind.  Eine Projektmappe stellt einen abstrakten Container dar, der zur Gruppierung mehrerer Projekte dient.  Informationen über Projektmappen werden in einer Projektmappendatei mit der Erweiterung SLN gespeichert.  Weitere Informationen finden Sie unter [PAVE: Managing Solutions and Projects](assetId:///7a50db22-d3cc-46f3-b648-ab7e0528e260) und [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## Importieren von vorhandenem Code  
 In [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] können Sie vorhandenen Code verwenden, der für die Kompilierung mit oder ohne Makefile eingerichtet wurde, und Sie können diesen Code in ein [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\-Projekt einfügen.  Weitere Informationen finden Sie unter dem Thema **Assistent für das Erstellen von Projekten aus vorhandenen Codedateien**.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines C\+\+\-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md).  
  
## Erstellen eines neuen Projekts  
 Sie können in der Entwicklungsumgebung neue Projekte erstellen.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] bietet eine Vielzahl von Vorlagen, die Standardcode für verschiedene, häufig verwendete Projekte enthalten.  Mit Anwendungs\-Assistenten können Sie Projekte mit Codegliederungen für verschiedene Anwendungstypen generieren.  
  
 Sie können mit einem leeren Projekt beginnen, indem Sie den **Assistenten für Konsolenanwendungen \(Win32\)** verwenden.  Aktivieren Sie das Kontrollkästchen **Leeres Projekt**.  Sie können dem Projekt dann später neue Dateien und bereits vorhandene Dateien hinzufügen.  
  
 Beim Erstellen eines Projekts müssen Sie dem Projekt einen Namen geben.  Standardmäßig erhält das Projekt denselben Namen wie die DLL \(Dynamic Link Library\) oder die ausführbare Datei, die aus dem Projekt erstellt wird.  Weitere Informationen finden Sie unter [Erstellen von Projekten und Projektmappen](../Topic/Creating%20Solutions%20and%20Projects.md).  
  
## Microsoft\-spezifische Modifizierer  
 Visual C\+\+ enthält gegenüber der Standardprogrammiersprache C\+\+ verschiedene Erweiterungen.  Diese Erweiterungen werden unter anderem zum Angeben von Speicherklassenattributen, Konventionen für Funktionsaufrufe sowie der Adressierungsart verwendet.  Eine vollständige Liste aller Visual C\+\+\-Erweiterungen finden Sie unter [Microsoft\-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).  
  
 Sie können alle Microsoft\-spezifischen Erweiterungen von C\+\+ deaktivieren, indem Sie die **\/Za**\-Compileroption verwenden.  Diese Option wird für das Schreiben von Code empfohlen, der auf mehreren Plattformen ausgeführt werden soll.  Weitere Informationen zur **\/Za**\-Compileroption finden Sie unter [\/Za, \/Ze \(Spracherweiterungen deaktivieren\)](../build/reference/za-ze-disable-language-extensions.md).  Weitere Informationen zur Konformität von Visual C\+\+ finden Sie unter [Kompatibilitäts\- und Konformitätsprobleme in Visual C\+\+](../misc/compatibility-and-compliance-issues-in-visual-cpp.md).  
  
## Vorkompilierte Header  
 Die Microsoft C\- und C\+\+\-Compiler stellen Optionen für das Vorkompilieren von beliebigem C\- oder C\+\+\-Code bereit, einschließlich Inlinecode.  Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren.  So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.  
  
 Standardmäßig wird sämtlicher vorkompilierter Code in den Dateien **stdafx.h** und **stdafx.cpp** angegeben.  Der **Assistent für neue Projekte** erstellt diese Dateien automatisch, solange Sie die Option **Vorkompilierte Header** nicht deaktivieren.  Weitere Informationen zu vorkompilierten Headern finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/reference/creating-precompiled-header-files.md).  
  
## Verwandte Abschnitte  
 Weitere Informationen finden Sie unter [Portieren von UNIX auf Win32](../porting/porting-from-unix-to-win32.md).  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)