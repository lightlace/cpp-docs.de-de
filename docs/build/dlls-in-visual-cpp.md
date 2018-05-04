---
title: DLLs in Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: facb085ae134c3ecea635ab68dd73f98e55488a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="dlls-in-visual-c"></a>DLLs in Visual C++  
  
In Windows ist eine Dynamic Link Library (DLL) eine Art der ausführbaren Datei, die eine gemeinsam genutzte Bibliothek von Funktionen und Ressourcen fungiert. Dynamisches Verknüpfen ist ein Betriebssystem-Funktion, die ermöglicht eine ausführbare Datei, Funktionen aufzurufen oder Ressourcen in einer separaten Datei gespeichert. Diese Funktionen und Ressourcen können getrennt von den ausführbaren Dateien, von denen sie verwendet werden, kompiliert und bereitgestellt werden. Eine DLL ist nicht eigenständig ausführbare Dateien. Es wird im Kontext einer Anwendung, die ihn aufruft. Das Betriebssystem kann die DLL in Speicherbereich einer Anwendung laden, wenn die Anwendung geladen wird (*implizite Verknüpfung*), oder bei Bedarf zur Laufzeit (*explizite Verknüpfung*). DLLs machen es außerdem einfach, Funktionen und Ressourcen in ausführbaren Dateien gemeinsam zu nutzen. Mehrere Anwendungen können gleichzeitig auf den Inhalt einer einzigen Kopie einer im Arbeitsspeicher enthaltenen DLL zugreifen.  
  
## <a name="differences-between-dynamic-linking-and-static-linking"></a>Unterschiede zwischen dynamisches Verknüpfen und statische Verknüpfung  
  
Statisches verknüpfen kopiert den Objektcode in einer statischen Bibliothek in den ausführbaren Dateien, die sie verwenden, wenn sie erstellt werden. Dynamisches Verknüpfen bindet nur die Informationen, die von Windows benötigt werden, zur Laufzeit zu suchen und Laden der DLL, die ein Datenelement oder die Funktion enthält. Wenn Sie eine DLL erstellen, erstellen Sie auch eine Importbibliothek, die diese Informationen enthält. Wenn Sie eine ausführbare Datei, die die DLL aufruft erstellen, verwendet der Linker die exportierten Symbole in der Importbibliothek her, um diese Informationen für das Windows-Ladeprogramm zu speichern. Wenn das Ladeprogramm eine DLL geladen wird, wird die DLL in den Speicherbereich Ihrer Anwendung zugeordnet. Falls vorhanden, eine spezielle Funktion, in der DLL `DllMain`, wird aufgerufen, um die Initialisierung auszuführen, die die DLL benötigt.  
  
<a name="differences-between-applications-and-dlls"></a>  
  
## <a name="differences-between-applications-and-dlls"></a>Unterschiede zwischen Anwendungen und DLLs  
  
Obwohl DLLs und Anwendungen sowohl ausführbare Module sind, unterscheiden sich jedoch auf unterschiedliche Weise. Für den Endbenutzer ist der offensichtlichste Unterschied, dass DLLs keine Anwendungen sind, die direkt ausgeführt werden können. Im Hinblick auf das System gibt es zwei grundsätzliche Unterschiede zwischen Anwendungen und DLLs:  
  
-   Von einer Anwendung können mehrere Instanzen gleichzeitig im System ausgeführt werden, während eine DLL nur eine Instanz haben kann.  
  
-   Als ein Prozess, der Besitzer der Dinge, wie ein Stapel, Threads, die der Ausführung, globalen Arbeitsspeicher, Dateihandles und eine Warteschlange kann eine Anwendung geladen werden, jedoch nicht von einer DLL.  
  
<a name="advantages-of-using-dlls"></a>  
  
## <a name="advantages-of-using-dlls"></a>Vorteile der Verwendung von DLLs  
  
Dynamisches Verknüpfen gegenüber der statischen Verknüpfung zu Code und Ressourcen, eine Reihe von Vorteilen. Wenn Sie DLLs verwenden, können Sie Speicherplatz sparen und Auslagerungsvorgänge (Swapping) verringern. Wenn mehrere Anwendungen eine einzige Kopie einer DLL verwenden können, können Sie Speicherplatz und Downloadbandbreite sparen. DLLs können getrennt bereitgestellt und aktualisiert werden, wodurch Sie Wartungsunterstützung und Softwareupdates bereitstellen können, ohne Ihren gesamten Code erneut erstellen zu müssen. DLLs bieten eine bequeme Möglichkeit, gebietsschemaspezifische Ressourcen bereitzustellen, die mehrsprachige Programme unterstützen können, und vereinfachen ein Erstellen von internationalen Versionen Ihrer Anwendungen. Explizite Verknüpfung, können Ihre Anwendung zu ermitteln und Laden von DLLs zur Laufzeit, z. B. Erweiterungen, die neue Funktionen bereitstellen.  
  
Die dynamische Verknüpfung hat die folgenden Vorteile:  
  
-   Dynamisches Verknüpfen Sie spart Arbeitsspeicher und reduziert die Auslagerung. Viele Prozesse können eine DLL gleichzeitig verwenden eine einzige Kopie von nur-Lese Bestandteile einer DLL im Arbeitsspeicher freigeben. Im Gegensatz dazu verfügt jede Anwendung, die erstellt wird, mithilfe einer statisch verknüpften Bibliothek eine vollständige Kopie des Bibliothekscodes, die Windows in den Arbeitsspeicher geladen werden müssen.  
  
-   Dynamisches Verknüpfen spart Speicherplatz und Netzwerkbandbreite. Viele Anwendungen können eine einzelne, auf der Festplatte gespeicherte Kopie der DLL gemeinsam nutzen. Im Gegensatz dazu wird für jede Anwendung, die mit einer static Link Library erstellt der Bibliothekscode in deren ausführbares Bild, die mehr Speicherplatz verwendet, und nimmt mehr Bandbreite zum übertragen wurde.  
  
-   Sicherheitsupdates für Wartung und Upgrades können einfacher sein. Wenn Ihre Anwendungen häufig verwendete Funktionen in einer DLL verwenden, können dann so lange die Funktionsargumente und Rückgabewerte nicht ändern, Fehlerbehebungen zu implementieren und Bereitstellen von Softwareupdates auf die DLL. Wenn DLLs aktualisiert werden, die Anwendungen, die sie verwenden müssen nicht neu kompiliert oder neu verknüpft werden, und sie machen die neue DLL verwendet werden, sobald er bereitgestellt wird. Im Gegensatz dazu erfordern Fixes, die Sie statisch verknüpfter Objektcode stellen Sie verknüpfen und erneute Bereitstellung jeder Anwendung, die verwendet werden.  
  
-   DLLs können um Vermarktung zu unterstützen. Eine Treiber-DLL für ein Anzeigegerät kann z. B. so geändert werden, dass ein Gerät unterstützt wird, das zum Zeitpunkt der Auslieferung der Anwendung noch gar nicht verfügbar war. Sie können mit der Anwendung als DLLs laden explizite Verknüpfung und neue Funktionalität in Ihrer app hinzufügen, ohne das Neuerstellen oder ihn erneut bereitzustellen.  
  
-   Dynamisches Verknüpfen erleichtert die Unterstützung von Anwendungen, die in verschiedenen Programmiersprachen erstellt wurden. Programme, die in verschiedenen Programmiersprachen erstellt wurden, können dieselbe DLL-Funktion aufrufen, solange sie die Aufrufkonvention der Funktion einhalten. Die Programme und die DLL-Funktion müssen in folgenden Punkten kompatibel sein: die von der Funktion erwartete Reihenfolge, in der Argumente auf den Stapel verschoben werden, ob die Funktion oder die Anwendung für das Bereinigen des Stapels verantwortlich ist und ob Argumente in Registern übergeben werden.  
  
-   Die dynamische Verknüpfung bietet einen Mechanismus zum Erweitern der MFC-Bibliotheksklassen. Sie können Klassen von bestehenden MFC-Klassen ableiten und diese in einer MFC-Erweiterungs-DLL speichern, die dann von MFC-Anwendungen genutzt werden kann.  
  
-   Dynamisches Verknüpfen erleichtert die Erstellung von internationalen Versionen Ihrer Anwendung. Gebietsschemaspezifische Ressourcen in einer DLL platzieren, ist es viel einfacher, internationale Versionen einer Anwendung zu erstellen. Anstelle von Protokollversand viele lokalisierte Versionen der Anwendung, Sie können die Zeichenfolgen und Bilder für jede Sprache in einer separaten Ressourcen-DLL platzieren, und Ihre Anwendung kann dann die entsprechenden Ressourcen für dieses Gebietsschema zur Laufzeit laden.   
  
 Ein potenzieller Nachteil von DLLs ist, dass die Anwendung nicht eigenständig ist. Es hängt die Existenz eines separaten DLL-Moduls, die Sie bereitstellen oder sich selbst als Teil der Installation überprüfen müssen.  
  
  
## <a name="more-information-on-how-to-create-and-use-dlls"></a>Weitere Informationen zum Erstellen und Verwenden von DLLs  
  
Die folgenden Themen enthalten ausführliche Informationen dazu, wie DLLs in Visual C++ programmiert.  
  
 [Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Beschreibt, wie Sie mit Visual Studio eine DLL erstellen und verwenden.  
  
 [Arten von DLLs](../build/kinds-of-dlls.md)  
 Bietet Informationen zu den verschiedenen Arten von DLLs, die erstellt werden können.  
  
 [DLL-häufig gestellte Fragen](../build/dll-frequently-asked-questions.md)  
 Bietet Antworten auf häufig gestellte Fragen zu DLLs.  
  
 [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](../build/linking-an-executable-to-a-dll.md)  
 Beschreibt das explizite und implizite Verknüpfen mit einer DLL.  
  
 [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
 Erläutert die Initialisierungscode einer DLL, die beim Laden der DLL ausgeführt werden muss.  
  
 [DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../build/run-time-library-behavior.md)  
 Beschreibt, wie die DLL-Startsequenz durch die Laufzeitbibliothek ausgeführt wird.  
  
 [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 Erläutert die Verwendung von **LoadLibrary** und `AfxLoadLibrary` zum expliziten Verknüpfen einer DLL zur Laufzeit.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 Erläutert die Verwendung von **GetProcAddress** zum Abrufen der Adresse einer exportierten Funktion in der DLL.  
  
 [FreeLibrary und AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 Erläutert die Verwendung von **FreeLibrary** und `AfxFreeLibrary` Wenn DLL-Modul nicht mehr benötigt wird.  
  
 [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 Beschreibt den Suchpfad, der von Windows verwendet wird, um eine DLL im System zu finden.  
  
 [Module States of a Regular MFC DLL Dynamically Linked to MFC (Modulzustände einer regulären, dynamisch mit MFC verknüpften MFC-DLL)](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 Beschreibt die Modulzustände einer regulären, die MFC-DLL dynamisch mit MFC verknüpft.  
  
 [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls-overview.md)  
 Erläutert DLLs, die typischerweise wiederverwendbare Klassen implementieren, welche von bestehenden Microsoft Foundation Class Library-Klassen abgeleitet wurden.  
  
 [Erstellen einer DLL als reine Ressource](../build/creating-a-resource-only-dll.md)  
 Erörtert eine reine Ressourcen-DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder.  
  
 [Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 Bietet erweiterte Unterstützung für Satelliten-DLLs, eine Funktion, die den Entwickler bei der Erstellung von Anwendungen unterstützt, die für mehrere Sprachen lokalisiert sind.  
  
 [Importieren und Exportieren](../build/importing-and-exporting.md)  
 Beschreibt das Importieren öffentlicher Symbole in eine Anwendung bzw. das Exportieren von Funktionen aus einer DLL.  
  
 [Active Technology und DLLs](../build/active-technology-and-dlls.md)  
 Bietet die Möglichkeit, Objektserver innerhalb einer DLL zu implementieren.  
  
 [Automatisierung in einer DLL](../build/automation-in-a-dll.md)  
 Beschreibt, welche Features die Automatisierungsoption im MFC-DLL-Assistenten bereitstellt.  
  
 [Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)  
 Erörtert, nach welcher strukturierten Namenskonvention die in MFC enthaltenen DLLs und Bibliotheken benannt sind.  
  
 [Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Beschreibt den Aufruf von DLL-Funktionen aus Visual Basic-Anwendungen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
 [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 Beschreibt reguläre DLLs MFC, denen Sie die MFC-Bibliothek als Bestandteil einer Dynamic Link Library von Windows verwenden können.  
  
 [DLL Version of MFC](../mfc/tn033-dll-version-of-mfc.md)  
 Beschreibt, wie können Sie die MFCxx.dll und MFCxxD.dll (wobei x für die MFC-Versionsnummer steht), MFC-Anwendungen und MFC-Erweiterungs-DLLs Dynamic Link Libraries freigegeben.  
