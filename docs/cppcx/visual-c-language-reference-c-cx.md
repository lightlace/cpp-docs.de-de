---
title: Visual C++-Sprachreferenz (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
caps.latest.revision: "27"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a0e7cba73d85253db28d719932d02cfb3cdecca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-language-reference-ccx"></a>Sprachreferenz zu Visual C++ (C++/CX)

C + c++ / CX ist ein Satz von Erweiterungen der Programmiersprache C++, die die Erstellung von Windows-apps und Windows-Runtime-Komponenten in einer Ausdrucksweise ermöglicht so ein, die so nah wie möglich am modernen C++ ist. Verwenden Sie C + c++ / CX zum Schreiben von Windows-apps und-Komponenten in systemeigenem Code, die leicht mit Visual c#, Visual Basic und JavaScript interagieren und anderen Sprachen, die die Windows-Runtime unterstützt. In den seltenen Fällen, die direkten Zugriff auf die unformatierten COM-Schnittstellen oder den normalcode erforderlich ist, können Sie die [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

Das neue Modell stellt die nächste Generation von systemeigener C++-Programmierung auf Windows dar. Sie können damit Folgendes erstellen:

- C++ universelle Windows-Plattform (UWP)-apps, die XAML verwenden, um den Benutzer zu definieren, Benutzeroberfläche und den systemeigenen Stapel zu verwenden. Weitere Informationen finden Sie unter [erstellen Sie eine "Hello World"-app in C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++-Windows-Runtime-Komponenten, die von JavaScript-basierten Windows-apps genutzt werden können. Weitere Informationen finden Sie unter [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows-DirectX-Spiele und grafikintensive Apps. Weitere Informationen finden Sie unter [Erstellen eines einfachen uwp-Spiels mit DirectX](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>Verwandte Artikel

|||
|-|-|
|[Kurzübersicht](../cppcx/quick-reference-c-cx.md)|Tabelle von Schlüsselwörtern und Operatoren für C + c++ / CX.|
|[Typsystem](../cppcx/type-system-c-cx.md)|Beschreibt grundlegende C + c++ / CX-Typen und Programmierungskonstrukte und wie C + c++ / CX zu nutzen und Windows-Runtime-Typen zu erstellen.|
|[Erstellen von apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)|Erläutert, wie die IDE verwendet werden kann, um Apps und Links zu statischen Bibliotheken und DLLs zu erstellen.|
|[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)|Erläutert, wie Komponenten, die mit C + c++ / CX kann verwendet werden, für Komponenten, die in JavaScript geschrieben sind, die einer beliebigen verwalteten Sprache, oder die [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)].|
|[Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)|Erläutert, wie Sie das Threading- und Marshallingverhalten von Komponenten, die Sie erstellen, angeben können.|
|[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)|Referenzdokumentation für den Standardnamespace, den Plattformnamespace, den Platform::Collections-Namespace und die zugehörigen Namespaces.|
|[In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Listet die CRT-Funktionen auf, die nicht für die Verwendung in Windows Runtime-Apps verfügbar sind.|
|[Anleitungen für Windows 10-Apps](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Bietet Anleitung auf hoher Ebene zu Windows 10-Apps und Links zu weiterführenden Informationen.|
|[C + c++ / CX Teil 0 von \[ n \]: eine Einführung](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + c++ / CX Teil 1 von \[ n \]: eine einfache Klasse](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + c++ / CX Teil 2 von \[ n \]: Typen mit Hut](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + c++ / CX Teil 3 von \[ n \]: Baustelle](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + c++ / CX Teil 4 von \[ n \]: statische Memberfunktionen](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Eine einführende Visual C++-blogreihe über C + c++ / CX.|
