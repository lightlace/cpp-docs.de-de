---
title: Linkertoolfehler Lnk1104 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: c6121f598bc2913b65fe781b07bcc27e6b55375b
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1104"></a>Linkertoolfehler LNK1104
Öffnen der Datei "*Filename*"  
  
Der Linker konnte die angegebene Datei nicht geöffnet werden.  
  
## <a name="possible-causes-and-solutions"></a>Mögliche Ursachen und Lösungen
  
Dieser Fehler kann auftreten, wenn der Linker versucht, eine Datei zum Lesen oder schreiben zu öffnen. Die häufigsten Ursachen für dieses Problem sind, dass die Datei nicht vorhanden ist, kann nicht gefunden werden in einem der Verzeichnisse den Linker sucht, oder wird derzeit verwendet und von einem anderen Prozess gesperrt. Weniger üblich, Sie möglicherweise nicht genügend Speicherplatz, die Datei ist möglicherweise zu groß, den Pfad zur Datei ist möglicherweise zu lang oder Sie möglicherweise keine Zugriffsberechtigung auf die Datei zuzugreifen.  

Überprüfen Sie eine der folgenden Probleme:  

-   Die Anwendung wird bereits ausgeführt, wenn Sie versuchen, ihn neu erstellen. Wenn die Datei, die nicht geöffnet werden kann die ausführbare Datei oder eine Datei debuggen, z. B. einer PDB-Datei handelt, ist dies eine häufige Ursache. Um dieses Problem zu beheben, beenden Sie das Programm, und über den Debugger entladen Sie werden, bevor Sie es erneut erstellen.  
  
-   Die Datei *Filename* , die von der Projektmappe erstellt wird, aber noch nicht vorhanden, wenn der Linker versucht, darauf zuzugreifen. Dies kann geschehen, wenn ein Projekt hängt von einem anderen Projekt diese Datei erzeugen, aber die Projekte werden nicht in der richtigen Reihenfolge erstellt. Um dieses Problem zu beheben, stellen Sie sicher, dass Ihre Projektverweise auf im Projekt festgelegt werden, die die Datei verwendet, sodass die fehlende Datei erstellt wird, bevor er erforderlich ist. Weitere Informationen finden Sie unter [Hinzufügen von Verweisen in Visual C++-Projekten](../../ide/adding-references-in-visual-cpp-projects.md) und [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).  
  
-   Der Dateiname oder Pfad angegeben, in der Befehlszeile oder in einem #pragma-Anweisung Lib ist falsch, oder der Pfad weist eine ungültige Laufwerksangabe. Überprüfen Sie die Schreibweise, und stellen Sie sicher, dass die Datei am angegebenen Speicherort vorhanden ist.  
  
-   Wenn Sie Visual Studio-IDE verwenden, um ein Projekt zu erstellen, die von einem anderen Computer kopiert wurde, können die Installationspfade für Bibliotheken abweichen. Überprüfen Sie die Bibliotheksverzeichnisse-Eigenschaft auf die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) und bei Bedarf zu aktualisieren. Um anzuzeigen, und bearbeiten die aktuellen Library-Pfade, die in der IDE festgelegt, wählen Sie das Dropdown-Steuerelement für die Bibliotheksverzeichnisse-Eigenschaft, und wählen Sie **bearbeiten**. Die **Wert ausgewertet** Abschnitt des Dialogfelds Bibliotheksverzeichnisse Listet die aktuellen Pfade Bibliotheksdateien gesucht.  
  
-   Wenn Sie ein Projekt erstellen, die mit einer älteren Version von Visual Studio erstellt wurde, können die Plattformtoolset und Bibliotheken für diese Version nicht nicht installiert. Um dieses Problem zu beheben, haben Sie zwei Optionen: upgrade des Projekts, um die aktuellen-Plattformtoolset verwenden Sie installiert haben, oder installieren Sie das ältere Toolset und erstellen Sie das Projekt nicht geändert. Weitere Informationen finden Sie unter [Aktualisierung von Projekten aus früheren Versionen von Visual C++](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) und [verwenden systemeigene Festlegung von Zielversionen in Visual Studio zum Erstellen von Projekten alten](../../porting/use-native-multi-targeting.md).
  
-   Die Bibliotheken für die aktuelle Konfiguration des Projekts oder Plattformtoolset sind nicht installiert. Stellen Sie sicher, dass das Plattformtoolset und das Windows SDK, in angegeben der [Eigenschaftenseite Allgemein](../../ide/general-property-page-project.md) für das Projekt installiert sind, und stellen Sie sicher, dass die erforderlichen Bibliotheken in der Bibliothek unter verfügbar sind die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) für Ihre Konfigurationseinstellungen. Es gibt separate Einstellungen für die Debug-und die Verkaufsversion, wenn Erstellung funktioniert, aber die andere einen Fehler verursacht, achten Sie darauf die Einstellungen richtig sind und die erforderlichen Tools und Bibliotheken für beide Konfigurationen installiert sind.  
  
-   Der Pfad zum Windows SDK ist veraltet. Wenn Sie eine Version des Windows SDK, die neuer ist als Ihre Version von Visual Studio installiert haben, stellen Sie sicher, dass die Pfade in angegeben die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md) werden aktualisiert, um das neue SDK übereinstimmen. Wenn Sie die Developer-Eingabeaufforderung verwenden, stellen Sie sicher, dass die Batchdatei, die die Umgebungsvariablen initialisiert für die neue SDK-Pfade aktualisiert wird.  
  
-   Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben. Oft blockiert Antivirusprogramme vorübergehend den Zugriff auf die neu erstellte Dateien. Um dieses Problem zu beheben, versuchen Sie es Ausschließen von Ihrem Build Projektverzeichnisse von der Antivirenscanner.  
  
-   Wenn Sie eine parallele Buildoption verwendet werden, ist es möglich, dass Visual Studio die Datei in einem anderen Thread gesperrt hat. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie nicht die gleichen Codeobjekt oder eine Bibliothek in mehreren Projekten erstellen und Sie Buildabhängigkeiten oder Projektverweise verwenden, um in Ihrem Projekt erstellten Binärdateien zu übernehmen.  
  
-   Sie haben eine falsche LIB-Umgebungsvariable. In Befehlszeilenbuilds stellen Sie sicher, dass die LIB-Umgebungsvariable festgelegt ist, und enthält alle Verzeichnisse für die Bibliotheken, die Sie verwenden. In der IDE die LIB-Variable Festlegen von der Bibliotheksverzeichnisse-Eigenschaft auf die [VC++-Verzeichnisse Eigenschaftenseite](../../ide/vcpp-directories-property-page.md). Stellen Sie sicher, dass alles, was die Verzeichnisse, die Bibliotheken enthalten, die Sie müssen, hier aufgeführt sind. Wenn Sie ein Bibliotheksverzeichnis angeben müssen, überschreibt eine standard-Bibliotheksverzeichnis, können Sie mithilfe der [/LIBPATH](../../build/reference/libpath-additional-libpath.md)) Option in der Befehlszeile oder die zusätzliche Bibliotheksverzeichnisse-Eigenschaft in der Linker-Eigenschaftenseite für das Projekt.  
  
-   Wenn Sie einzelne Bibliotheken im Dialogfeld Eigenschaftenseiten des Projekts angeben, müssen die Bibliotheksnamen durch Leerzeichen, nicht durch Kommas getrennt werden.  
  
-   Der Pfad für *Filename* wird auf mehr als 260 Zeichen erweitert. Ändern Sie die Namen oder ordnen Sie die Verzeichnisstruktur neu an, bei Bedarf, um die Pfade zu den erforderlichen Dateien zu kürzen.  
  
-   Die Datei ist zu groß. Objekt oder Bibliotheken Dateien mehr als ein Gigabyte groß für den 32-Bit-Linker möglicherweise Probleme verursacht. Eine mögliche Lösung für dieses Problem ist die 64-Bit-Toolset verwendet. Weitere Informationen dazu in der Befehlszeile finden Sie unter [Vorgehensweise: Aktivieren Sie eine 64-Bit-Visual C++-Toolsets in der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). Informationen dazu in der IDE finden Sie unter [mithilfe von MSBuild mit 64-Bit-Compiler und Tools](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) und diesen Beitrag Stack Overflow: [wie Sie Visual Studio verwenden, die amd64 native-toolkette](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).  
  
-   Sie haben nicht genügend Berechtigungen zum Zugreifen auf *Filename*. Dies kann geschehen, wenn Sie Bibliotheksdateien in der geschützten Verzeichnisse zugreifen, oder verwenden die Dateien kopiert, die von anderen Benutzern, die ihre ursprünglichen Berechtigungen verfügen festgelegt. Um dieses Problem zu beheben, verschieben Sie die Datei in einem beschreibbaren Projektverzeichnis. Wenn die Datei in einem beschreibbaren Verzeichnis jedoch berechtigt ist nicht zugegriffen werden kann, können Sie verwenden eine Eingabeaufforderung mit Administratorrechten aus und führen Sie den Befehl takeown.exe des Besitzes der Datei.  
  
-   Sie haben keine genügend Speicherplatz vorhanden. Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch wenn Sie über ausreichend Speicherplatz verfügen, kann eine sehr umfangreiche Verknüpfung ausschöpfen oder fragmentieren den verfügbare Speicherplatz. Erwägen Sie die [/OPT (Optimierungen)](../../build/reference/opt-optimizations.md) Option; auf diese Weise transitive Comdat-Eliminierung liest alle Objektdateien mehrfach.  
  
-   Wenn die *Filename* heißt LNK*n*, also einen vom Linker für eine temporäre Datei generierten Dateinamen, die in der TMP-Umgebungsvariablen angegebene Verzeichnis ist möglicherweise nicht vorhanden oder kann mehr als ein Verzeichnis für die TMP-Umgebungsvariable angegeben werden. Nur ein Verzeichnispfad sollte für die TMP-Umgebungsvariable angegeben werden.  
  
-   Wenn die Fehlermeldung für einen Bibliotheksnamen auftritt und Sie kürzlich die MAK-Datei von einem früheren Microsoft Visual C++-Entwicklungssystem portiert haben, ist die Bibliotheksdatei möglicherweise nicht mehr gültig. Stellen Sie sicher, dass der Bibliotheksname richtig ist und noch am angegebenen Speicherort vorhanden ist, oder aktualisieren Sie die LIB-Pfad, um auf den neuen Speicherort zu verweisen.  

