---
title: Windows-Desktop-Assistenten
ms.date: 03/29/2019
f1_keywords:
- vc.appwiz.win32.overview
- vc.appwiz.win32.appset
helpviewer_keywords:
- Windows Desktop Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
ms.openlocfilehash: 43a47366475b227ccfc5918b07760cc582326e82
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041470"
---
# <a name="windows-desktop-wizard"></a>Windows-Desktop-Assistenten

Die Windows-Desktop-Assistenten ersetzt, die Win32-Anwendungsassistenten in Visual Studio 2017 und höher. Der Assistent ermöglicht Ihnen die Erstellung einer der vier Arten von C++-Projekte (in der Überschrift in der folgenden Tabelle aufgeführt). Sie können zusätzliche Optionen festlegen, die für den jeweils geöffneten Projekttyp geeignet sind. 

   ![Windows-Desktop-Assistenten](media/windows-desktop-wizard.png)

Der folgenden Tabelle können Sie entnehmen, welche Optionen für die einzelnen Anwendungstypen verfügbar sind.

|Art der Unterstützung|Konsolenanwendung|Ausführbare (Windows-)Anwendung|Dynamic Link Library|Statische Bibliothek|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**Leeres Projekt**|Ja|Ja|Ja|Nein|
|**Symbole exportieren**|Nein|Nein|Ja|Nein|
|**Vorkompilierter Header**|Nein|Nein|Nein|Ja|
|**ATL-Unterstützung**|Ja|Nein|Nein|Nein|
|**MFC-Unterstützung**|Ja|Nein|Nein|Ja|

## <a name="overview"></a>Übersicht

Auf der Seite für diesen Assistenten werden die aktuellen Projekteinstellungen für die von Ihnen erstellte Win32-Anwendung beschrieben. Die folgenden Optionen sind standardmäßig aktiviert:

- Das Projekt ist eine Windows-Anwendung.

- Das Projekt ist nicht leer.

- Das Projekt enthält keine Exportsymbole.

- Das Projekt verwendet keine vorkompilierte Headerdatei (diese Option ist nur für statische Bibliotheksprojekte verfügbar).

- Das Projekt unterstützt weder MFC noch ATL.

## <a name="application-type"></a>Anwendungstyp

Erstellt den angegebenen Anwendungstyp.

|Option|Beschreibung|
|------------|-----------------|
|**Konsolenanwendung**|Erstellt eine Konsolenanwendung. Konsolenprogramme werden mit entwickelt [Konsolenfunktionen](https://msdn.microsoft.com/library/ms813137.aspx), die Zeichenmodus-Unterstützung in Konsolenfenstern zeichenmodusunterstützung bieten. Visual C++ [Laufzeitbibliotheken](../c-runtime-library/c-run-time-library-reference.md) auch Ausgabe und Eingabe in Konsolenfenstern mit standard-e/a-Funktionen, z. B. `printf_s()` und `scanf_s()`. Eine Konsolenanwendung hat keine grafische Benutzeroberfläche. Sie kompiliert Code in einer EXE-Datei und kann als eigenständige Anwendung von der Befehlszeile ausgeführt werden.<br /><br /> Sie können einer Konsolenanwendung MFC- und ATL-Unterstützung hinzufügen.|
|**Windows-Anwendung**|Erstellt ein Win32-Programm. Ein Win32-Programm ist eine ausführbare Anwendung (EXE), die in C oder C++ geschrieben ist und über Aufrufe der Win32-API eine grafische Benutzeroberfläche erstellt.<br /><br /> Sie können einer Windows-Anwendung keine MFC- oder ATL-Unterstützung hinzufügen.|
|**Dynamic Link Library**|Erstellt eine Win32-Dynamic Link Library (DLL). Eine Win32-DLL ist eine in C oder C++ geschriebene Binärdatei, die anstelle von MFC-Klassenaufrufen Win32-API-Aufrufe verwendet. Sie fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig eingesetzt werden kann.<br /><br /> Eine DLL-Anwendung erstellt, die mit diesem Assistenten können keine MFC- oder ATL-Unterstützung hinzugefügt, aber Sie können eine MFC-DLL erstellen auswählen **neu > Projekt > MFC-DLL**.|
|**Statische Bibliothek**|Erstellt eine statische Bibliothek. Eine statische Bibliothek ist eine Datei, die Objekte sowie zugehörige Funktionen und Daten enthält, die bei der Erstellung der ausführbaren Datei mit dem Programm verknüpft werden. In diesem Thema wird erläutert, wie Sie die Erstellung von Startdateien und [Projekteigenschaften](../build/reference/property-pages-visual-cpp.md) für eine statische Bibliothek. Eine statische Bibliothek bietet die folgenden Vorteile:<br /><br />– Eine statische Win32-Bibliothek ist hilfreich, wenn die Anwendung, die, der Sie gerade arbeiten, Aufrufe der Win32-API anstelle von MFC ausführt.<br />-Der Verknüpfungsvorgang ist identisch, ob die übrigen Teile Ihrer Windows-Anwendung in C oder C++ geschrieben wird.<br />– Sie können eine statische Bibliothek zu einem MFC-basierten Programm oder zu einem MFC-fremden Programm verknüpfen.|

## <a name="additional-options"></a>Zusätzliche Optionen

Definiert abhängig vom Anwendungstyp die Unterstützung sowie Optionen für die Anwendung.

|Option|Beschreibung|
|------------|-----------------|
|**Leeres Projekt**|Legt fest, dass die Projektdateien leer sind. Wenn Sie über eine Gruppe von Quellcodedateien (z. B. CPP-Dateien, Headerdateien, Symbole, Symbolleisten, Dialogfelder usw.) verfügen und in der Visual C++-Entwicklungsumgebung ein Projekt erstellen möchten, müssen Sie zunächst ein leeres Projekt anlegen und die Dateien dem Projekt dann hinzufügen.<br /><br /> Diese Option ist für statische Bibliotheksprojekte nicht verfügbar.|
|**Symbole exportieren**|Legt fest, dass vom DLL-Projekt Symbole exportiert werden.|
|**Vorkompilierter Header**|Legt fest, dass das statische Bibliotheksprojekt einen vorkompilierten Header verwendet.|
|**Security Development Lifecycle (SDL) überprüft.**|Weitere Informationen zu SDL finden Sie unter [Prozessleitfaden für die Microsoft Security Development Lifecycle (SDL)](../build/reference/sdl-enable-additional-security-checks.md)|

## <a name="add-common-headers-for"></a>Fügen Sie allgemeine Header für hinzu:

Fügen Sie Unterstützung für eine der in Visual C++ enthaltenen Bibliotheken hinzu.

|Option|Beschreibung|
|------------|-----------------|
|**ATL**|Wird in die Projektunterstützung für Klassen in ATL (Active Template Library) integriert. Nur für Win32-Konsolenanwendungen.<br /><br /> **Beachten Sie** diese Option gibt keine Unterstützung für das Hinzufügen von ATL-Objekten, die mit den ATL-code-Assistenten. Sie können ATL-Objekte nur zu ATL- oder MFC-Projekten mit ATL-Unterstützung hinzufügen.|
|**MFC**|Wird in die Projektunterstützung für die MFC (Microsoft Foundation Class)-Bibliothek integriert. Nur für Win32-Konsolenanwendungen und statische Bibliotheken.|

## <a name="remarks"></a>Hinweise

Nach Erstellung einer Windows-Desktopanwendung können Sie mit dem Assistenten für [generischen](../ide/generic-cpp-class-wizard.md) Code generische C++-Klassen hinzufügen. Sie können weitere Elemente, wie HTML-Dateien, Headerdateien, Ressourcen oder Textdateien, hinzufügen.

> [!NOTE]
> Es können keine ATL-Klassen hinzugefügt werden. MFC-Klassen können nur solchen Windows-Desktopanwendungstypen hinzugefügt werden, die MFC unterstützen (siehe vorangehende Tabelle).

Die vom Assistenten erstellten Projektdateien können im **Projektmappen-Explorer**angezeigt werden. Weitere Informationen zu den Dateien, die der Assistent erstellt für das Projekt, finden Sie in der Datei Projekt generierten `ReadMe.txt`. Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual C++-Projekte erstellte Dateitypen](../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[Visual C++-Projekttypen](../build/reference/visual-cpp-project-types.md)