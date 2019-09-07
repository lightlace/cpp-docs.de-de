---
title: C++/CX-Sprachreferenz
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: ed8e2374daf862e99517fb113e869504b7c7aabc
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740868"
---
# <a name="ccx-language-reference"></a>C++/CX-Sprachreferenz

C++/CX ist ein Satz von Erweiterungen für die C++ Sprache, die die Erstellung von Windows-apps und Windows-Runtime Komponenten in einer Ausdrucksweise ermöglichen, die so nah wie C++möglich an modern ist. Verwenden C++Sie/CX, um Windows-apps und-Komponenten in nativem Code zu C#schreiben, die problemlos mit Visual, Visual Basic und JavaScript und anderen Sprachen interagieren, die die Windows-Runtime unterstützen. In den seltenen Fällen, die direkten Zugriff auf die unformatierten COM-Schnittstellen oder nicht Ausnahme Code erfordern, können Sie die [Windows-Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)verwenden.

> [!NOTE]
> **/WinRT ist die empfohlene Alternative zu C++/CX. [ C++](/windows/uwp/cpp-and-winrt-apis/index) Dabei handelt es sich um eine neue, standardmäßige c++ 17-sprach Projektion für Windows-Runtime-APIs, die im neuesten Windows 10 SDK ab Version 1803 verfügbar ist. C++/WinRT wird vollständig in Header Dateien implementiert und wurde entwickelt, um Ihnen erstklassigen Zugriff auf die moderne Windows-API zu ermöglichen.
>
> Mit C++/WinRT können Sie Windows-Runtime APIs mithilfe eines beliebigen Standard kompatiblen c++ 17-Compilers nutzen und erstellen. C++/WinRT führt in der Regel zu einer besseren Leistung und erzeugt kleinere Binärdateien als jede andere Sprachoption für die Windows-Runtime. Wir unterstützen C++/CX und WRL weiterhin, empfehlen jedoch dringend die Verwendung von C++/WinRT für neue Anwendungen. Weitere Informationen finden Sie unter [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index).

Mit C++/CX können Sie Folgendes erstellen:

- C++Universelle Windows-Plattform (UWP)-apps, die XAML verwenden, um die Benutzeroberfläche zu definieren und den systemeigenen Stapel zu verwenden. Weitere Informationen finden Sie unter [Erstellen einer "Hello World"-App C++ in (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++Windows-Runtime Komponenten, die von JavaScript-basierten Windows-Apps verwendet werden können. Weitere Informationen finden Sie unter [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows-DirectX-Spiele und grafikintensive Apps. Weitere Informationen finden Sie unter [Erstellen eines einfachen UWP-Spiels mit DirectX](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game).

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Kurzreferenz](../cppcx/quick-reference-c-cx.md)|Tabelle mit Schlüsselwörtern und Operatoren für C++/CX.|
|[Typsystem](../cppcx/type-system-c-cx.md)|Beschreibt Grund C++Legende/CX-Typen und Programmierungskonstrukte und C++erläutert, wie/CX verwendet wird, um Windows-Runtime Typen zu nutzen und zu erstellen.|
|[Erstellen von Apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)|Erläutert, wie die IDE verwendet wird, um apps zu erstellen und mit statischen Bibliotheken und DLLs zu verknüpfen.|
|[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)|Erläutert, wie Komponenten, die mithilfe C++von/CX geschrieben wurden, mit-Komponenten verwendet werden können, die in JavaScript, einer beliebigen verwalteten Sprache C++ oder in der Windows-Runtime-Vorlagen Bibliothek geschrieben sind.|
|[Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)|Erläutert, wie Sie das Threading- und Marshallingverhalten von Komponenten, die Sie erstellen, angeben können.|
|[Referenz zu Namespaces](../cppcx/namespaces-reference-c-cx.md)|Referenzdokumentation für den Standardnamespace, den Plattformnamespace, den Platform::Collections-Namespace und die zugehörigen Namespaces.|
|[In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Listet die CRT-Funktionen auf, die nicht für die Verwendung in Windows Runtime-Apps verfügbar sind.|
|[Einstieg in Windows 10-apps](/windows/uwp/get-started/)|Bietet Anleitung auf hoher Ebene zu Windows 10-Apps und Links zu weiterführenden Informationen.|
|[C++/CX Teil 0 von \[n\]: Eine Einführung](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX Teil 1 von \[n\]: Eine einfache Klasse](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX Teil 2 von \[n\]: Typen, die Hüte haben](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX Teil 3 von \[n\]: Unterkonstruktion](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX Teil 4 von \[n\]: Statische Element Funktionen](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Eine Einführungs Blog Reihe zu C++/CX.|
