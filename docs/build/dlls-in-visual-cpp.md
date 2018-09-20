---
title: DLLs in Visual C++ | Microsoft-Dokumentation
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
ms.openlocfilehash: 4ea5026100239f00f03147e435ddd9555617f1dd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432710"
---
# <a name="dlls-in-visual-c"></a>DLLs in Visual C++

In Windows ist eine Dynamic Link Library (DLL) eine Art der ausführbaren Datei, die eine gemeinsam genutzte Bibliothek von Funktionen und Ressourcen fungiert. Dynamisches Verknüpfen ist eine Betriebssystem-Funktion, die es eine ausführbare Datei ermöglicht, Funktionen aufzurufen, oder verwenden die Ressourcen, die in einer separaten Datei gespeichert. Diese Funktionen und Ressourcen können getrennt von den ausführbaren Dateien, von denen sie verwendet werden, kompiliert und bereitgestellt werden. Eine DLL-Datei ist nicht über eine eigenständige ausführbare Datei. Es wird im Kontext einer Anwendung, die ihn aufruft. Das Betriebssystem kann die DLL in Speicherbereich einer Anwendung laden, wenn die Anwendung geladen wird (*implizite Verknüpfung*), oder bei Bedarf zur Laufzeit (*explizite Verknüpfung*). DLLs machen es außerdem einfach, Funktionen und Ressourcen in ausführbaren Dateien gemeinsam zu nutzen. Mehrere Anwendungen können gleichzeitig auf den Inhalt einer einzigen Kopie einer im Arbeitsspeicher enthaltenen DLL zugreifen.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>Unterschiede zwischen dynamisches Verknüpfen und statische Verknüpfung

Statisches verknüpfen kopiert den Objektcode in einer statischen Bibliothek in die ausführbare Dateien, die sie verwenden, wenn sie erstellt werden. Dynamisches Verknüpfen bindet nur die Informationen, die von Windows benötigt werden, zur Laufzeit zu suchen und laden die DLL, die ein Datenelement oder die Funktion enthält. Wenn Sie eine DLL-Datei erstellen, erstellen Sie auch eine Importbibliothek, die diese Informationen enthält. Wenn Sie eine ausführbare Datei, die die DLL aufruft erstellen, verwendet der Linker die exportierten Symbole in der Importbibliothek her, um diese Informationen für das Windows-Ladeprogramm zu speichern. Wenn das Ladeprogramm eine DLL geladen wird, wird die DLL in den Speicherbereich Ihrer Anwendung zugeordnet. Falls vorhanden, eine spezielle Funktion, in der DLL `DllMain`, wird aufgerufen, um die Initialisierung auszuführen, die DLL benötigt.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>Unterschiede zwischen Anwendungen und DLLs

Auch wenn die DLLs und Anwendungen sowohl ausführbare Module sind, unterscheiden sie sich auf verschiedene Weise. Für den Endbenutzer ist der deutlichste Unterschied darin, dass DLLs keine Anwendungen sind, die direkt ausgeführt werden können. Im Hinblick auf das System gibt es zwei grundsätzliche Unterschiede zwischen Anwendungen und DLLs:

- Von einer Anwendung können mehrere Instanzen gleichzeitig im System ausgeführt werden, während eine DLL nur eine Instanz haben kann.

- Eine Anwendung kann als ein Prozess, der Besitzer der Dinge, wie z. B. einen Stapel, Threads, der Ausführung, globalen Arbeitsspeicher, Dateihandles und eine Warteschlange geladen werden, aber eine DLL-Datei kann nicht aus.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Vorteile der Verwendung von DLLs

Dynamisches verknüpfen, anstatt eine statische Verknüpfung zu Code und Ressourcen bietet mehrere Vorteile. Wenn Sie DLLs verwenden, können Sie Speicherplatz sparen und Auslagerungsvorgänge (Swapping) verringern. Wenn mehrere Anwendungen eine einzige Kopie einer DLL verwenden können, können Sie Speicherplatz und Downloadbandbreite sparen. DLLs können getrennt bereitgestellt und aktualisiert werden, wodurch Sie Wartungsunterstützung und Softwareupdates bereitstellen können, ohne Ihren gesamten Code erneut erstellen zu müssen. DLLs bieten eine bequeme Möglichkeit, gebietsschemaspezifische Ressourcen bereitzustellen, die mehrsprachige Programme unterstützen können, und vereinfachen ein Erstellen von internationalen Versionen Ihrer Anwendungen. Explizite Verknüpfung, können Ihre Anwendung ermitteln und Laden von DLLs zur Laufzeit, z. B. Erweiterungen, die neue Funktionen zu bieten.

Die dynamische Verknüpfung hat die folgenden Vorteile:

- Dynamisches Verknüpfen Sie spart Arbeitsspeicher und reduziert die Auslagerung. Viele Prozesse können eine DLL gleichzeitig eine einzelne Kopie der schreibgeschützten Teile einer im Arbeitsspeicher enthaltenen DLL. Im Gegensatz dazu hat jede Anwendung, die mithilfe einer statisch verknüpften Bibliothek erstellt wird, eine vollständige Kopie des Bibliothekscodes, die von Windows in den Arbeitsspeicher geladen werden müssen.

- Dynamisches Verknüpfen zur spart Speicherplatz und Bandbreite. Viele Anwendungen können eine einzelne, auf der Festplatte gespeicherte Kopie der DLL gemeinsam nutzen. Im Gegensatz dazu hat jede Anwendung, die mit einer static Link Library erstellt den Bibliothekscode in deren ausführbares Image, die mehr Speicherplatz verwendet, und nimmt mehr Bandbreite zum Übertragen von verknüpft.

- Sicherheitsfixes für Wartung und Upgrades können einfacher sein. Wenn Ihre Anwendungen allgemeine Funktionen in einer DLL verwenden, können klicken Sie dann so lange die Funktionsargumente und Rückgabewerte nicht ändern, Sie Fehlerbehebungen zu implementieren und Bereitstellen von Softwareupdates auf die DLL. Wenn DLLs aktualisiert werden, die Anwendungen, die sie verwenden müssen nicht erneut kompiliert oder erneut verknüpft werden soll, und sie stellen die neue DLL verwendet werden, sobald er bereitgestellt wird. Im Gegensatz dazu erfordern Fixes, die Sie in statisch verknüpfter Objektcode vornehmen neu verknüpfen und erneute Bereitstellung jeder Anwendung, der verwendet wird.

- DLLs können Sie um nach der Vermarktung zu unterstützen. Eine Treiber-DLL für ein Anzeigegerät kann z. B. so geändert werden, dass ein Gerät unterstützt wird, das zum Zeitpunkt der Auslieferung der Anwendung noch gar nicht verfügbar war. Sie können explizite Verknüpfung verwenden, Erweiterungen als DLLs geladen und Hinzufügen von neuen Funktionen zu Ihrer app ohne Neuerstellung oder erneute Bereitstellung.

- Dynamisches Verknüpfen zur erleichtert die Unterstützung von Anwendungen, die in verschiedenen Programmiersprachen geschrieben wurden. Programme, die in verschiedenen Programmiersprachen erstellt wurden, können dieselbe DLL-Funktion aufrufen, solange sie die Aufrufkonvention der Funktion einhalten. Die Programme und die DLL-Funktion müssen in folgenden Punkten kompatibel sein: die von der Funktion erwartete Reihenfolge, in der Argumente auf den Stapel verschoben werden, ob die Funktion oder die Anwendung für das Bereinigen des Stapels verantwortlich ist und ob Argumente in Registern übergeben werden.

- Die dynamische Verknüpfung bietet einen Mechanismus zur Erweiterung der MFC-Bibliotheksklassen. Sie können Klassen von bestehenden MFC-Klassen ableiten und diese in einer MFC-Erweiterungs-DLL speichern, die dann von MFC-Anwendungen genutzt werden kann.

- Dynamisches Verknüpfen zur erleichtert die Erstellung von internationalen Versionen Ihrer Anwendung. Platzieren Sie gebietsschemaspezifische Ressourcen in einer DLL, ist es viel einfacher, internationale Versionen einer Anwendung zu erstellen. Anstelle von Protokollversand viele lokalisierte Versionen Ihrer Anwendung können Sie die Zeichenfolgen und Bilder für jede Sprache in einer separaten Ressourcen-DLL platzieren, und klicken Sie dann die Anwendung die entsprechenden Ressourcen für dieses Gebietsschema zur Laufzeit laden kann.

Ein potenzieller Nachteil bei der Verwendung von DLLs ist, dass die Anwendung nicht eigenständig ist. Es setzt das Vorhandensein einer separaten DLL-Moduls, die Sie bereitstellen oder sich im Rahmen der Installation überprüfen müssen.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Weitere Informationen zum Erstellen und Verwenden von DLLs

Die folgenden Themen enthalten ausführliche Informationen zur Verwendung DLLs in Visual C++ programmiert.

[Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Beschreibt, wie Sie mit Visual Studio eine DLL erstellen und verwenden.

[Arten von DLLs](../build/kinds-of-dlls.md)<br/>
Bietet Informationen zu den verschiedenen Arten von DLLs, die erstellt werden können.

[DLL-häufig gestellte Fragen](../build/dll-frequently-asked-questions.md)<br/>
Bietet Antworten auf häufig gestellte Fragen zu DLLs.

[Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](../build/linking-an-executable-to-a-dll.md)<br/>
Beschreibt das explizite und implizite Verknüpfen mit einer DLL.

[Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)<br/>
Erläutert die Initialisierungscode einer DLL, die beim Laden der DLL ausgeführt werden muss.

[DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../build/run-time-library-behavior.md)<br/>
Beschreibt, wie die DLL-Startsequenz durch die Laufzeitbibliothek ausgeführt wird.

[LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)<br/>
Erläutert die Verwendung von **LoadLibrary** und `AfxLoadLibrary` zum expliziten Verknüpfen einer DLL zur Laufzeit.

[GetProcAddress](../build/getprocaddress.md)<br/>
Erläutert die Verwendung von **GetProcAddress** zum Abrufen der Adresse einer exportierten Funktion in der DLL.

[FreeLibrary und AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)<br/>
Erläutert die Verwendung von **FreeLibrary** und `AfxFreeLibrary` Wenn das DLL-Modul nicht mehr benötigt wird.

[Dynamic Link Library Search Order](/windows/desktop/Dlls/dynamic-link-library-search-order)<br/>
Beschreibt den Suchpfad, der von Windows verwendet wird, um eine DLL im System zu finden.

[Module States of a Regular MFC DLL Dynamically Linked to MFC (Modulzustände einer regulären, dynamisch mit MFC verknüpften MFC-DLL)](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
Beschreibt die Modulzustände einer regulären, die MFC-DLL dynamisch mit MFC verknüpften an.

[MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls-overview.md)<br/>
Erläutert DLLs, die typischerweise wiederverwendbare Klassen implementieren, welche von bestehenden Microsoft Foundation Class Library-Klassen abgeleitet wurden.

[Erstellen einer DLL als reine Ressource](../build/creating-a-resource-only-dll.md)<br/>
Erörtert eine reine Ressourcen-DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder.

[Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs](../build/localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
Bietet erweiterte Unterstützung für Satelliten-DLLs, eine Funktion, die den Entwickler bei der Erstellung von Anwendungen unterstützt, die für mehrere Sprachen lokalisiert sind.

[Importieren und Exportieren](../build/importing-and-exporting.md)<br/>
Beschreibt das Importieren öffentlicher Symbole in eine Anwendung bzw. das Exportieren von Funktionen aus einer DLL.

[Active Technology und DLLs](../build/active-technology-and-dlls.md)<br/>
Bietet die Möglichkeit, Objektserver innerhalb einer DLL zu implementieren.

[Automatisierung in einer DLL](../build/automation-in-a-dll.md)<br/>
Beschreibt, welche Features die Automatisierungsoption im MFC-DLL-Assistenten bereitstellt.

[Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
Erörtert, nach welcher strukturierten Namenskonvention die in MFC enthaltenen DLLs und Bibliotheken benannt sind.

[Aufrufen von DLL-Funktionen aus Visual Basic-Anwendungen](../build/calling-dll-functions-from-visual-basic-applications.md)<br/>
Beschreibt den Aufruf von DLL-Funktionen aus Visual Basic-Anwendungen.

## <a name="related-sections"></a>Verwandte Abschnitte

[Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
Beschreibt reguläre MFC-DLLs, mit denen Sie die MFC-Bibliothek als Bestandteil einer Dynamic Link Library von Windows verwenden können.

[DLL-Version von MFC](../mfc/tn033-dll-version-of-mfc.md)<br/>
Beschreibt, wie können Sie die MFCxx.dll und MFCxxD.dll (wobei x für die MFC-Versionsnummer ist), Dynamic Link Libraries für MFC-Anwendungen und MFC-Erweiterungs-DLLs zu freigegeben.
