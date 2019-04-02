---
title: Universelle Windows-Apps (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: fbd5366ee52dfe32baef9458a82c16914666699e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784270"
---
# <a name="universal-windows-apps-c"></a>Universelle Windows-Apps (C++)

Die universelle Windows-Plattform (UWP) ist die moderne Programmierschnittstelle für Windows. Mit der UWP, wenn Sie eine Anwendung oder Komponente einmal schreiben und auf Windows 10-Geräten bereitstellen. Sie können eine Komponente in C++ schreiben und in einer beliebigen anderen UWP-kompatiblen Sprache geschriebene Anwendungen können Sie sie.

Die meisten der UWP-Dokumentation befindet sich in der Windows-Inhaltsstruktur an [Dokumentation für die universelle Windows-Plattform](/windows/uwp/). Dort sehen Sie Anfang Tutorials sowie Referenzdokumentation. 

Für neue UWP-apps und Komponenten, empfehlen wir die Verwendung von [C++ / WinRT](/windows/uwp/cpp-and-winrt-apis/), einen neuen C ++ 17-standardsprachprojektion für Windows-Runtime-APIs. C++ / WinRT finden Sie in das Windows 10 SDK Version 1803 gerechnet. C++ / WinRT ist nur in Headerdateien implementiert wird, und soll Sie mit erstklassigen Zugriff auf die moderne Windows-API bereitstellen. Im Gegensatz zu C++ / CX-Implementierung. C++ / WinRT nicht standardisierte Syntax oder Microsoft-spracherweiterungen, und es nutzt der C++-Compiler, um hochgradig optimierte Ausgabe zu erstellen. Weitere Informationen finden Sie unter [Einführung in C++ / WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Sie können den Desktop-Brücke app Converter verwenden, zum Packen Ihrer vorhandenen Desktopanwendung für die Bereitstellung über den Microsoft Store. Weitere Informationen finden Sie unter [Using Visual C++ Runtime in Centennial Project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und [Desktop-Brücke](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-ccx"></a>UWP-apps, mit denen C++ / CX

|||
|-|-|
|[Sprachreferenz zu Visual C++ (C++/CX)](visual-c-language-reference-c-cx.md)|Beschreibt den Satz von Erweiterungen, die C++-Verbrauch von Windows-Runtime-APIs vereinfachen, und aktivieren die Fehlerbehandlung, die auf Ausnahmen basieren.|
|[Erstellen von Apps und Bibliotheken (C++/CX)](building-apps-and-libraries-c-cx.md)|Beschreibt das Erstellen von DLLs und statischen Bibliotheken, auf die von einer C++/CX-App oder Komponente zugegriffen werden kann.|
|[Tutorial: Erstellen einer UWP-app "Hello, World" in C++ / CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Eine exemplarische Vorgehensweise, die die grundlegenden Konzepte der Entwicklung von UWP-Apps in C++ stellt c++ / CX. |
|[Erstellen von Windows-Runtime-Komponenten in C++ / CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Beschreibt, wie zum Erstellen von DLLs, die anderen UWP-apps und Komponenten verwenden können.|
|[UWP-Spiel-Programmierung](/windows/uwp/gaming/)|Beschreibt, wie DirectX und C++ / CX verwenden, um Spiele zu erstellen.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>UWP-Apps, die die Windows Runtime C++-Vorlagenbibliothek (WRL) verwenden.

Die Windows Runtime C++ Template Library stellt die Low-Level COM-Schnittstellen, die über denen ISO C++-Code auf die Windows-Runtime in einer ausnahmefreien Umgebung zugreifen kann. In den meisten Fällen empfiehlt es sich, dass Sie C++ verwenden c++ / WinRT oder C++ / CX anstelle der Windows Runtime C++ Template Library für die Entwicklung von UWP-Apps. Weitere Informationen zu den Windows Runtime C++ Template Library, finden Sie unter [Windows Runtime C++ Template Library (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Siehe auch

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
[Übersicht über Windows-Programmierung in C++](../windows/overview-of-windows-programming-in-cpp.md)<br/>