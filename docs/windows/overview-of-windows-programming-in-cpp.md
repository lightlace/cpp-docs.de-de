---
title: "Übersicht über die Windows-Programmierung in C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bf25d8f3653d2146774efd333daff74a5fb33e2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="overview-of-windows-programming-in-c"></a>Übersicht über Windows-Programmierung in C++

Sie können Visual C++ zum Schreiben einer Vielzahl von Programmen verwenden, die auf einem Windows-PC (x86, x64 oder ARM), auf einen Windows-Server, in der Cloud oder auf der Xbox ausgeführt werden. Gut geschriebene C++-Programme sind schnell, effizient, wirtschaftlich im Energieverbrauch und in der Lage, die Vorteile von Mehr- und Vielkerngeräten, allgemeine Berechnungen auf der Grafikverarbeitungseinheit (GPGPU) und andere neue Entwicklungen im Hardwarebereich in vollem Umfang zu nutzen.

Es gibt mehrere allgemeine Kategorien von Windows-Apps, die mit Visual C++ entwickelt werden können. Diese Kategorien verwenden unterschiedliche verschiedene Programmiermodelle bzw. App-Modelle, was bedeutet, dass sie verschiedene Bibliotheken und APIs nutzen, um Zugriff auf die Plattform und die Benutzeroberfläche bereitzustellen///.

- [Universelle Windows-Apps](#BK_WindowsUniversal). Die dritte Kategorie von Windows-Apps wurde mit Windows 8 eingeführt und wird in Windows 10 weiterhin unterstützt. Diese Apps werden häufig einfach nur als „Windows-Apps“ bezeichnet und umfassen Desktop- und mobile Apps für eine Vielzahl von Geräten. Sie können diese Apps in C++ / CX schreiben, einer Abwandlung von C++, die Unterstützung für die Windows-Runtime-Entwicklung bietet, oder in der C++-Standardprogrammiersprache mit COM unter Verwendung der Windows-Runtime-Bibliothek (WRL). Diese Apps wurden ursprünglich für die Ausführung im Vollbildmodus entworfen, in Windows 10 haben die Benutzer jedoch die Möglichkeit, sie in einem Desktopfenster auszuführen. Diese Apps sind für Toucheingabe ausgelegt, Benutzer können sie jedoch auch problemlos mit der Maus bedienen, wenn sie dies bevorzugen oder kein Touchscreen verfügbar ist. Diese Apps werden über den Windows Store vertrieben, weshalb sie mittlerweile als „Windows Store-Apps“ bezeichnet werden.

- [Desktop-, Server-, Cloudanwendungen und Spiele](#BK_Native) Diese Kategorie umfasst Windows Desktop-Anwendungen, die manchmal auch als Win32-Anwendungen bezeichnet werden, da diese Anwendungen die Win32-API verwendeten. Vor Windows 8 gehörten alle Windows-Anwendungen zu dieser Kategorie. Anwendungen in dieser Kategorie können MFC als Benutzeroberfläche und ATL für die Interaktion mit Windows-Komponenten verwenden, bei denen es sich in der Regel um COM-Objekte handelt.

   Auch Anwendungen, Komponenten oder Bibliotheken, die mit der C++-Standardprogrammiersprache geschriebene wurden, gehören zu dieser Kategorie.

   Diese Kategorie umfasst auch die Verwendung von C++ für Kernkomponenten und rechnerischen Code im Kontext der Server- und Cloud-Programmierung. Manchmal wird der rechenintensive Code den Kern eines Servers oder einer Cloud-Anwendung in C++ zum Maximieren der Leistung geschrieben. Sie können Code in eine DLL kompilieren und in C# oder Visual Basic verwenden.

- **.NET Framework-Anwendungen**. Die meisten .NET Framework-Anwendungen sind in C# oder Visual Basic geschrieben, Sie können jedoch auch C++ / CLI (die Compileroption in Visual C++) verwenden. Wir empfehlen die Verwendung von C++/CLI für eine minimale Interop-Ebene in einer umfangreicheren Anwendung, die verwalteten und systemeigenen Code enthält.

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Mit Windows-10 können Apps auf allen Windows-10-Geräten ausgeführt werden, z. B. Tablet-PCs und Mobiltelefone sowie auf dem Desktop. Auf dem Desktop können Sie als Desktop-Fenster ausgeführt werden, statt sie immer im Vollbildmodus ausführen zu müssen. Diese Anwendungen können auch auf der Xbox und auf zukünftigen Geräten ausgeführt werden.  Das Programmiermodell für die beiden App-Typen unterscheideb sich von Win32-Desktopanwendungen. Diese Windows-Anwendungen werden unter Windows-Runtime ausgeführt, sie stellt Benutzeroberflächenelemente, grundlegende Dienste für diese Apps und eine Schnittstelle zu verschiedenen Hardwaregeräten bereit, die unterstützt werden. Diese Apps werden in systemeigenem Code kompiliert, verfügen über eine XAML-Benutzeroberfläche oder verwenden DirectX. Sie können auch Windows-Runtime-Komponenten schreiben, in systemeigenen Code, der andere Windows-apps genutzt werden können – dazu gehören in c#, Visual Basic oder JavaScript geschriebene apps. Weitere Informationen finden Sie unter [erstellen Sie eine universelle Windows-Plattform-app in C++](http://go.microsoft.com/fwlink/p/?linkid=534976), [Erstellen Ihrer ersten uwp-Spiels mit DirectX](http://go.microsoft.com/fwlink/p/?LinkId=244656), und [Erstellen von Windows-Runtime-Komponenten in C++](http://go.microsoft.com/fwlink/p/?LinkId=244658).

> [!TIP]
> Für Windows 10 können Sie den Desktop-App-Konverter verwenden, um Ihre vorhandenen desktop-Anwendung für die Bereitstellung über den Windows Store verpacken. Weitere Informationen finden Sie im Blogbeitrag [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und unter [Überführen Ihrer Desktop-App auf die universelle Windows-Plattform (UWP) mit Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Beispiele für die universelle Windows-Plattform (Universal Windows Platform; UWP) finden Sie unter [Beispiele für die universelle Windows-Plattform auf GitHub](https://github.com/Microsoft/Windows-universal-samples)

Wenn Sie einen vorhandenen Windows 8.1-Projekt und möchten es auf Windows 10 Portieren haben, finden Sie unter [auf die universelle Windows-Plattform portieren](../porting/porting-to-the-universal-windows-platform-cpp.md). Wenn Sie über vorhandene klassische Win32-desktop-Bibliotheken und codieren, Sie möchten in einer uwp-app integrieren, finden Sie unter [Vorgehensweise: verwenden vorhandenen C++-Code in einer universellen Windows-Plattform-App](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

Sie können auch die universelle Windows-apps, Spiele und Komponenten schreiben, ohne die C + c++ / CX; Stattdessen können Sie die Windows Runtime C++ Template Library (Windows Runtime C++ Template Library) verwenden. Weitere Informationen finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

Mit [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]können Sie universelle Windows-Apps entwickeln, die unter Windows 10 Desktop und auf mobilen Geräten ausgeführt werden können. Sie können auch Windows 8.1- und Windows Phone 8.1-Apps in [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]entwickeln, dazu müssen Sie jedoch zunächst Visual Studio 2013 auf demselben Computer installieren und Ihr Projekt anschließend so konfigurieren,dass es das **Visual Studio 2013 (v120)** -Toolset verwendet. Um diese Einstellung in Ihrem Projekt zu konfigurieren, öffnen Sie die Eigenschaften des Projekts und legen Sie im Abschnitt **Allgemeine** für das **Plattformtoolset** **Visual Studio 2013 (v120)**fest.

Wenn Sie die Phone 8.0-Tools im Visual Studio-Setup installieren, können Sie auch Entwicklungen für Windows Phone 8.0 erstellen.

Ein neues in Windows 10 eingeführtes Konzept mit der Bezeichnung API-Verträge ersetzt die alte Vorgehensweise für die Entwicklung für bestimmte Windows-Versionen. Stattdessen können Sie auswählen, welche API-Verträge Ihre App benötigt, und sie kann dann auf jedem Windows-Gerät ausgeführt werden, das diese Verträge unterstützt. Ein API-Vertrag ist eine Reihe von stabilen APIs, die Zugriff auf Ressourcen von Plattformen oder Geräten bereitstellen. API-Verträge können im Projektsystem als Verweise enthalten sein. Wenn Sie in einem Visual Studio-Projekt einen Verweis auf einen bestimmtes Erweiterungs-SDK hinzufügen, fügt Visual Studio die entsprechenden API-Verträge hinzu.

Weitere Informationen zu diesen Konzepten, finden Sie unter [Anleitung für universelle Windows-Apps](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Desktop-, Server-, Cloud-Apps und Spiele

In der Cloud können Sie native Azure-Codeassamblys in C++ schreiben und sie über in C# erstellte Webrollen aufrufen. Weitere Informationen finden Sie unter [Azure SDK](http://go.microsoft.com/fwlink/p/?LinkId=256416).

Informationen über die Grundlagen zum Schreiben von Windows-Clientanwendungen für den Desktop finden Sie unter [Entwickeln von Windows-Anwendungen in C++](http://msdn.microsoft.com/vstudio//hh304489) und [Einführung in die Windows-Programmierung in C++](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx).

Unter Windows 10 können Sie Visual C++ zum Erstellen vieler Arten von Programmen verwenden:

- Befehlszeilen-Apps und -programme. Weitere Informationen finden Sie unter [Konsolenanwendungen](../windows/console-applications-in-visual-cpp.md).

- DirectX-Spiele, die auf dem PC oder der Xbox ausgeführt werden. Weitere Informationen finden Sie unter [DirectX Developer Center](http://go.microsoft.com/fwlink/p/?LinkId=256418).

- Consumer-Anwendungen mit ausgearbeiteten grafischen Benutzeroberflächen. Weitere Informationen finden Sie unter [Hilo: Entwickeln von C++-Anwendungen für Windows](http://go.microsoft.com/fwlink/p/?LinkId=256417)

- Enterprise und Branchen-Apps, die auf .NET Framework ausgeführt werden oder als Brücke zwischen .NET Framework-Apps und Apps bzw. Komponenten dienen, die in nativem Code geschrieben werden. Weitere Informationen finden Sie unter [.NET Framework-Programmierung mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- SQL-Datenbankclients, die in nativem Code ausführen. Weitere Informationen finden Sie unter [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419).

- Add-Ins für Microsoft Office-Anwendungen. Weitere Informationen finden Sie unter [Erstellen eines C++-Add-Ins für Outlook 2010](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Gerätetreiber Weitere Informationen finden Sie unter [Windows-Treiberkit](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Windows-Dienste Weitere Informationen finden Sie unter [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

Sie können Visual C++ verwenden, um nahezu jede Art von benutzerdefinierter leistungsstarker Funktion in Win32-DLLs oder COM-DLLs zu verpacken, die von C++-Apps oder von Apps genutzt werden können, die in anderen Sprachen, wie z. B. C# oder Visual Basic geschrieben werden. Weitere Informationen zu Win32-DLLs finden Sie unter [DLLs in Visual C++](../build/dlls-in-visual-cpp.md). Weitere Informationen zur COM-Entwicklung finden Sie unter [Component Object Model (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="sdks-and-header-files"></a>SDKs und Headerdateien

Visual C++ enthält die C-Laufzeitbibliothek (CRT), der C++-Standardbibliothek und andere Microsoft-spezifische Bibliotheken. Die Include-Ordner, die Headerdateien für diese Bibliotheken enthalten sind, befinden sich im Visual Studio-Installationsverzeichnis im Ordner \VC\ oder im Fall der CRT Windows SDK-Installationsordner, beispielsweise Windows Kits\10 im Programm-Dateien der Ordner für das Windows 10-SDK.  Die Microsoft-Bibliotheken enthalten:

- Microsoft Foundation Classes (MFC): Ein objektorientiertes Framework zum Erstellen herkömmlicher Windows-Programme (im Besonderen Unternehmensanwendungen), die über komplexe Benutzeroberflächen mit Schaltflächen, Listenfeldern, Strukturansichten und anderen Steuerelementen verfügen. Weitere Informationen finden Sie unter [MFC Desktop Applications](../mfc/mfc-desktop-applications.md).

- Active Template Library (ATL): Eine leistungsstarke Hilfebibliothek zum Erstellen von COM-Komponenten. Weitere Informationen finden Sie unter [ATL COM Desktop Components](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): Eine Bibliothek, die leistungsstarke allgemeine Computerarbeit auf der GPU ermöglicht. Weitere Informationen finden Sie unter [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Concurrency Runtime: Eine Bibliothek, mit der die Arbeit mit paralleler und asynchroner Programmierung für Viel- und Mehrkerngeräte vereinfacht wird. Weitere Informationen finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).

Viele Programmierszenarien bei Windows erfordern zudem das Windows SDK, in dem die Headerdateien enthalten sind, die den Zugriff auf Komponenten des Windows-Betriebssystems ermöglichen. Visual Studio installiert standardmäßig das Windows-SDK, die Entwicklung von universellen Windows-apps ermöglicht. Um allgemeine Windows-Apps für Windows 10 entwickeln zu können, benötigen Sie die Windows-10-Version des Windows SDK. Informationen über das Windows 10-SDK finden Sie unter [Windows 10-SDK](https://dev.windows.com/downloads/windows-10-sdk). (Weitere Informationen zu Windows SDKs für frühere Versionen von Windows finden Sie unter der [Windows SDK-Archivs](https://developer.microsoft.com/windows/downloads/sdk-archive)).

Für andere Plattformen, wie Xbox und Azure, sind eigene SDKs verfügbar, die sie ggf. installieren müssen. Weitere Informationen finden Sie im DirectX-Developer Center sowie im Azure Developer Center.

## <a name="development-tools"></a>Entwicklungstools

Visual Studio bietet einen leistungsfähigen Debugger für nativen Code, Tools für statische Analyse, Grafikdebugtools, einen umfassenden Code-Editor, Unterstützung für Komponententests und viele weitere Tools und Hilfsprogramme. Weitere Informationen finden Sie unter [Einstieg in die Entwicklung mit Visual Studio](/visualstudio/ide/get-started-developing-with-visual-studio), und [IDE und Entwicklungstools](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Übergeordnetes Thema für Visual C++-Entwickler-Inhalte.|