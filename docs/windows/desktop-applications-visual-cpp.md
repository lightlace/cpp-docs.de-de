---
title: Desktopanwendungen (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 991e3e74ba280b615d951c12472de46833b7de72
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083345"
---
# <a name="desktop-applications-visual-c"></a>Desktopanwendungen (Visual C++)

Ein *Desktopanwendung* in C++ ist eine native Anwendung, die den vollständigen Satz von Windows-APIs und entweder ausgeführt wird, die in einem Fenster oder in der Systemkonsole zugreifen können. Desktopanwendung in C++ können unter Windows XP bis Windows 10 ausführen können (Obwohl Windows XP wird nicht mehr offiziell unterstützt, und es gibt viele Windows-APIs, die seit damals eingeführt wurden).

Eine Desktopanwendung unterscheidet sich von einer app (Universelle Windows Plattform), die auf PCs unter Windows 10 und auch auf XBox, Windows Phone, Surface Hub und anderen Geräten ausgeführt werden können. Weitere Informationen zu desktop-Visual-Studio. UWP-Anwendungen finden Sie unter [wählen Sie Ihre Technologie](https://msdn.microsoft.com/library/windows/desktop/dn614993).


### <a name="desktop-bridge"></a>Desktop-Brücke

In Windows 10 können Sie Ihrer vorhandenen Desktopanwendung oder COM-Objekt als UWP-app-Paket und UWP-Features wie z. B. Touch hinzufügen oder APIs aus dem Satz der modernen Windows-API aufrufen. Sie können auch eine UWP-app hinzufügen, um eine desktop-Lösung in Visual Studio, und sie in einem einzelnen Paket und Windows-APIs verwenden, um die Kommunikation zwischen ihnen.

In Visual Studio 2017 Version 15.4 und höher können Sie ein Windows-Anwendungsprojekt Paket zum Packen Ihrer vorhandenen Desktopanwendung Arbeit erheblich vereinfachen erstellen. Einige Einschränkungen in Bezug auf welche Registrierungsaufrufe oder APIs, die desktop-Anwendung verwendet, aber in vielen Fällen können Sie alternative Codepfade, um ähnliche Funktionalität zu erzielen, während der Ausführung in einem app-Paket erstellen. Weitere Informationen finden Sie unter [Desktop Bridge](/windows-uwp/porting/desktop-to-uwp-root).

### <a name="terminology"></a>Terminologie

- Ein *Win32* Anwendung ist eine Windows-Desktopanwendung in C++, die können Verwenden von systemeigenen [C-APIs für Windows und/oder COM-APIs](https://msdn.microsoft.com/library/windows/desktop/ff818516) CRT- und APIs der .NET-Standardbibliothek und 3. Bibliotheken von Drittanbietern. Eine Win32-Anwendung in einem Fenster verlangt vom Entwickler explizit mit Windows-Nachrichten innerhalb einer Prozedur-Funktion von Windows zu arbeiten. Trotz des Namens kann eine Win32-Anwendung als eine (x86) 32-Bit oder 64-Bit-(x64) binäre kompiliert werden. In der Visual Studio-IDE sind die Begriffe X86 und die Win32-Synonym.

- Die [Component Object Model (COM)](/windows/desktop/com/the-component-object-model) ist eine Spezifikation, die in verschiedenen Sprachen für die Kommunikation mit anderen geschriebene Programme ermöglicht. Viele Windows-Komponenten werden als COM-Objekte implementiert, und führen Sie die standard-COM-Regeln für die objekterstellung, Schnittstelle, die Zerstörung von Ermittlung und -Objekt.  COM-Objekte aus der C++-desktop-Anwendungen ist relativ unkompliziert, aber Ihre eigenen COM-Objekt zu schreiben ist komplexer. Die [Active Template Library (ATL)](../atl/atl-com-desktop-components.md) enthält Makros und Hilfsfunktionen, die COM-Entwicklung zu vereinfachen.

- Eine MFC-Anwendung ist eine Windows-Desktopanwendung, mit denen die [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md) die Benutzeroberfläche zu erstellen. Eine MFC-Anwendung kann auch COM-Komponenten "als auch" CRT "und" Standard-Bibliothek-APIs verwenden. MFC stellt einen dünnen objektorientierten C++-Wrapper über die Nachrichtenschleife für Fenster und die Windows-APIs bereit. MFC ist die Standardauswahl für Anwendungen – insbesondere Enterprise-Anwendungen –, die viele Steuerelemente der Benutzeroberfläche oder benutzerdefinierten Steuerelementen aufweisen. MFC stellt bequeme Hilfsklassen für die fensterverwaltung, Serialisierung, Textbearbeitung, Drucken und moderne Benutzeroberflächenelemente wie das Menüband bereit. Um effektiv mit MFC sollten Sie mit Win32 vertraut sein.

- C++ / CLI-Anwendung oder Komponente verwendet Erweiterungen für C++-Syntax (wie von der C++-Spezifikation zugelassen) zur Interaktion zwischen .NET und nativem C++-Code zu ermöglichen.  C++ / CLI-Anwendung kann Teile, die nativ ausgeführt und Teile, die auf .NET Framework mit Zugriff auf die Basisklassenbibliothek von .NET ausgeführt haben. C++ / CLI ist die bevorzugte Option, wenn Sie systemeigenen C++-Code verfügen, die Arbeit mit Code in c# oder Visual Basic geschrieben werden soll. Es dient in erster Linie für die Verwendung in .NET DLLs nicht im Code der Benutzeroberfläche. Weitere Informationen finden Sie unter [.NET-Programmierung mit C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

C Runtime (CRT) und Standard-Bibliothek von Klassen und Funktionen, COM-Objekte und der öffentlichen Windows-Funktionen, die insgesamt als Windows-API bezeichnet werden, kann desktop-Anwendung in C++ verwenden. Eine Einführung in Windows-Desktopanwendung in C++ finden Sie unter [Erfahren Sie, wie für Windows in C++ programmiert wird](http://go.microsoft.com/fwlink/p/?LinkId=262281).

## <a name="in-this-section"></a>In diesem Abschnitt

|Titel|Beschreibung|
|-----------|-----------------|
|[Konsolenanwendungen](../windows/console-applications-in-visual-cpp.md)|Enthält Informationen über Konsolen-Apps. Eine Win32- oder Win64-Konsolenanwendung hat kein eigenes Fenster und keine Meldungsschleife. Sie wird im Konsolenfenster ausgeführt. Eingaben und Ausgaben werden von der Befehlszeile behandelt.|
|[Windows-Desktop-Anwendungen](../windows/windows-desktop-applications-cpp.md)|Vorgehensweise: Erstellen von desktop-Anwendungen, die in Windows im Gegensatz zu der-Konsole ausgeführt.|
|[Ressourcen für das Erstellen eines Spiels mit DirectX (C++)](../windows/resources-for-creating-a-game-using-directx.md)|Enthält Links zu Inhalten für das Erstellen von Spielen in C++.|
|[Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Vorgehensweise: Erstellen Sie eine LIB-Binärdatei.|
|[Gewusst wie: Verwenden des Windows 10-SDKs in einer Windows-Desktopanwendung](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Enthält Schritte zum Einrichten Ihres Projekts für das Erstellen mit dem Windows 10-SDK.|

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Windows-Entwicklung](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Enthält Informationen zur Windows-API und COM. (Einige Windows-APIs und Drittanbieter-DLLs werden als COM-Objekte implementiert).|
|[Hilo: Entwickeln von C++-Anwendungen für Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Beschreibt, wie Sie eine vielseitige Windows-Desktopanwendung erstellen, die Windows-Animationen und Direct2D verwendet, um eine karussellbasierte Benutzeroberfläche zu erstellen.  In diesem Tutorial wurde nicht aktualisiert, seit Windows 7, aber es bietet weiterhin eine ausführliche Einführung in Win32-Programmierung.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|

## <a name="see-also"></a>Siehe auch

[Visual C++](../visual-cpp-in-visual-studio.md)