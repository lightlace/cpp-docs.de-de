---
title: "DLLs in Visual C++"
ms.custom: na
ms.date: "12/03/2016"
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
  - "DLLs [C++]"
  - "DLLs [C++], Informationen über DLLs"
  - "Dynamisches Verknüpfen [C++]"
  - "Ausführbare Dateien [C++]"
  - "Verknüpfen [C++], Dynamisch und statisch im Vergleich"
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# DLLs in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Dynamic Link Library \(DLL\) ist eine ausführbare Datei, die als eine gemeinsam genutzte Bibliothek von Funktionen und Ressourcen fungiert.  Dynamisches Verknüpfen \(Linken\) ermöglicht es einer ausführbaren Datei, Funktionen aufzurufen oder Ressourcen zu verwenden, die in einer separaten Datei gespeichert sind.  Diese Funktionen und Ressourcen können getrennt von den ausführbaren Dateien, von denen sie verwendet werden, kompiliert und bereitgestellt werden.  Das Betriebssystem kann die jeweilige DLL in den Speicherbereich der ausführbaren Datei laden, wenn diese geladen wird, oder auf Anforderung zur Laufzeit laden.  DLLs machen es außerdem einfach, Funktionen und Ressourcen in ausführbaren Dateien gemeinsam zu nutzen.  Mehrere Anwendungen können gleichzeitig auf den Inhalt einer einzigen Kopie einer im Arbeitsspeicher enthaltenen DLL zugreifen.  
  
 Statisches Verknüpfen kopiert den gesamten Objektcode, der sich in einer LIB\-Datei befindet, in eine ausführbare Datei.  Dynamisches Verknüpfen bindet nur die Informationen ein, die zur Laufzeit benötigt werden, um die DLL zu finden und zu laden, in der ein Datenelement oder eine Funktion enthalten ist.  Wenn Sie eine DLL erstellen, erstellen Sie auch eine LIB\-Datei, die diese Informationen enthält.  Wenn Sie eine ausführbare Datei erstellen, die die DLL aufruft, verwendet der Linker die exportierten Symbole in der LIB\-Datei, um diese Informationen für das Ladeprogramm zu speichern.  Wenn das Ladeprogramm eine DLL lädt, wird die DLL in den Speicherbereich Ihrer ausführbaren Datei eingebunden.  In der DLL wird die spezielle Funktion `DllMain` aufgerufen, um die Initialisierung auszuführen, die die DLL benötigt.  
  
 Die dynamische Verknüpfung bietet gegenüber der statischen Verknüpfung verschiedene Vorteile.  Wenn Sie DLLs verwenden, können Sie Speicherplatz sparen und Auslagerungsvorgänge \(Swapping\) verringern.  Wenn mehrere Anwendungen eine einzige Kopie einer DLL verwenden können, können Sie Speicherplatz und Downloadbandbreite sparen.  DLLs können getrennt bereitgestellt und aktualisiert werden, wodurch Sie Wartungsunterstützung und Softwareupdates bereitstellen können, ohne Ihren gesamten Code erneut erstellen zu müssen.  DLLs bieten eine bequeme Möglichkeit, gebietsschemaspezifische Ressourcen bereitzustellen, die mehrsprachige Programme unterstützen können, und vereinfachen ein Erstellen von internationalen Versionen Ihrer Anwendungen.  
  
 Die folgenden Themen enthalten ausführliche Informationen dazu, wie DLLs programmiert werden.  
  
## In diesem Abschnitt  
 [Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library \(C\+\+\)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Beschreibt, wie Sie mit Visual Studio eine DLL erstellen und verwenden.  
  
 [Unterschiede zwischen Anwendungen und DLLs](../build/differences-between-applications-and-dlls.md)  
 Beschreibt die grundlegenden Unterschiede zwischen Anwendungen und DLLs.  
  
 [Vorteile der Verwendung von DLLs](../build/advantages-of-using-dlls.md)  
 Beschreibt die Vorteile von dynamischen Verknüpfungen.  
  
 [Arten von DLLs](../build/kinds-of-dlls.md)  
 Bietet Informationen zu den verschiedenen Arten von DLLs, die erstellt werden können.  
  
 [Häufig gestellte Fragen \(FAQs\)zu DLLs](../build/dll-frequently-asked-questions.md)  
 Bietet Antworten auf häufig gestellte Fragen zu DLLs.  
  
 [Verknüpfen einer ausführbaren Datei mit einer DLL](../build/linking-an-executable-to-a-dll.md)  
 Beschreibt das explizite und implizite Verknüpfen mit einer DLL.  
  
 [Initialisieren einer DLL](../build/initializing-a-dll.md)  
 Beschreibt den Initialisierungscode einer DLL \(z. B. den zur Speicherbelegung\), der beim Laden der DLL ausgeführt werden muss.  
  
 [Verhalten der Laufzeitbibliothek](../build/run-time-library-behavior.md)  
 Beschreibt, wie die DLL\-Startsequenz durch die Laufzeitbibliothek ausgeführt wird.  
  
 ["LoadLibrary" und "AfxLoadLibrary"](../build/loadlibrary-and-afxloadlibrary.md)  
 Erörtert die Verwendung von **LoadLibrary** und `AfxLoadLibrary` zum expliziten Verknüpfen \(Linken\) einer DLL zur Laufzeit.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 Erörtert die Verwendung von **GetProcAddress**, um die Adresse einer exportierten Funktion in der DLL abzurufen.  
  
 ["FreeLibrary" und "AfxFreeLibrary"](../build/freelibrary-and-afxfreelibrary.md)  
 Beschreibt die Verwendung von **FreeLibrary** und `AfxFreeLibrary` in Situationen, in denen das DLL\-Modul nicht länger benötigt wird.  
  
 [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 Beschreibt den Suchpfad, der von Windows verwendet wird, um eine DLL im System zu finden.  
  
 [Modulzustände einer regulären, dynamisch mit MFC verknüpften DLL](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 Beschreibt die Modulzustände einer regulären, dynamisch mit MFC verknüpften DLL.  
  
 [Erweiterungs\-DLLs](../build/extension-dlls-overview.md)  
 Erläutert DLLs, die typischerweise wiederverwendbare Klassen implementieren, welche von bestehenden Microsoft Foundation Class Library\-Klassen abgeleitet wurden.  
  
 [Erstellen einer DLL als reine Ressource](../build/creating-a-resource-only-dll.md)  
 Erörtert eine reine Ressourcen\-DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder.  
  
 [Lokalisierte Ressourcen in MFC\-Anwendungen: Satelliten\-DLLs](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 Bietet erweiterte Unterstützung für Satelliten\-DLLs, ein Feature, das den Entwickler bei der Erstellung von Anwendungen unterstützt, die für mehrere Sprachen lokalisiert sind.  
  
 [Importieren und Exportieren](../build/importing-and-exporting.md)  
 Beschreibt das Importieren öffentlicher Symbole in eine Anwendung bzw. das Exportieren von Funktionen aus einer DLL.  
  
 [Active Technology und DLLs](../build/active-technology-and-dlls.md)  
 Bietet die Möglichkeit, Objektserver innerhalb einer DLL zu implementieren.  
  
 [Automatisierung in einer DLL](../build/automation-in-a-dll.md)  
 Beschreibt, welche Features die Automatisierungsoption im MFC\-DLL\-Assistenten bereitstellt.  
  
 [Namenskonventionen für MFC\-DLLs](../build/naming-conventions-for-mfc-dlls.md)  
 Erörtert, nach welcher strukturierten Namenskonvention die in MFC enthaltenen DLLs und Bibliotheken benannt sind.  
  
 [Aufrufen von DLL\-Funktionen aus Visual Basic\-Anwendungen heraus](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Beschreibt den Aufruf von DLL\-Funktionen aus Visual Basic\-Anwendungen.  
  
## Verwandte Abschnitte  
 [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 Beschreibt reguläre DLLs, über die Sie die MFC\-Bibliothek als Bestandteil einer Windows\-DLL \(Dynamic Link Library\) verwenden können.  
  
 [DLL Version of MFC \(nur auf Englisch verfügbar\)](../mfc/tn033-dll-version-of-mfc.md)  
 Beschreibt, wie die gemeinsam genutzten Dynamic Link Libraries MFCxx.dll und MFCxxD.dll \(wobei x für die MFC\-Versionsnummer steht\) mit MFC\-Anwendungen und Erweiterungs\-DLLs verwendet werden können.  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](assetId:///0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Enthält Links zu Themen, die grundlegende Informationen über Visual C\+\+\-Bibliotheken bieten, sowie zu Themen, in denen unterschiedliche Codierungstechnologien und \-verfahren erläutert werden.