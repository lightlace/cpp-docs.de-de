---
title: Übersicht über die Windows-Programmierung in C++ | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2096c36ec24c1ca7e20c789b8a1eb8c24589ccc1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="overview-of-windows-programming-in-c"></a>Übersicht über Windows-Programmierung in C++

Sie können Visual C++ verwenden, auf um viele Arten von Programmen zu schreiben, die auf einem Windows-PC (x 86, X64 oder ARM) ausgeführt, auf einem WindowsServer, in der Cloud oder auf der Xbox. Gut geschriebene C++-Programmen über diese Qualitäten verfügen:
- effiziente in speicheranforderungen
- wirtschaftlich im Energieverbrauch 
- vollständige Nutzen von mehr- und m-Core-Geräten
- Allgemeine Berechnungen auf Grafikprozessor (GPGPU) ausführen können   
- andere jüngsten Entwicklungen im Hardwarebereich nutzen können.

Es gibt mehrere allgemeine Kategorien von Windows-Apps, die mit Visual C++ entwickelt werden können. Diese Kategorien eingeteilt werden verschiedene Programmiermodelle bzw. app-Modelle, die im Laufe der Jahre eingeführt wurden. Jedes Modell verwendet verschiedene Bibliotheken und APIs bieten Zugriff auf die Plattform und Erstellen von Benutzeroberflächen wie Fenster und Dialogfelder. Die C++-Standardbibliothek sowie Bibliotheken von Drittanbietern können in einer dieser Kategorien, mit wenigen Einschränkungen für universelle Windows-Plattform verwendet werden.

- [Universelle Windows-Apps](#BK_WindowsUniversal). Die dritte Kategorie von Windows-Apps wurde mit Windows 8 eingeführt und wird in Windows 10 weiterhin unterstützt. Diese Apps werden häufig einfach nur als „Windows-Apps“ bezeichnet und umfassen Desktop- und mobile Apps für eine Vielzahl von Geräten. Sie können diese Apps in C++ / CX schreiben, einer Abwandlung von C++, die Unterstützung für die Windows-Runtime-Entwicklung bietet, oder in der C++-Standardprogrammiersprache mit COM unter Verwendung der Windows-Runtime-Bibliothek (WRL). Diese Apps wurden ursprünglich für die Ausführung im Vollbildmodus entworfen, in Windows 10 haben die Benutzer jedoch die Möglichkeit, sie in einem Desktopfenster auszuführen. Diese Apps sind für Toucheingabe ausgelegt, Benutzer können sie jedoch auch problemlos mit der Maus bedienen, wenn sie dies bevorzugen oder kein Touchscreen verfügbar ist. Diese apps werden aus dem Microsoft-Store ein Fakt verteilt die Ihnen die aufgerufenen "Store" apps geführt hat.

Uwp-apps werden auf allen Windows 10-Geräten wie Tablet-PCs und Mobiltelefone sowie auf dem Desktop ausgeführt. Auf dem Desktop können Sie als Desktop-Fenster ausgeführt werden, statt sie immer im Vollbildmodus ausführen zu müssen. Diese Anwendungen können auch auf der Xbox und auf zukünftigen Geräten ausgeführt werden.  Führen Sie uwp-apps auf Windows-Runtime, die stellt Benutzeroberflächenelemente, Dienste und eine Schnittstelle zu verschiedenen Hardwaregeräten, die unter Windows unterstützt werden.  

Sie können die uwp-apps in C++ schreiben c++ / CX, einer Abwandlung von C++, können Sie die [C + c++ / WinRT-Bibliothek](https://moderncpp.com/)für einige Szenarien. Uwp-apps in systemeigenen Code kompiliert und verfügen über eine XAML-Benutzeroberfläche oder verwenden DirectX. Windows-Runtime-Komponenten, die in systemeigenem Code geschrieben werden, dass die uwp-apps, die in anderen Sprachen geschriebene genutzt werden können. Weitere Informationen finden Sie unter [erstellen Sie eine universelle Windows-Plattform-app in C++](http://go.microsoft.com/fwlink/?LinkID=534976), [Erstellen Ihrer ersten uwp-Spiels mit DirectX](http://go.microsoft.com/fwlink/p/?LinkId=244656), und [Erstellen von Windows-Runtime-Komponenten in C++](http://go.microsoft.com/fwlink/p/?LinkId=244658).

   Diese Kategorie umfasst auch die Verwendung von C++ für Kernkomponenten und rechnerischen Code im Kontext der Server- und Cloud-Programmierung. Manchmal wird der rechenintensive Code den Kern eines Servers oder einer Cloud-Anwendung in C++ zum Maximieren der Leistung geschrieben. Sie können Code in eine DLL kompilieren und in C# oder Visual Basic verwenden.

- **.NET Framework-Anwendungen**. Die meisten .NET Framework-Anwendungen sind in C# oder Visual Basic geschrieben, Sie können jedoch auch C++ / CLI (die Compileroption in Visual C++) verwenden. Wir empfehlen die Verwendung von C++/CLI für eine minimale Interop-Ebene in einer umfangreicheren Anwendung, die verwalteten und systemeigenen Code enthält.

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Mit Windows-10 können Apps auf allen Windows-10-Geräten ausgeführt werden, z. B. Tablet-PCs und Mobiltelefone sowie auf dem Desktop. Auf dem Desktop können Sie als Desktop-Fenster ausgeführt werden, statt sie immer im Vollbildmodus ausführen zu müssen. Diese Anwendungen können auch auf der Xbox und auf zukünftigen Geräten ausgeführt werden.  Das Programmiermodell für die beiden App-Typen unterscheideb sich von Win32-Desktopanwendungen. Diese Windows-Anwendungen werden unter Windows-Runtime ausgeführt, sie stellt Benutzeroberflächenelemente, grundlegende Dienste für diese Apps und eine Schnittstelle zu verschiedenen Hardwaregeräten bereit, die unterstützt werden. Diese Apps werden in systemeigenem Code kompiliert, verfügen über eine XAML-Benutzeroberfläche oder verwenden DirectX. Sie können auch Windows-Runtime-Komponenten schreiben, in systemeigenen Code, der andere Windows-apps genutzt werden können – dazu gehören in c#, Visual Basic oder JavaScript geschriebene apps. Weitere Informationen finden Sie unter [erstellen Sie eine UWP-app "Hello World" in C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp), [erstellen ein einfachen uwp-Spiels mit DirectX](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game), und [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

> [!TIP]
> Für Windows 10 können Sie Desktop-App-Konverter verwenden, um Ihre vorhandenen desktop-Anwendung für die Bereitstellung über den Microsoft Store verpacken. Weitere Informationen finden Sie im Blogbeitrag [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und unter [Überführen Ihrer Desktop-App auf die universelle Windows-Plattform (UWP) mit Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Beispiele für die universelle Windows-Plattform (Universal Windows Platform; UWP) finden Sie unter [Beispiele für die universelle Windows-Plattform auf GitHub](https://github.com/Microsoft/Windows-universal-samples)

Wenn Sie einen vorhandenen Windows 8.1-Projekt und möchten es auf Windows 10 Portieren haben, finden Sie unter [auf die universelle Windows-Plattform portieren](../porting/porting-to-the-universal-windows-platform-cpp.md). Wenn Sie über vorhandene klassische Win32-desktop-Bibliotheken und codieren, Sie möchten in einer uwp-app integrieren, finden Sie unter [Vorgehensweise: verwenden vorhandenen C++-Code in einer universellen Windows-Plattform-App](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

Weitere Informationen zu UWP im Allgemeinen finden Sie unter [was eine universelle Windows-Plattform (UWP)-app ist?](/windows/uwp/get-started/whats-a-uwp).

Weitere Informationen zu diesen Konzepten, finden Sie unter [Anleitung für universelle Windows-Apps](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Desktop- und -Anwendungen

Informationen über die Grundlagen zum Schreiben von Windows-Clientanwendungen für den Desktop finden Sie unter [Entwickeln von Windows-Anwendungen in C++](http://msdn.microsoft.com/vstudio//hh304489) und [Einführung in die Windows-Programmierung in C++](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx).

Unter Windows 10 können Sie Visual C++ viele Arten von desktop-Programme zu erstellen:

- Befehlszeilen-Apps und -programme. Weitere Informationen finden Sie unter [Konsolenanwendungen](../windows/console-applications-in-visual-cpp.md).

- Consumer-Anwendungen mit ausgearbeiteten grafischen Benutzeroberflächen. Weitere Informationen finden Sie unter [Hilo: Entwickeln von C++-Anwendungen für Windows](http://go.microsoft.com/fwlink/p/?LinkId=256417)

- Enterprise und Branchen-apps, die auf .NET Framework ausgeführt. Die meisten .NET Framework-Anwendungen werden in c# oder Visual Basic geschrieben. Sie können C + c++ / CLI Interop-Ebenen zu erstellen, mit denen .NET Code systemeigene C++-Bibliotheken verwenden können. Weitere Informationen finden Sie unter [.NET Framework-Programmierung mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- SQL-Datenbankclients, die in nativem Code ausführen. Weitere Informationen finden Sie unter [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

- Add-Ins für Microsoft Office-Anwendungen. Weitere Informationen finden Sie unter [Erstellen eines C++-Add-Ins für Outlook 2010](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Gerätetreiber Weitere Informationen finden Sie unter [Windows-Treiberkit](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Windows-Dienste Weitere Informationen finden Sie unter [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

Sie können Visual C++ verwenden, um nahezu jede Art von benutzerdefinierter leistungsstarker Funktion in Win32-DLLs oder COM-DLLs zu verpacken, die von C++-Apps oder von Apps genutzt werden können, die in anderen Sprachen, wie z. B. C# oder Visual Basic geschrieben werden. Weitere Informationen zu Win32-DLLs finden Sie unter [DLLs in Visual C++](../build/dlls-in-visual-cpp.md). Weitere Informationen zur COM-Entwicklung finden Sie unter [Component Object Model (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="games"></a>Spiele

DirectX-Spiele können auf dem PC oder der Xbox ausgeführt werden. Weitere Informationen finden Sie unter [DirectX Developer Center](http://go.microsoft.com/fwlink/p/?LinkId=256418).

## <a name="sdks-libraries-and-header-files"></a>SDKs, Bibliotheken und Headerdateien

Visual C++ enthält die C-Laufzeitbibliothek (CRT), der C++-Standardbibliothek und andere Microsoft-spezifische Bibliotheken. Die Include-Ordner, die Headerdateien für diese Bibliotheken enthalten befinden sich entweder in der Visual Studio-Installationsverzeichnis im Ordner \VC\ oder im Fall der CRT in das Windows SDK-Installationsordner.   

Sie können die [Vcpkg-Paket-Manager](../vcpkg.md) bequem Hunderte von Drittanbieter-Open-Source-Bibliotheken für Windows installieren.

Die Microsoft-Bibliotheken enthalten:

- Microsoft Foundation Classes (MFC): Ein objektorientiertes Framework zum Erstellen herkömmlicher Windows-Programme (im Besonderen Unternehmensanwendungen), die über komplexe Benutzeroberflächen mit Schaltflächen, Listenfeldern, Strukturansichten und anderen Steuerelementen verfügen. Weitere Informationen finden Sie unter [MFC Desktop Applications](../mfc/mfc-desktop-applications.md).

- Active Template Library (ATL): Eine leistungsstarke Hilfebibliothek zum Erstellen von COM-Komponenten. Weitere Informationen finden Sie unter [ATL COM Desktop Components](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): Eine Bibliothek, die leistungsstarke allgemeine Computerarbeit auf der GPU ermöglicht. Weitere Informationen finden Sie unter [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Concurrency Runtime: Eine Bibliothek, mit der die Arbeit mit paralleler und asynchroner Programmierung für Viel- und Mehrkerngeräte vereinfacht wird. Weitere Informationen finden Sie unter [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).

Viele Programmierszenarien bei Windows erfordern zudem das Windows SDK, in dem die Headerdateien enthalten sind, die den Zugriff auf Komponenten des Windows-Betriebssystems ermöglichen. Standardmäßig installiert Visual Studio das Windows SDK als Komponente von der C++-Desktop arbeitsauslastung aus, die Entwicklung von universellen Windows-apps ermöglicht. Um uwp-apps zu entwickeln, benötigen Sie die Windows 10-Version des Windows SDK. Informationen finden Sie unter [Windows 10-SDK](https://dev.windows.com/downloads/windows-10-sdk). (Weitere Informationen zu Windows SDKs für frühere Versionen von Windows finden Sie unter der [Windows SDK-Archivs](https://developer.microsoft.com/windows/downloads/sdk-archive)). 

**Programmieren von Dateien (x86) \Windows Kits** ist der Standardspeicherort für alle Versionen von Windows-SDK, die Sie installiert haben.

Für andere Plattformen, wie Xbox und Azure, sind eigene SDKs verfügbar, die sie ggf. installieren müssen. Weitere Informationen finden Sie im DirectX-Developer Center sowie im Azure Developer Center.

## <a name="development-tools"></a>Entwicklungstools

Visual Studio bietet einen leistungsfähigen Debugger für nativen Code, Tools für statische Analyse, Grafikdebugtools, einen umfassenden Code-Editor, Unterstützung für Komponententests und viele weitere Tools und Hilfsprogramme. Weitere Informationen finden Sie unter [Einstieg in die Entwicklung mit Visual Studio](/visualstudio/ide/get-started-developing-with-visual-studio), und [IDE und Entwicklungstools](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>Verwandte Artikel

|Titel|Beschreibung|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Übergeordnetes Thema für Visual C++-Entwickler-Inhalte.|
