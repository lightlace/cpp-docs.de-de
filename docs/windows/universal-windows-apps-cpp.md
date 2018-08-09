---
title: Universelle Windows-Apps (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56b6642bb24107da4c09856dbd8daaf70fb7dfd5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015006"
---
# <a name="universal-windows-apps-c"></a>Universelle Windows-Apps (C++)

Apps der universellen Windows-Plattform (UWP) stellen einen Satz Entwurfsprinzipien dar, die einfache Benutzeroberflächen betonen, die um Inhalt zentriert werden, die automatisch für verschiedene Bildschirmgrößen auf verschiedenen Geräten anpasst. Sie erstellen die Benutzeroberfläche in XAML-Markup und den Code-Behind in systemeigenem C++. Sie können auch Komponenten (DLLs) für UWP-Apps erstellen, die in anderen Sprachen geschrieben sind. Die API-Oberfläche für UWP-apps ist die Windows-Runtime, d. h. eine gut ausgearbeitete Bibliothek, die eine Vielzahl von Betriebssystemdiensten bereitstellt.

> [!TIP]  
> Für Windows 10 können Sie den Desktop-Brücke app Converter zum Packen Ihrer vorhandenen Desktopanwendung für die Bereitstellung über den Microsoft Store verwenden. Weitere Informationen finden Sie unter [Using Visual C++ Runtime in Centennial Project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und [Desktop-Brücke](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>UWP-apps, mit denen C++ / WinRT

C++ / WinRT ist eine neue, nur-Header-Bibliothek basierende C++-sprachprojektion für die Windows-Runtime, die vollständig standard C++, im Gegensatz zu C + verwendet c++ / CX-Implementierung. C++ / WinRT nicht standardisierte Syntax oder Microsoft-spracherweiterungen, und es nutzt der C++-Compiler, um hochgradig optimierte Ausgabe zu erstellen. Weitere Informationen finden Sie unter [C++ / WinRT](/windows/uwp/cpp-and-winrt-apis). Eine Einführung in C++ / WinRT und eine schnellstartanleitung Code finden Sie unter [Einführung in C++ / WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>UWP-apps, mit denen C++ / CX

|||
|-|-|
|[Sprachreferenz zu Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Beschreibt den Satz von Erweiterungen, die C++-Verbrauch von Windows-Runtime-APIs vereinfachen, und aktivieren die Fehlerbehandlung, die auf Ausnahmen basieren.|
|[Erstellen von Apps und Bibliotheken (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Beschreibt das Erstellen von DLLs und statischen Bibliotheken, auf die von einer C++/CX-App oder Komponente zugegriffen werden kann.|
|[Tutorial: Erstellen einer UWP-app "Hello, World" in C++ / CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Eine exemplarische Vorgehensweise, die die grundlegenden Konzepte der Entwicklung von UWP-Apps in C++ stellt c++ / CX. |
|[Erstellen von Windows-Runtime-Komponenten in C++ / CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Beschreibt, wie zum Erstellen von DLLs, die anderen UWP-apps und Komponenten verwenden können.|
|[UWP-Spiel-Programmierung](/windows/uwp/gaming/)|Beschreibt, wie DirectX und C++ / CX verwenden, um Spiele zu erstellen.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>UWP-Apps, die die Windows Runtime C++-Vorlagenbibliothek (WRL) verwenden.

Die Windows Runtime C++ Template Library stellt die Low-Level COM-Schnittstellen, die über denen ISO C++-Code auf die Windows-Runtime in einer ausnahmefreien Umgebung zugreifen kann. In den meisten Fällen empfiehlt es sich, dass Sie C++ verwenden c++ / WinRT oder C++ / CX anstelle der Windows Runtime C++ Template Library für die Entwicklung von UWP-Apps. Weitere Informationen zu den Windows Runtime C++ Template Library, finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Siehe auch
 [Visual C++](../visual-cpp-in-visual-studio.md)<br/>