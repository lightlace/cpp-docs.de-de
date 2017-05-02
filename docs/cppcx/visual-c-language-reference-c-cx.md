---
title: "Sprachreferenz zu Visual&#160;C++ (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
caps.latest.revision: 27
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 27
---
# Sprachreferenz zu Visual&#160;C++ (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) ist ein Satz von Erweiterungen der Programmiersprache C\+\+, die die Erstellung von Windows\-Apps und von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten in einer Ausdrucksweise ermöglicht, die so nah wie möglich am modernen C\+\+ ist. Verwenden Sie [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], um Windows\-Apps und \-Komponenten in systemeigenem Code zu schreiben, die leicht mit Visual C\#, Visual Basic, JavaScript und anderen Sprachen, die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützen, interagieren. In den seltenen Fällen, in denen ein direkter Zugriff auf die unformatierten COM\-Schnittstellen oder den Normalcode erforderlich ist, können Sie [Windows Runtime C\+\+ Template Library \(WRL\)](~/windows/windows-runtime-cpp-template-library-wrl.md) verwenden.  
  
 Das neue Modell stellt die nächste Generation von systemeigener C\+\+\-Programmierung auf Windows dar. Sie können damit Folgendes erstellen:  
  
-   Windows\-C\+\+ Apps, die XAML verwenden, um die Benutzeroberfläche zu definieren und den systemeigenen Stapel zu verwenden. Weitere Informationen finden Sie unter [Erstellen der App „Hello World“ in C\+\+ \(Windows 10\)](http://msdn.microsoft.com/library/windows/apps/dn996906.aspx).  
  
-   C\+\+ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten, die von JavaScript\-basierten Windows\-Apps genutzt werden können. Weitere Informationen finden Sie unter [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/hh441569.aspx)[Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
-   Windows\-DirectX\-Spiele und grafikintensive Apps. Weitere Informationen finden Sie unter [Erstellen eines einfachen UWP\-Spiels \(Universelle Windows\-Plattform\) mit DirectX](http://msdn.microsoft.com/library/windows/apps/xaml/mt210793.aspx).  
  
## Verwandte Artikel  
  
|||  
|-|-|  
|[Kurzreferenz](../cppcx/quick-reference-c-cx.md)|Tabelle von Schlüsselwörtern und Operatoren für [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).|  
|[Typsystem](../cppcx/type-system-c-cx.md)|Beschreibt grundlegende [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Typen und \-Programmierungskonstrukte und wie [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] verwendet werden kann, um [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen zu konsumieren und zu erstellen.|  
|[Erstellen von Apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)|Erläutert, wie die IDE verwendet werden kann, um Apps und Links zu statischen Bibliotheken und DLLs zu erstellen.|  
|[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)|Erläutert, wie Komponenten, die unter Verwendung von [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] geschrieben wurden, mit Komponenten verwendet werden können, die in JavaScript, einer beliebigen verwalteten Sprache oder in [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] geschrieben wurden.|  
|[Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)|Erläutert, wie Sie das Threading\- und Marshallingverhalten von Komponenten, die Sie erstellen, angeben können.|  
|[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)|Referenzdokumentation für den Standardnamespace, den Plattformnamespace, den Platform::Collections\-Namespace und die zugehörigen Namespaces.|  
|[In Apps für die universelle Windows\-Plattform nicht unterstützte CRT\-Funktionen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Listet die CRT\-Funktionen auf, die nicht für die Verwendung in Windows Runtime\-Apps verfügbar sind.|  
|[Anleitungen für Windows 10\-Apps](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Bietet Anleitung auf hoher Ebene zu Windows 10\-Apps und Links zu weiterführenden Informationen.|  
  
1.  [C\+\+\/CX Teil 0 von \[n\]: Einführung](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX Teil 0 von \[n\]: Einführung](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX Teil 2 von \[n\]: Typen mit Hut](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX Teil 3 von \[n\]: Baustelle](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX Teil 4 von \[n\]: Statische Memberfunktionen](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)