---
title: Erstellen von CC++ /DLLs in Visual Studio
ms.date: 07/18/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 33f002143e306c99b4d17b7a01ddd4a9738e38e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493275"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Erstellen von CC++ /DLLs in Visual Studio

In Windows ist eine Dynamic Link Library (dll) eine Art ausführbare Datei, die als freigegebene Bibliothek von Funktionen und Ressourcen fungiert. Dynamic Linking ist eine Funktion des Betriebssystems, mit der eine ausführbare Dateifunktionen aufruft oder Ressourcen verwendet, die in einer separaten Datei gespeichert sind. Diese Funktionen und Ressourcen können getrennt von den ausführbaren Dateien, von denen sie verwendet werden, kompiliert und bereitgestellt werden. Eine dll ist keine eigenständige ausführbare Datei. Er wird im Kontext einer Anwendung ausgeführt, die ihn aufruft. Das Betriebssystem kann die dll in den Speicherbereich einer Anwendung laden, wenn die Anwendung geladen wird (*implizites verknüpfen*), oder bei Bedarf zur Laufzeit (*explizite Verknüpfung*). DLLs machen es außerdem einfach, Funktionen und Ressourcen in ausführbaren Dateien gemeinsam zu nutzen. Mehrere Anwendungen können gleichzeitig auf den Inhalt einer einzigen Kopie einer im Arbeitsspeicher enthaltenen DLL zugreifen.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>Unterschiede zwischen dynamischem verknüpfen und statischem verknüpfen

Statisches verknüpfen kopiert den gesamten Objektcode in einer statischen Bibliothek in die ausführbaren Dateien, die diese verwenden, wenn Sie erstellt werden. Die dynamische Verknüpfung umfasst nur die Informationen, die von Windows zur Laufzeit benötigt werden, um die dll zu suchen und zu laden, die ein Datenelement oder eine Funktion enthält. Wenn Sie eine DLL erstellen, erstellen Sie auch eine Import Bibliothek, die diese Informationen enthält. Wenn Sie eine ausführbare Datei erstellen, die die DLL aufruft, verwendet der Linker die exportierten Symbole in der Import Bibliothek, um diese Informationen für das Windows-Lade Programm zu speichern. Wenn das Lade Modul eine DLL lädt, wird die dll im Speicherbereich der Anwendung zugeordnet. Falls vorhanden, wird eine spezielle Funktion in der DLL `DllMain`,, aufgerufen, um jede Initialisierung auszuführen, die die dll benötigt.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>Unterschiede zwischen Anwendungen und DLLs

Obwohl es sich bei DLLs und Anwendungen um ausführbare Module handelt, unterscheiden Sie sich auf verschiedene Weise. Für den Endbenutzer liegt der offensichtlichste Unterschied darin, dass es sich bei DLLs nicht um Anwendungen handelt, die direkt ausgeführt werden können. Im Hinblick auf das System gibt es zwei grundsätzliche Unterschiede zwischen Anwendungen und DLLs:

- Von einer Anwendung können mehrere Instanzen gleichzeitig im System ausgeführt werden, während eine DLL nur eine Instanz haben kann.

- Eine Anwendung kann als Prozess geladen werden, der Elemente wie einen Stapel, Ausführungs Threads, globalen Arbeitsspeicher, Datei Handles und eine Nachrichten Warteschlange, aber eine DLL, besitzen kann.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Vorteile der Verwendung von DLLs

Dynamisches Verknüpfen mit Code und Ressourcen bietet im Vergleich zur statischen Verknüpfung mehrere Vorteile:

- Die dynamische Verknüpfung spart Arbeitsspeicher und verringert den Austausch. Viele Prozesse können eine DLL gleichzeitig verwenden und eine einzelne Kopie der schreibgeschützten Teile einer DLL im Arbeitsspeicher freigeben. Im Gegensatz dazu verfügt jede Anwendung, die mit einer statisch verknüpften Bibliothek erstellt wird, über eine komplette Kopie des Bibliothekscodes, den Windows in den Arbeitsspeicher laden muss.

- Die dynamische Verknüpfung spart Speicherplatz und Bandbreite. Viele Anwendungen können eine einzelne, auf der Festplatte gespeicherte Kopie der DLL gemeinsam nutzen. Im Gegensatz dazu ist für jede Anwendung, die mit einer statischen Link Bibliothek erstellt wurde, der Bibliotheks Code mit dem ausführbaren Image verknüpft, das mehr Speicherplatz beansprucht und mehr Bandbreite für die Übertragung benötigt.

- Wartung, Sicherheitskorrekturen und Upgrades können einfacher sein. Wenn Ihre Anwendungen allgemeine Funktionen in einer DLL verwenden, können Sie Fehlerbehebungen implementieren und Updates für die DLL bereitstellen, solange die Funktionsargumente und Rückgabewerte nicht geändert werden. Wenn DLLs aktualisiert werden, müssen die Anwendungen, die Sie verwenden, nicht erneut kompiliert oder neu verknüpft werden, und Sie verwenden die neue dll, sobald Sie bereitgestellt wird. Im Gegensatz dazu müssen Sie für Fehlerbehebungen, die Sie in statisch verknüpftem Objektcode vornehmen, jede Anwendung, die diese verwendet, neu verknüpfen und erneut bereitstellen.

- Sie können DLLs zum Bereitstellen von nach Marktunterstützung verwenden. Eine Treiber-DLL für ein Anzeigegerät kann z. B. so geändert werden, dass ein Gerät unterstützt wird, das zum Zeitpunkt der Auslieferung der Anwendung noch gar nicht verfügbar war.

- Mithilfe der expliziten Verknüpfung können Sie DLLs zur Laufzeit ermitteln und laden, z. b. Anwendungs Erweiterungen, die Ihrer APP neue Funktionen hinzufügen, ohne Sie erneut zu erstellen oder bereitzustellen.

- Durch dynamisches Verknüpfen wird die Unterstützung von Anwendungen vereinfacht, die in verschiedenen Programmiersprachen geschrieben wurden. Programme, die in verschiedenen Programmiersprachen erstellt wurden, können dieselbe DLL-Funktion aufrufen, solange sie die Aufrufkonvention der Funktion einhalten. Die Programme und die DLL-Funktion müssen in folgenden Punkten kompatibel sein: die von der Funktion erwartete Reihenfolge, in der Argumente auf den Stapel verschoben werden, ob die Funktion oder die Anwendung für das Bereinigen des Stapels verantwortlich ist und ob Argumente in Registern übergeben werden.

- Dynamic Linking bietet einen Mechanismus zum Erweitern der MFC-Bibliotheks Klassen. Sie können Klassen von bestehenden MFC-Klassen ableiten und diese in einer MFC-Erweiterungs-DLL speichern, die dann von MFC-Anwendungen genutzt werden kann.

- Durch dynamisches Verknüpfen wird die Erstellung internationaler Versionen der Anwendung vereinfacht. DLLs sind eine bequeme Möglichkeit zum Bereitstellen von Gebiets Schema spezifischen Ressourcen, die das Erstellen internationaler Versionen einer Anwendung erheblich vereinfachen. Anstatt viele lokalisierte Versionen der Anwendung zu versenden, können Sie die Zeichen folgen und Bilder für jede Sprache in einer separaten Ressourcen-DLL platzieren, und die Anwendung kann dann die entsprechenden Ressourcen für dieses Gebiets Schema zur Laufzeit laden.

Ein potenzieller Nachteil bei der Verwendung von DLLs besteht darin, dass die Anwendung nicht eigenständig ist. Dies hängt davon ab, ob ein separates dll-Modul vorhanden ist, das Sie im Rahmen ihrer Installation bereitstellen oder selbst überprüfen müssen.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Weitere Informationen zum Erstellen und Verwenden von DLLs

Die folgenden Themen enthalten ausführliche Informationen zum Erstellen von C/C++ DLLs in Visual Studio.

[Exemplarische Vorgehensweise: Erstellen und Verwenden einer Dynamic Link Library (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Beschreibt, wie Sie mit Visual Studio eine DLL erstellen und verwenden.

[Arten von DLLs](kinds-of-dlls.md)<br/>
Bietet Informationen zu den verschiedenen Arten von DLLs, die erstellt werden können.

[Häufig gestellte dll-Fragen](dll-frequently-asked-questions.md)<br/>
Bietet Antworten auf häufig gestellte Fragen zu DLLs.

[Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md)<br/>
Beschreibt das explizite und implizite Verknüpfen mit einer DLL.

[Initialisieren einer dll](run-time-library-behavior.md#initializing-a-dll)<br/>
Erläutert den dll-Initialisierungs Code, der beim Laden der DLL ausgeführt werden muss.

[DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](run-time-library-behavior.md)<br/>
Beschreibt, wie die DLL-Startsequenz durch die Laufzeitbibliothek ausgeführt wird.

[LoadLibrary und AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
Erläutert die Verwendung von **LoadLibrary** und `AfxLoadLibrary` die explizite Verknüpfung mit einer DLL zur Laufzeit.

[GetProcAddress](getprocaddress.md)<br/>
Erläutert die Verwendung von **GetProcAddress** zum Abrufen der Adresse einer exportierten Funktion in der dll.

[FreeLibrary und AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
Erläutert die Verwendung von " **FreeLibrary** " und wenn das DLL- `AfxFreeLibrary` Modul nicht mehr benötigt wird.

[Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)<br/>
Beschreibt den Suchpfad, der von Windows verwendet wird, um eine DLL im System zu finden.

[Module States of a Regular MFC DLL Dynamically Linked to MFC (Modulzustände einer regulären, dynamisch mit MFC verknüpften MFC-DLL)](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
Beschreibt die Modul Zustände einer regulären MFC-DLL, die dynamisch mit MFC verknüpft ist.

[MFC extension DLLs (MFC-Erweiterungs-DLLs)](extension-dlls-overview.md)<br/>
Erläutert DLLs, die typischerweise wiederverwendbare Klassen implementieren, welche von bestehenden Microsoft Foundation Class Library-Klassen abgeleitet wurden.

[Erstellen einer DLL als reine Ressource](creating-a-resource-only-dll.md)<br/>
Erörtert eine reine Ressourcen-DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder.

[Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs](localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
Bietet erweiterte Unterstützung für Satelliten-DLLs, eine Funktion, die den Entwickler bei der Erstellung von Anwendungen unterstützt, die für mehrere Sprachen lokalisiert sind.

[Importieren und Exportieren](importing-and-exporting.md)<br/>
Beschreibt das Importieren öffentlicher Symbole in eine Anwendung bzw. das Exportieren von Funktionen aus einer DLL.

[Active Technology und DLLs](active-technology-and-dlls.md)<br/>
Bietet die Möglichkeit, Objektserver innerhalb einer DLL zu implementieren.

[Automatisierung in einer DLL](automation-in-a-dll.md)<br/>
Beschreibt, welche Features die Automatisierungsoption im MFC-DLL-Assistenten bereitstellt.

[Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
Erörtert, nach welcher strukturierten Namenskonvention die in MFC enthaltenen DLLs und Bibliotheken benannt sind.

[Aufrufen von DLL-Funktionen aus Visual Basic Anwendungen](calling-dll-functions-from-visual-basic-applications.md)<br/>
Beschreibt den Aufruf von DLL-Funktionen aus Visual Basic-Anwendungen.

## <a name="related-sections"></a>Verwandte Abschnitte

[Verwenden von MFC als Teil einer dll](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
Beschreibt reguläre MFC-DLLs, mit denen Sie die MFC-Bibliothek als Bestandteil einer Windows Dynamic Link Library verwenden können.

[DLL-Version von MFC](../mfc/tn033-dll-version-of-mfc.md)<br/>
Beschreibt, wie Sie MFCxx. dll und MFCxxD. dll (wobei x die MFC-Versionsnummer ist) freigegebene Dynamic-Link-Bibliotheken mit MFC-Anwendungen und MFC-Erweiterungs-DLLs verwenden können.
