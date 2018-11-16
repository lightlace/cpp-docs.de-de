---
title: Übersicht über Windows-Programmierung in C++
ms.date: 11/15/2018
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: b33236df6e4c7f679ff1dd9f9f8bc409c86e011a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693859"
---
# <a name="overview-of-windows-programming-in-c"></a>Übersicht über Windows-Programmierung in C++

Es gibt mehrere allgemeine Kategorien von Windows-Anwendungen, die Sie mit C++ erstellen können. Jede verfügt über eine eigene Programmiermodell und Satz von Windows-spezifischen Bibliotheken, aber der C++-Standardbibliothek sowie die C++-Bibliotheken von Drittanbietern können in einer von ihnen verwendet werden. 

## <a name="command-line-console-applications"></a>Über die Befehlszeile (Konsole)-Anwendungen

C++-konsolenanwendungen, über die Befehlszeile in einem Konsolenfenster ausführen und nur die Ausgabe von Text anzeigen. Weitere Informationen finden Sie unter [Konsolenanwendungen](console-applications-in-visual-cpp.md).
 
## <a name="native-desktop-client-applications"></a>Systemeigene desktop-Clientanwendungen

Der Begriff *systemeigene desktop-Client-Anwendung* bezieht sich auf eine C- oder C++ im Fenstermodus-Anwendung, die die ursprüngliche Win32-APIs von Windows verwendet wird, um das Betriebssystem zugreifen. Diese APIs sind sich größtenteils in c geschriebenen Wenn Sie diese Art von Anwendung zu erstellen, Sie haben die Wahl der Programmierung einer Nachrichtenschleife für C-Stil, die Betriebssystemereignisse verarbeitet direkt oder über *Microsoft Foundation Classes* (MFC), eine C++-Bibliothek, die dient als Wrapper für Win32 in einer Weise, etwas objektorientierten. Keiner dieser Ansätze gilt als "modernen" im Vergleich zu der universellen Windows-Plattform (siehe unten), aber beide sind weiterhin vollständig unterstützt und Millionen von Codezeilen, die derzeit in der Welt ausführen.

Um den ersten Schritten mit herkömmlichen Windows C++-Programmierung finden Sie unter [erste Schritte mit Win32- und C++](/windows/desktop/LearnWin32/learn-to-program-for-windows). Nachdem Sie ein Verständnis für Win32 erhalten, ist dies einfacher Informationen [MFC-Desktopanwendungen](/mfc/mfc-desktop-applications). Ein Beispiel für eine herkömmliche C++-Desktopanwendung, die komplexe Grafiken verwendet, finden Sie unter [Hilo: Entwickeln von C++-Anwendungen für Windows](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx).

### <a name="c-or-net"></a>C++ oder .NET? 

Den meisten desktop Anwendungsszenarien (das heißt, nicht mit UWP), sollten Sie C# und .NET. Dies ist, da die Programmierung mit .NET ist in der Regel weniger komplex und weniger fehleranfällig und verfügt über eine modernere, objektorientierte API als Win32 oder MFC. In den meisten Fällen ist die Leistung mehr als ausreichend. Der Windows Presentation Foundation (WPF) für komplexe Grafiken für .NET features, und Sie können Win32-als auch für die moderne Windows-Runtime-API (siehe unten UWP) nutzen. Es wird empfohlen, als in der Regel mithilfe C++ für desktop-Anwendungen, wenn erforderlich ist:

- präzise Steuerung der speicherauslastung
- der Energieverbrauch soweit wie möglich zu optimieren
- Nutzung der GPU für allgemeine Berechnungen
- der Zugriff auf DirectX
- einer hohen Auslastung der Standard-c++-Bibliotheken

## <a name="com-components"></a>COM-Komponenten

Viele Teile des Windows-Betriebssystems basieren auf das Component Object Model (COM), die einen binären Standard, mit dem Sie die Komponente definiert, die von Clientanwendungen, die in jeder beliebigen Computersprache genutzt werden können. In C++ können Sie die Active Template Library (ATL) um die Last der Erstellung Ihrer eigenen COM-Komponenten zu vereinfachen. Weitere Informationen finden Sie unter [Component Object Model (COM)](/windows/desktop/com/component-object-model--com--portal) und [ATL-COM-desktop-Komponenten](../atl/atl-com-desktop-components.md).

## <a name="windows-universal-apps"></a>Universelle Windows-Apps

Die universelle Windows-Plattform (UWP) ist die moderne Windows-API. UWP-apps auf allen Windows 10-Geräten ausgeführt, verwenden XAML für die Benutzeroberfläche und sind vollständig Touch-fähig. Weitere Informationen zu UWP finden Sie unter [was einer app für die universelle Windows-Plattform (UWP) ist?](/windows/uwp/get-started/whats-a-uwp) und [Anleitung für universelle Windows-Apps](/windows/uwp/get-started/universal-application-platform-guide).

Die ursprüngliche C++-Unterstützung für UWP Bestand aus der (1) C + c++ / CX, ein Dialekt von C++ mit Erweiterungen für die Syntax oder (2) der Windows-Runtime Library (WRL) basierend auf standard C++ und COM. Sowohl C + c++ / CX und WRL werden weiterhin unterstützt. Für neue Projekte empfohlen [C++ / WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt) der basiert vollständig auf C++-standard und bietet schnellere Leistung. 

Für Windows 10, Sie können Ihre vorhandenen C++-Desktopanwendung als Verpacken – für die Bereitstellung über den Microsoft Store ist. Weitere Informationen finden Sie unter [Packen von desktop-Anwendungen (Desktop-Brücke)](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="games"></a>Spiele

DirectX-Spiele können auf dem PC oder der Xbox ausgeführt werden. Weitere Informationen finden Sie unter [DirectX-Grafiken und-Spiele](/windows/desktop/directx).

## <a name="net-wrappers-for-c-libraries"></a>.NET-Wrapper für C++-Bibliotheken

Sie können C++ / CLI eine Interop-Ebene zu erstellen, können .NET Code systemeigene C++-Bibliotheken zu nutzen. Weitere Informationen finden Sie unter [.NET-Programmierung mit C++ / CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

## <a name="sql-server-database-clients"></a>SQL Server-Datenbank-clients

Verwenden Sie den Zugriff auf SQL Server-Datenbanken von nativem Code ODBC- oder OLE DB. Weitere Informationen finden Sie unter [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

## <a name="windows-device-drivers"></a>Windows-Gerätetreiber

Treiber sind Low-Level-Komponenten, die Daten von Hardwaregeräten für Anwendungen zugänglich zu machen und andere Komponenten des Betriebssystems. Weitere Informationen finden Sie unter [Windows-Treiberkit (WDK)](/windows-hardware/drivers/index).

## <a name="windows-services"></a>Windows-Dienste

Eine Windows *Service* ist ein Programm, das im Hintergrund mit wenig oder ganz ohne Benutzereingriff ausgeführt werden kann. Diese werden in UNIX genannt *Daemons*. Weitere Informationen finden Sie unter [Services](/windows/desktop/services/services).

## <a name="sdks-libraries-and-header-files"></a>SDKs, Bibliotheken und Headerdateien

Visual Studio enthält die C-Laufzeitbibliothek (CRT), die C++-Standardbibliothek und anderen Microsoft-spezifische Bibliotheken. Die Include-Ordner, die Headerdateien für diese Bibliotheken enthalten befinden sich entweder in der Visual Studio-Installationsverzeichnis im Ordner \VC\ oder im Falle der CRT, im Windows SDK-Installationsordner.

Sie können die [Vcpkg-Paket-Manager](../vcpkg.md) sinnvoll, Hunderte von Drittanbieter-Open Source-Bibliotheken für Windows installieren.

Die Microsoft-Bibliotheken enthalten:

- Microsoft Foundation Classes (MFC): Ein objektorientiertes Framework zum Erstellen herkömmlicher Windows-Programme (im Besonderen Unternehmensanwendungen), die über komplexe Benutzeroberflächen mit Schaltflächen, Listenfeldern, Strukturansichten und anderen Steuerelementen verfügen. Weitere Informationen finden Sie unter [MFC Desktop Applications](../mfc/mfc-desktop-applications.md).

- Active Template Library (ATL): Eine leistungsstarke Hilfebibliothek zum Erstellen von COM-Komponenten. Weitere Informationen finden Sie unter [ATL COM Desktop Components](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): Eine Bibliothek, die leistungsstarke allgemeine Computerarbeit auf der GPU ermöglicht. Weitere Informationen finden Sie unter [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Concurrency Runtime: Eine Bibliothek, mit der die Arbeit mit paralleler und asynchroner Programmierung für Viel- und Mehrkerngeräte vereinfacht wird. Weitere Informationen finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).

Viele Programmierszenarien bei Windows erfordern zudem das Windows SDK, in dem die Headerdateien enthalten sind, die den Zugriff auf Komponenten des Windows-Betriebssystems ermöglichen. Standardmäßig installiert Visual Studio das Windows SDK als Komponente von der C++-Desktop-Workload, die Entwicklung von universellen Windows-apps ermöglicht. Zum Entwickeln von UWP-apps benötigen Sie die Windows 10-Version des Windows SDK. Weitere Informationen finden Sie unter [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk). (Weitere Informationen zu Windows SDKs für frühere Versionen von Windows finden Sie unter den [Windows SDK-Archivs](https://developer.microsoft.com/windows/downloads/sdk-archive)).

**Programmieren von Dateien (x86) \Windows Kits** ist der Standardspeicherort für alle Versionen des Windows SDK, das Sie installiert haben.

Für andere Plattformen, wie Xbox und Azure, sind eigene SDKs verfügbar, die sie ggf. installieren müssen. Weitere Informationen finden Sie im DirectX-Developer Center sowie im Azure Developer Center.

## <a name="development-tools"></a>Entwicklungstools

Visual Studio bietet einen leistungsfähigen Debugger für nativen Code, Tools für statische Analyse, Grafikdebugtools, einen umfassenden Code-Editor, Unterstützung für Komponententests und viele weitere Tools und Hilfsprogramme. Weitere Informationen finden Sie unter [erste Schritte mit Visual Studio beim Entwickeln](/visualstudio/ide/get-started-developing-with-visual-studio), und [IDE und Entwicklungstools](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="in-this-section"></a>In diesem Abschnitt
|Titel|Beschreibung|
|-----------|-----------------|
|[Windows-Desktopanwendungen in C++](desktop-applications-visual-cpp.md)| Vorgehensweise: Erstellen Sie herkömmliche desktopanwendungen.|
|[Active Template Library (ATL)](../atl/TOC.md)|Verwenden Sie die ATL-Bibliothek, um COM-Komponenten in C++ zu erstellen.|
|[Microsoft Foundation Classes (MFC)](../mfc/TOC.md)|Verwenden von MFC um zu große oder kleine ein Windows-Anwendungen mit Dialogfelder und Steuerelemente zu erstellen.|
|[Freigegebene ATL- und MFC-Klassen](../atl-mfc-shared/TOC.md)|Verwenden Sie Klassen wie z. B. CString, die in ATL- und MFC-freigegeben werden.|
|[.NET-Entwicklung mit C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Erstellen von Wrappern für systemeigenen C++-Bibliotheken, die sie zur Kommunikation mit .NET-Anwendungen und-Komponenten zu aktivieren.|
|[Komponentenerweiterungen für .NET und UWP](component-extensions-for-runtime-platforms.md)|Referenz für Syntaxelemente, die von C++ freigegebene c++ / CX und C++ / CLI.|
|[Universelle Windows-Apps (C++)](universal-windows-apps-cpp.md)|Schreiben von UWP-Anwendungen, die mithilfe C++ / CX oder Windows Runtime Template Library (WRL).|
|[C++-Attribute für COM und .NET](attributes/cpp-attributes-com-net.md)|Nicht standardmäßige Attribute für nur-Windows-Programmierung mit der .NET- oder COM.|

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Übergeordnetes Thema für Inhalte von Visual C++-Entwickler.|
