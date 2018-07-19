---
title: Universelle Windows-Apps (C++) | Microsoft Docs
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
ms.openlocfilehash: 9914e9ac83efcc43ef120259254b65ef4f1e0ee9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891122"
---
# <a name="universal-windows-apps-c"></a>Universelle Windows-Apps (C++)

Apps der universellen Windows-Plattform (UWP) stellen einen Satz von Entwurfsprinzipien einfache Benutzeroberflächen, die um Inhalt zentriert werden, die für verschiedene Bildschirmgrößen auf verschiedenen Geräten automatisch anpasst. Sie erstellen die Benutzeroberfläche in XAML-Markup und den Code-Behind in systemeigenem C++. Sie können auch Komponenten (DLLs) für UWP-Apps erstellen, die in anderen Sprachen geschrieben sind. Die API-Oberfläche für uwp-apps ist der Windows-Runtime, eine gut ausgearbeitete Bibliothek, die eine Vielzahl von Betriebssystemdiensten bereitstellt.

> [!TIP]  
> Für Windows 10 können Sie Bridge Desktop-app-Konverter verwenden, um Ihre vorhandenen desktop-Anwendung für die Bereitstellung über den Microsoft Store verpacken. Weitere Informationen finden Sie unter [mithilfe von Visual C++-Runtime in das Projekt](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>Uwp-apps, die C + c++ / WinRT

C + c++ / WinRT ist eine neue, reine Library-basierte C++ Language Projektion für die Windows-Runtime, die vollständig Standard-c++ im Gegensatz zu C + verwendet c++ / CX-Implementierung. C + c++ / WinRT verwendet keine nicht standardmäßigen Syntax oder Microsoft spracherweiterungen und dauert vollem Umfang der C++-Compiler stark optimiert Ausgabe erstellen. Weitere Informationen finden Sie unter [C + c++ / WinRT](/windows/uwp/cpp-and-winrt-apis). Eine Einführung in die C + c++ / WinRT und einen Schnellstart Code finden Sie unter [Einführung in die C + c++ / WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>Uwp-apps, die C + c++ / CX

|||
|-|-|
|[Sprachreferenz zu Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Beschreibt den Satz von Erweiterungen, die C++-Verbrauch von Windows-Runtime-APIs zu vereinfachen, und aktivieren die Fehlerbehandlung, die auf Grundlage von Ausnahmen ist.|
|[Erstellen von Apps und Bibliotheken (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Beschreibt das Erstellen von DLLs und statischen Bibliotheken, auf die von einer C++/CX-App oder Komponente zugegriffen werden kann.|
|[Lernprogramm: Erstellen eine uwp-App "Hello, World"-app in C + c++ / CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Eine exemplarische Vorgehensweise, die die grundlegenden Konzepte von uwp-app-Entwicklung in C++ eingeführt werden c++ / CX. |
|[Erstellen von Windows-Runtime-Komponenten in C + c++ / CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Beschreibt, wie zum Erstellen von DLLs, die andere uwp-apps und Komponenten genutzt werden können.|
|[Uwp-Spiels Programmierung](/windows/uwp/gaming/)|Beschreibt, wie DirectX und C + c++ / CX zum Erstellen von Spielen.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Uwp-Apps, die die Windows Runtime C++-Vorlagenbibliothek (WRL)

Der Windows Runtime C++ Template Library stellt die Low-Level COM-Schnittstellen, die mit denen ISO C++-Code der Windows-Runtime in einer ausnahmefreien Umgebung zugreifen kann. In den meisten Fällen empfiehlt es sich, dass Sie C++ verwenden c++ / WinRT oder C + c++ / CX anstatt Windows Runtime C++ Template Library für uwp-app-Entwicklung. Informationen über die Windows Runtime C++ Template Library finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Siehe auch

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
