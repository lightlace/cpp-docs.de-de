---
title: Visual C++-Sprachverzeichnis (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 801a88573133a68beec4855dc499fcba27bb64e8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593868"
---
# <a name="visual-c-language-reference-ccx"></a>Sprachreferenz zu Visual C++ (C++/CX)

C++ / CX-ist ein Satz von Erweiterungen der C++-Sprache, mit denen die Erstellung von Windows-apps und Windows-Runtime-Komponenten in einer Ausdrucksweise ermöglicht, so nah wie möglich am modernen C++. C++ / CX verwenden, um das Schreiben von Windows-apps und-Komponenten in systemeigenem Code, die einfache Interaktion mit Visual c#, Visual Basic und JavaScript und anderen Sprachen, die die Windows-Runtime unterstützen. In den seltenen Fällen, die direkter Zugriff auf den unformatierten COM-Schnittstellen oder den normalcode erforderlich ist, können Sie mithilfe der [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> C++ / WinRT ist eine neue "," standard C ++ 17-sprachprojektion für Windows-Runtime-APIs. Es ist im aktuellen Windows 10 SDK Version 1803 gerechnet verfügbar. C++ / WinRT ist nur in Headerdateien implementiert und bietet Ihnen mit erstklassigen Zugriff auf die moderne Windows-API.

> Mit C++ / WinRT, können Sie sowohl nutzen und Erstellen von Windows-Runtime-APIs mit einem beliebigen standardkonformen C ++ 17-Compiler. C++ / WinRT in der Regel eine bessere Leistung und erzeugt kleinere Binärdateien als jede andere Sprachoption für die Windows-Runtime. Wir weiterhin zur Unterstützung von C++ / CX- und WRL, jedoch dringend empfohlen, neue Anwendungen C++ mithilfe / WinRT. Weitere Informationen finden Sie unter [C++ / WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).


Mithilfe von C++ / CX werden, die Sie erstellen können:

- C++ Universal Windows Platform (UWP)-apps, die XAML verwenden, um den Benutzer zu definieren. Benutzeroberfläche und den systemeigenen Stapel zu verwenden. Weitere Informationen finden Sie unter [Erstellen einer "Hello World"-app in C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++-Windows-Runtime-Komponenten, die von JavaScript-basierten Windows-apps genutzt werden können. Weitere Informationen finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows-DirectX-Spiele und grafikintensive Apps. Weitere Informationen finden Sie unter [Erstellen eines einfachen UWP-Spiels mit DirectX](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Kurzübersicht](../cppcx/quick-reference-c-cx.md)|Tabelle von Schlüsselwörtern und Operatoren für C++ / CX.|
|[Typsystem](../cppcx/type-system-c-cx.md)|Beschreibt grundlegende C + c++ / CX-Typen und Konstrukte der Programmierung und beschrieben, wie Sie C++ / CX zu nutzen und die Windows-Runtime-Typen zu erstellen.|
|[Erstellen von apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)|Erläutert, wie die IDE verwendet werden kann, um Apps und Links zu statischen Bibliotheken und DLLs zu erstellen.|
|[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)|Erläutert, wie Komponenten, die geschrieben werden, mithilfe von C++ / CX kann verwendet werden, mit Komponenten, die in JavaScript geschrieben sind, einem der verwalteten Sprache oder der Windows Runtime C++ Template Library.|
|[Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)|Erläutert, wie Sie das Threading- und Marshallingverhalten von Komponenten, die Sie erstellen, angeben können.|
|[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)|Referenzdokumentation für den Standardnamespace, den Plattformnamespace, den Platform::Collections-Namespace und die zugehörigen Namespaces.|
|[In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Listet die CRT-Funktionen auf, die nicht für die Verwendung in Windows Runtime-Apps verfügbar sind.|
|[Anleitungen für Windows 10-Apps](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Bietet Anleitung auf hoher Ebene zu Windows 10-Apps und Links zu weiterführenden Informationen.|
|[C++ / CX Teil 0 von \[n\]: Einführung](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++ / CX Teil 1 von \[n\]: eine einfache Klasse](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++ / CX Teil 2 von \[n\]: Typen mit Hut](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++ / CX Teil 3 von \[n\]: in Bearbeitung](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++ / CX Teil 4 von \[n\]: statische Memberfunktionen](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Eine einführende Visual C++-Blog-Reihe an C++ / CX.|
