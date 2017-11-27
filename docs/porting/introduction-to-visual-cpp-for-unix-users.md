---
title: "Einführung in Visual C++ für UNIX-Benutzer | Microsoft-Dokumentation"
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 798dc2ca8b6a04203232d9eee52b1f5be5eacdd5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="introduction-to-visual-c-for-unix-users"></a>Einführung in Visual C++ für UNIX-Benutzer

Dieses Thema enthält Informationen für UNIX-Benutzer, die noch keine Erfahrungen mit Visual C++ sammeln konnten und Visual C++ und die integrierte Entwicklungsumgebung (IDE) von Visual Studio produktiv einsetzen möchten.  
  
## <a name="getting-started-on-the-command-line"></a>Erste Schritte über die Befehlszeile  

Sie können Visual C++ von der Befehlszeile aus auf ähnliche Weise wie eine Befehlszeilenumgebung unter UNIX verwenden. Die Kompilierung erfolgt mithilfe der Eingabeaufforderung mit dem C/C++-Befehlszeilencompiler (CL.EXE), dem Linker (LINK.EXE) und weiteren Tools, darunter NMAKE.EXE, der Microsoft-Version des UNIX-Dienstprogramms Make.  
  
Unter UNIX werden Befehle in einem gemeinsam genutzten Ordner, z. B. /usr/bin, installiert. In Visual C++ werden die Befehlszeilentools in Ihrem Visual Studio-Installationsverzeichnis im Unterverzeichnis „VC\bin“ und seinen Unterverzeichnissen installiert. Im Gegensatz zu UNIX sind diese Tools nicht in einem einfachen Eingabeaufforderungsfenster verfügbar. Um die Befehlszeilentools zu verwenden, verwenden Sie einen Eingabeaufforderungskurzbefehl für Entwickler, oder führen Sie eine Entwicklerbefehlsdatei wie „vcvarsall.bat“ aus. Dadurch werden der Pfad und andere Umgebungsvariablen festgelegt, die erforderlich sind, um Visual C++-Programme von der Befehlszeile aus zu kompilieren. Weitere Informationen finden Sie unter [Erstellen von C/C++-Code über die Befehlszeile](../build/building-on-the-command-line.md) und unter [Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
Um einen Eingabeaufforderungskurzbefehl für Entwickler zu öffnen, geben Sie *Entwicklereingabeaufforderung* in das Desktopsuchsteuerelement ein, und wählen Sie das Ergebnis **Entwicklereingabeaufforderung** für Ihre Version von Visual Studio aus. Um eine Entwicklereingabeaufforderung auszuwählen, die für einen bestimmten Host und eine Zielarchitektur vorkonfiguriert ist, öffnen Sie das Menü **Start** (das Windows-Symbol in der Ecke des Desktops), und scrollen Sie dann zu dem Ordner für Ihre Visual Studio-Version, z. B. **Visual Studio 2017**. Öffnen Sie den Ordner, und wählen Sie den Eingabeaufforderungskurzbefehl für Ihren bevorzugten Host und eine Zielarchitektur aus.
  
Um die Vorteile leistungsfähigerer Features wie den Visual Studio-Debugger, die IntelliSense-Codesuche und -Anweisungsvervollständigung, visuelle Designer, Projektmanagement usw. nutzen zu können, müssen Sie die Visual Studio IDE verwenden.  
  
## <a name="debugging-your-code"></a>Debuggen von Code  

Wenn Sie die Befehlszeile verwenden und die Anwendungen auf der Entwicklungsarbeitsstation ausführen, wird ein Dialogfeld zur Ausführung des [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]-Debuggers angezeigt, sobald im Code eine Speicherzugriffsverletzung, eine nicht behandelte Ausnahme oder ein anderer nicht behebbarer Fehler auftritt. Wenn Sie auf **OK** klicken, wird die Entwicklungsumgebung von Visual Studio gestartet, und der Debugger wird an dem Punkt geöffnet, an dem der Fehler auftrat. Sie können Anwendungen auf diese Weise debuggen. Der Quellcode steht in diesem Fall jedoch nur dann zur Verfügung, wenn beim Kompilieren der [/Z7, /Zi, /ZI (Debuginformationsformat)](../build/reference/z7-zi-zi-debug-information-format.md)-Schalter verwendet wurde. Weitere Informationen finden Sie unter [Debuggen von nativem Code](/visualstudio/debugger/debugging-native-code) und [Verwenden der Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="using-the-development-environment"></a>Verwenden der Entwicklungsumgebung  

Die Verwendung der Entwicklungsumgebung vereinfacht das Bearbeiten und Erstellen von Quellcode in einem *Projekt* beträchtlich. Ein Projekt ist eine Auflistung von Quelldateien und zugehörigen Dateien, die zu einer Einheit, z. B. einer Bibliothek oder einer ausführbaren Datei, kompiliert werden. Ein Projekt enthält außerdem Informationen darüber, wie die Dateien erstellt werden sollen. Die Projektinformationen werden in einer Projektdatei mit der Erweiterung PJR gespeichert.  
  
Eine Anwendung, die aus mehreren Bibliotheken und ausführbaren Dateien besteht, von denen möglicherweise jede mit einem anderen Satz von Compileroptionen oder sogar in einer anderen Sprache erstellt wurde, wird in mehreren Projekten gespeichert, die Teil einer einzigen *Projektmappe* sind. Eine Projektmappe stellt einen abstrakten Container dar, der zur Gruppierung mehrerer Projekte dient. Informationen über Projektmappen werden in einer Projektmappendatei mit der Erweiterung SLN gespeichert. Weitere Informationen finden Sie unter [Projektmappen und Projekte in Visual Studio](/visualstudio/ide/solutions-and-projects-in-visual-studio) und unter [Verwenden der Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="importing-your-existing-code"></a>Importieren von vorhandenem Code 
 
Sie können Visual C++ verwenden, um vorhandenen Code zu erstellen, der für die Kompilierung mit oder ohne Makefile eingerichtet wurde, und Sie können diesen Code in ein [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]-Projekt einfügen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md).  
  
## <a name="creating-a-new-project"></a>Erstellen eines neuen Projekts  

Sie können in der Entwicklungsumgebung neue Projekte erstellen. Visual C++ bietet eine Vielzahl von Vorlagen, die Standardcode für verschiedene, häufig verwendete Projekte enthalten. Mit Anwendungs-Assistenten können Sie Projekte mit Codegliederungen für verschiedene Anwendungstypen generieren.  
  
Sie können mit einem leeren Projekt beginnen, indem Sie den **Assistenten für Konsolenanwendungen (Win32)** verwenden. Aktivieren Sie das Kontrollkästchen **Leeres Projekt**. Sie können dem Projekt dann später neue Dateien und bereits vorhandene Dateien hinzufügen.  
  
Beim Erstellen eines Projekts müssen Sie dem Projekt einen Namen geben. Standardmäßig erhält das Projekt denselben Namen wie die DLL (Dynamic Link Library) oder die ausführbare Datei, die aus dem Projekt erstellt wird. Weitere Informationen finden Sie unter [Erstellen von Projekten und Projektmappen](/visualstudio/ide/creating-solutions-and-projects).  
  
## <a name="microsoft-specific-modifiers"></a>Microsoft-spezifische Modifizierer  

Visual C++ enthält mehrere Erweiterungen der C++-Standardprogrammiersprache, um die Programmierung für Windows-Betriebssysteme zu unterstützen. Diese Erweiterungen werden unter anderem zum Angeben von Speicherklassenattributen, Funktionsaufrufknventionen sowie der Adressierungsart verwendet. Eine vollständige Liste aller Visual C++-Erweiterungen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).  
  
Sie können alle Microsoft-spezifischen Erweiterungen von C++ deaktivieren, indem Sie die **/Za**-Compileroption verwenden. Diese Option wird für das Schreiben von Code empfohlen, der auf mehreren Plattformen ausgeführt werden soll. Weitere Informationen zur **/Za**-Compileroption finden Sie unter [/Za, /Ze (Spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md). Weitere Informationen zur Visual C++-Konformität finden Sie unter [Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md).  
  
## <a name="precompiled-headers"></a>Vorkompilierte Header  

Die Microsoft C- und C++-Compiler stellen Optionen für das Vorkompilieren von beliebigem C- oder C++-Code bereit, einschließlich Inlinecode. Mithilfe dieser leistungsstarken Funktion können Sie einen stabilen Codeabschnitt kompilieren, den Code im kompilierten Zustand in einer Datei speichern und bei nachfolgenden Kompilierungen den vorkompilierten Code mit dem noch in Entwicklung befindlichen Code kombinieren. So können nachfolgende Kompilierungen beschleunigt werden, da der bereits stabile Code nicht neu kompiliert werden muss.  
  
Standardmäßig wird sämtlicher vorkompilierter Code in den Dateien **stdafx.h** und **stdafx.cpp** angegeben. Der **Assistent für neue Projekte** erstellt diese Dateien automatisch, sofern Sie die Option **Vorkompilierte Headerdatei** nicht deaktivieren. Weitere Informationen zu vorkompilierten Headern finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/reference/creating-precompiled-header-files.md).  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

Weitere Informationen finden Sie unter [Portieren von UNIX auf Win32](../porting/porting-from-unix-to-win32.md).  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)