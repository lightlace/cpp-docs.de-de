---
title: Desktop Anwendungen (Visual C++)
ms.date: 07/28/2019
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
ms.openlocfilehash: a1e302a29e079545f6d12ad544eab4f43e2bd445
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606514"
---
# <a name="desktop-applications-visual-c"></a>Desktop Anwendungen (Visual C++)

Eine *Desktop Anwendung* in C++ ist eine native Anwendung, die auf den vollständigen Satz von Windows-APIs zugreifen kann und entweder in einem Fenster oder in der Systemkonsole ausgeführt wird. Desktop Anwendungen in C++ können unter Windows XP bis Windows 10 ausgeführt werden (obwohl Windows XP nicht mehr offiziell unterstützt wird und seitdem viele Windows-APIs eingeführt wurden). 

Eine Desktop Anwendung unterscheidet sich von einer universelle Windows-Plattform-app (UWP), die auf PCs unter Windows 10 und auch auf Xbox, Windows Phone, Surface Hub und anderen Geräten ausgeführt werden kann. Weitere Informationen zu Desktop im Vergleich zu UWP-Anwendungen finden [Sie unter Wählen Sie Ihre Technologie](/windows/desktop/choose-your-technology).

### <a name="desktop-bridge"></a>Desktop Bridge

In Windows 10 können Sie die vorhandene Desktop Anwendung oder das COM-Objekt als UWP-App Verpacken und UWP-Features wie Finger Eingaben hinzufügen oder APIs aus dem modernen Windows-API-Satz aufzurufen. Sie können eine UWP-APP auch einer Desktop Projekt Mappe in Visual Studio hinzufügen und Sie in einem einzelnen Paket Verpacken und Windows-APIs für die Kommunikation zwischen Ihnen verwenden.

In Visual Studio 2017, Version 15,4 und höher, können Sie ein Windows-Anwendungspaket Projekt erstellen, um die Arbeit beim Verpacken Ihrer vorhandenen Desktop Anwendung erheblich zu vereinfachen. Es gelten einige Einschränkungen hinsichtlich der Registrierungs Aufrufe oder APIs, die von der Desktop Anwendung verwendet werden. in vielen Fällen können Sie jedoch alternative Codepfade erstellen, um eine ähnliche Funktionalität zu erzielen, während Sie in einem App-Paket ausgeführt werden. Weitere Informationen finden Sie unter [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

### <a name="terminology"></a>Terminologie

- Eine *Win32* -Anwendung ist eine Windows-Desktop C++ Anwendung in, die native [Windows C-APIs und/oder COM-APIs](/windows/desktop/apiindex/windows-api-list) CRT und Standard Bibliotheks-APIs sowie Bibliotheken von Drittanbietern verwenden kann. Eine Win32-Anwendung, die in einem-Fenster ausgeführt wird, erfordert, dass der Entwickler explizit mit Windows-Meldungen innerhalb einer Windows-Prozedur Funktion arbeitet. Trotz des Namens kann eine Win32-Anwendung als 32-Bit-(x86) oder 64-Bit-Binärdatei (x64) kompiliert werden. In der Visual Studio-IDE sind die Begriffe x86 und Win32 Synonym.

- Der [Component Object Model (com)](/windows/desktop/com/the-component-object-model) ist eine Spezifikation, mit der Programme, die in verschiedenen Sprachen geschrieben wurden, miteinander kommunizieren können. Viele Windows-Komponenten werden als COM-Objekte implementiert und befolgen die com-Standardregeln für Objekt Erstellung, Schnittstellen Ermittlung und Objekt Zerstörung.  Die Verwendung von com C++ -Objekten aus Desktop Anwendungen ist relativ unkompliziert, aber das Schreiben eines eigenen com-Objekts ist fortschrittlicher. Der [Active Template Library (ATL)](../atl/atl-com-desktop-components.md) stellt Makros und Hilfsfunktionen bereit, die die com-Entwicklung vereinfachen.

- Bei einer MFC-Anwendung handelt es sich um eine Windows-Desktop Anwendung, die die [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md) zum Erstellen der Benutzeroberfläche verwendet. In einer MFC-Anwendung können auch com-Komponenten sowie CRT-und Standard Bibliotheks-APIs verwendet werden. MFC bietet einen schmalen C++ objektorientierten Wrapper über die Fenster Nachrichten Schleife und Windows-APIs. MFC ist die Standardoption für Anwendungen – insbesondere Anwendungen vom Typ Unternehmensanwendungen –, die über viele Benutzeroberflächen-Steuerelemente oder benutzerdefinierte Benutzer Steuerelemente verfügen. MFC bietet bequeme Hilfsklassen für Fensterverwaltung, Serialisierung, Textbearbeitung, Druck und moderne Benutzeroberflächen Elemente, wie z. b. das Menüband. Damit Sie mit MFC wirksam werden, sollten Sie mit Win32 vertraut sein.

- Eine C++/CLI-Anwendung oder-Komponente verwendet C++ Erweiterungen für die Syntax (gemäß C++ dem Standard), um die Interaktion zwischen .net und nativem C + +-Code zu ermöglichen.  Eine C++/CLI-Anwendung kann Teile aufweisen, die System intern ausgeführt werden, sowie Teile, die auf dem .NET Framework mit Zugriff auf die .net-Basisklassen Bibliothek ausgeführt werden. C++/CLI ist die bevorzugte Option, wenn Sie über C++ systemeigenen Code verfügen, der mit in C# oder Visual Basic geschriebenen Code funktionieren muss. Sie ist für die Verwendung in .NET-DLLs und nicht in Benutzeroberflächen Code vorgesehen. Weitere Informationen Sie unter [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

Jede Desktop Anwendung in C++ kann Klassen und Funktionen der C-Laufzeit (CRT) und Standard Bibliothek, com-Objekte und die öffentlichen Windows-Funktionen verwenden, die kollektiv als Windows-API bezeichnet werden. Eine Einführung in Windows-Desktop Anwendungen in C++finden [Sie unter Get Started with Win32 C++and ](/windows/desktop/LearnWin32/learn-to-program-for-windows).

## <a name="in-this-section"></a>In diesem Abschnitt

|Titel|Beschreibung|
|-----------|-----------------|
|[Windows-Konsolenanwendungen in C++](console-applications-in-visual-cpp.md)|Enthält Informationen über Konsolen-Apps. Eine Win32- oder Win64-Konsolenanwendung hat kein eigenes Fenster und keine Meldungsschleife. Sie wird im Konsolenfenster ausgeführt. Eingaben und Ausgaben werden von der Befehlszeile behandelt.|
|[Exemplarische Vorgehensweise: Erstellen von Windows-Desktopanwendungen (C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|Erstellen Sie eine einfache Windows-Desktop Anwendung.|
|[Erstellen einer leeren Windows-Desktopanwendung](creating-an-empty-windows-desktop-application.md)|Erstellen eines Windows-Desktop Projekts, das keine Standard Dateien aufweist.|
|[Hinzufügen von Dateien zu leeren Win32-Anwendungen](adding-files-to-an-empty-win32-applications.md)|Vorgehensweise beim Hinzufügen von Dateien zu einem leeren Projekt.|
|[Arbeiten mit Ressourcendateien](working-with-resource-files.md)|Hinzufügen von Bildern, Symbolen, Zeichen folgen Tabellen und anderen Ressourcen zu einer Desktop Anwendung.|
|[Ressourcen zum Erstellen eines Spiels mit DirectX (C++)](resources-for-creating-a-game-using-directx.md)|Links zu Inhalten zum Erstellen von spielen C++in.|
|[Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek](walkthrough-creating-and-using-a-static-library-cpp.md)|So erstellen Sie eine lib-Binärdatei.|
|[Vorgehensweise: Verwenden des Windows 10 SDK in einer Windows-Desktopanwendung](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Enthält Schritte zum Einrichten Ihres Projekts für das Erstellen mit dem Windows 10-SDK.|

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Windows-Entwicklung](/windows/desktop/index)|Enthält Informationen zur Windows-API und COM. (Einige Windows-APIs und Drittanbieter-DLLs werden als COM-Objekte implementiert).|
|[Hilo Entwickeln C++ von Anwendungen für Windows 7](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)|Beschreibt, wie Sie eine vielseitige Windows-Desktopanwendung erstellen, die Windows-Animationen und Direct2D verwendet, um eine karussellbasierte Benutzeroberfläche zu erstellen.  Dieses Tutorial wurde seit Windows 7 nicht aktualisiert, bietet aber eine gründliche Einführung in die Win32-Programmierung.|
|[Übersicht über Windows-Programmierung in C++](overview-of-windows-programming-in-cpp.md)|Beschreibt die wichtigsten Features der Windows-Desktop C++Programmierung in.|

## <a name="see-also"></a>Siehe auch

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)