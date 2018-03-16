---
title: Bestimmen die zu verteilenden DLLs | Microsoft Docs
ms.custom: 
ms.date: 03/13/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6f942b01dd9379aea0c0ea2ab3751a6f140ef2a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="determining-which-dlls-to-redistribute"></a>Ermitteln der neu zu verteilenden DLLs

Beim Erstellen einer Anwendung, die von Visual Studio bereitgestellte DLLs für Bibliotheken verwendet, müssen Benutzer der Anwendung auch diese DLLs auf ihren Computern zum Ausführen der Anwendung verfügen. Da die meisten Benutzer wahrscheinlich nicht Visual Studio installiert haben, müssen Sie diese DLLs für sie bereitstellen. Visual Studio stellt diese DLLs als verfügbar *verteilbaren Dateien* , die Sie in das Installationsprogramm der Anwendung einschließen können.

Um enthalten die verteilbaren DLLs in den Installer zu erleichtern, sie stehen als eigenständige *verteilbare Pakete*. Hierbei handelt es sich um architekturspezifischer ausführbaren Dateien, die zentrale Bereitstellung zu verwenden, um die verteilbaren Dateien auf dem Computer eines Benutzers zu installieren. Beispielsweise Vcredist\_x86.exe installiert die 32-Bit-Bibliotheken für X86 Computer, Vcredist\_x64.exe installiert die 32-Bit und 64-Bit-Bibliotheken für X64 Computer und Vcredist\_ARM.exe installiert die Bibliotheken für ARM Computer. Zentrale Bereitstellung wird empfohlen, da Microsoft Windows Update-Dienst verwenden kann, um diese Bibliotheken unabhängig voneinander aktualisieren. Neben der Kopie in Visual Studio-Installation die aktuelle verteilbare Pakete stehen zum Download auf [VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/) im Abschnitt Weitere Tools und Frameworks.

Die Hauptversionsnummer des verteilbaren Pakets, die Sie bereitstellen, muss die Version von Visual Studio-Toolsets verwendet, um Ihre Anwendung zu erstellen überein. Haben Visual Studio 2017 und Visual Studio 2015 kompatibel Toolset Versionsnummern, bedeutet, dass die Visual Studio-2017 verteilbare Dateien von apps, die erstellt, indem Sie das Toolset 2015 verwendet werden können. Während sie kompatibel sind, unterstützen wir nicht, verwenden die 2015 verteilbaren Dateien in apps, die mit dem 2017 Toolset erstellt. Es wird nur unterstützt, mit einem redistributable Package, die neuer als die Toolsetversion oder mit diesem identisch ist. Links zu den neuesten unterstützten redistributable-Pakete für ältere Toolsets, finden Sie unter [die neuesten unterstützt Visual C++-Downloads](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Bestimmte frühere Versionen von die verteilbaren Pakete finden Sie durch Suchen der [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431) für "Visual C++ Redistributable Packages".

Ist die Verwendung einer anderen Methode zum Einschließen von die verteilbaren DLLs in den Installer *Mergemodule*. Diese Microsoft Installer-Module sind in enthalten und durch das Installationsprogramm der Anwendung installiert wird. Mergemodule für die verteilbaren DLLs befinden sich in Ihrem Visual Studio-Installationsverzeichnis unter \\VC\\Redist\MSVC\\*Version*\\MergeModules\\ . In früheren Versionen von Visual Studio befinden sich diese Dateien Ihrem \\Programmdateien oder \\(x86) Programmdateiverzeichnis in eine gemeinsame Dateien\\Mergemodulen-Unterverzeichnis. Weitere Informationen zur Verwendung dieser Dateien finden Sie unter [Neuverteilen von Komponenten mit Mergemodulen](../ide/redistributing-components-by-using-merge-modules.md).

Die einzelnen verteilbaren DLLs sind ebenfalls in Ihrer Installation von Visual Studio enthalten. Standardmäßig werden sie in der Visual Studio-Installationsverzeichnis unter installiert die \\VC\\Redist\\MSVC\\*Version* Ordner. Die *Version* Zahlen möglicherweise andere kleinere Buildnummern einer einzelnen allgemeinen Satz von verteilbaren Dateien darstellen. Verwenden Sie die neueste Version von Library-DLL-Datei, verteilbare Paket oder Mergemodul in diese Verzeichnisse gefunden. Sie können diese Bibliotheken für die lokale Bereitstellung nach deren Installation in demselben Verzeichnis wie die Anwendung verwenden. Wird nicht die lokale Bereitstellung empfohlen, da Sie für das Übermitteln von Updates für Ihre bereitgestellte Anwendungen verantwortlich ist. Zentrale Bereitstellung mithilfe von die verteilbaren Pakete wird bevorzugt.

Um zu bestimmen, welche DLLs mit der Anwendung verteilt werden müssen, sammeln Sie eine Liste der DLLs, von denen die Anwendung abhängig ist. Diese werden normalerweise als Bibliothek Eingaben an den Linker importieren aufgelistet. Bestimmte Bibliotheken, z. B. Vcruntime und die universelle C Runtime Library (UCRT), sind standardmäßig eingeschlossen. Wenn Ihre app oder eine seiner Abhängigkeiten LoadLibrary verwendet, dynamisch auf eine DLL geladen, kann dieser DLL in den Eingaben an den Linker nicht aufgelistet. Eine Möglichkeit zum Sammeln der Liste dynamisch geladene DLLs zur Ausführung von Dependency Walker (depends.exe) auf Ihre app ist, wie in beschrieben [Grundlegendes zu den Abhängigkeiten einer Visual C++-Anwendung](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Leider wird dieses Tool veraltet ist und möglicherweise gemeldet, dass bestimmte DLLs gefunden werden kann.

Wenn Sie die Liste der Abhängigkeiten haben, vergleichen Sie sie der Liste, die in der Datei Redist.txt finden Sie unter der Microsoft Visual Studio-Installationsverzeichnis verknüpft oder die "REDIST-Liste" verteilbarer DLLs, die im Abschnitt "Verteilbarer Codedateien" verwiesen wird die Microsoft-softwarelizenzbedingungen für Ihre Kopie von Visual Studio. Visual Studio 2017 finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2017 (enthält Dienstprogramme, Erweiterbarkeit und BuildServer-Dateien)](http://go.microsoft.com/fwlink/p/?linkid=823098). Visual Studio 2015 finden Sie unter [verteilbarer Code für Microsoft Visual Studio 2015 und Microsoft Visual Studio 2015 SDK (enthält Dienstprogramme und BuildServer-Dateien)](http://go.microsoft.com/fwlink/p/?linkid=799794). Für Visual Studio 2013, die Liste steht online im [verteilbarer Code für Microsoft Visual Studio 2013 und Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603).

In Visual Studio-Versionen vor Visual Studio 2015, war der C-Laufzeitbibliothek (CRT) enthalten, als verteilbare DLL, in Msvc*Version*DLL. Ab Visual Studio 2015, wurden die CRT-Funktionen in der Vcruntime und die UCRT umgestaltet. Die UCRT ist nun eine Systemkomponente in Windows 10, die von Windows Update verwaltet werden. Es ist für alle Windows 10-Betriebssysteme verfügbar. Um Ihre Anwendung in älteren Betriebssystemen bereitzustellen, müssen Sie möglicherweise die UCRT sowie zu verteilen. Eine frühere Version der ucrt wird in der verteilbaren Visual Studio-Dateien, die nur auf Betriebssystemen vor Windows 10 installiert ist, enthalten und nur, wenn keine Version der ucrt bereits installiert ist. Eine installierbare Version der ucrt für Systeme mit Vorgängerversionen als ein Update von Microsoft System-Paket, finden Sie unter [Windows 10 universelle C-Laufzeit](https://www.microsoft.com/en-us/download/details.aspx?id=48234) im Microsoft Download Center.

Sie können nicht alle Dateien weiterverteilen, die in Visual Studio enthalten sind. Sie sind nur zur Weiterverteilung der Dateien berechtigt, die in "Redist.txt" oder in der "REDIST-Liste" online angegeben sind. Debugversionen von Anwendungen und die verschiedenen Visual C++-Debug-DLLs sind nicht weiterverteilbar. Weitere Informationen finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).

In der folgenden Tabelle werden einige der Visual C++-DLLs beschrieben, von denen Ihre Anwendung möglicherweise abhängig ist.

|Visual C++-Bibliothek|Beschreibung|Betrifft|
|--------------------------|-----------------|----------------|
|vcruntime*version*.dll|Runtime-Bibliothek für systemeigenen Code.|Anwendungen, die die normale C und C++ Language starten und Beenden eines Dienste verwenden.|
|vccorlib*version*.dll|Runtime-Bibliothek für verwalteten Code.|Anwendungen, die die C++-Sprache-Dienste für verwalteten Code verwenden.|
|msvcp*version*.dll and msvcp*version*_*dotnumber*.dll|C++-Standardbibliothek für systemeigenen Code.|Anwendungen, die die [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md).|
|concrt*version*.dll|Concurrency Runtime-Bibliothek für systemeigenen Code.|Anwendungen, die die [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).|
|mfc*version*.dll|Microsoft Foundation Class-Bibliothek (MFC-Bibliothek).|Anwendungen, die die [MFC-Bibliothek](../mfc/mfc-desktop-applications.md).|
|mfc*version* *language*.dll|Microsoft Foundation Class-Bibliotheksressourcen (MFC).|Anwendungen, die bestimmte Sprachressourcen für MFC zu verwenden.|
|mfc*version*u.dll|MFC-Bibliothek mit Unicode-Unterstützung.|Anwendungen, die die [MFC-Bibliothek](../mfc/mfc-desktop-applications.md) und Unicode-Unterstützung erfordern.|
|mfcmifc80.dll|MFC-Bibliothek für verwaltete Schnittstellen.|Anwendungen, die die [MFC-Bibliothek](../mfc/mfc-desktop-applications.md) mit [Windows Forms-Steuerelementen](/dotnet/framework/winforms/controls/index).|
|mfcm*version*.dll|Verwaltete MFC-Bibliothek.|Anwendungen, die die [MFC-Bibliothek](../mfc/mfc-desktop-applications.md) mit [Windows Forms-Steuerelementen](/dotnet/framework/winforms/controls/index).|
|mfcm*version*u.dll|Verwaltete MFC-Bibliothek mit Unicode-Unterstützung.|Anwendungen, die die [MFC-Bibliothek](../mfc/mfc-desktop-applications.md) mit [Windows Forms-Steuerelementen](/dotnet/framework/winforms/controls/index) und Unicode-Unterstützung erfordern.|
|vcamp*version*.dll|AMP-Bibliothek für systemeigenen Code.|Anwendungen, die die [C++ AMP-Bibliothek](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) Code.|
|vcomp*version*.dll|OpenMP-Bibliothek für systemeigenen Code.|Anwendungen, die die [OpenMP C++-Bibliothek](../parallel/openmp/openmp-in-visual-cpp.md) Code.|

> [!NOTE]
> Sie müssen nicht mehr die Active Template Library als eine separate DLL weiterverteilen. Die Funktionalität wurde in Header und eine statische Bibliothek verschoben.

Weitere Informationen zur weiterverteilung dieser DLLs mit Ihrer Anwendung finden Sie unter [Neuverteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md). Beispiele finden Sie unter [Bereitstellungsbeispiele](../ide/deployment-examples.md).

In der Regel müssen Sie keinen System-DLLs zu verteilen, da sie Teil des Betriebssystems sind. Allerdings gelten möglicherweise Ausnahmen, z. B., wenn die Anwendung auf mehreren Versionen von Microsoft-Betriebssystemen ausgeführt wird. In diesem Fall müssen Sie die entsprechenden Lizenzbedingungen lesen. Versuchen Sie außerdem, die System-DLLs entweder mittels Windows Update, Service Packs oder verteilbarer Pakete von Microsoft zu aktualisieren.

## <a name="see-also"></a>Siehe auch

[Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md)

[Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)
