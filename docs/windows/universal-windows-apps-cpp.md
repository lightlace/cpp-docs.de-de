---
title: Universelle Windows-Apps (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a293f833de7bc575209089362bcaf146d074684b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="universal-windows-apps-c"></a>Universelle Windows-Apps (C++)
Apps der universellen Windows-Plattform (UWP) stellen einen Satz von Entwurfsprinzipien einfache Benutzeroberflächen, die um Inhalt zentriert werden, die für verschiedene Bildschirmgrößen auf verschiedenen Geräten automatisch anpasst. Sie erstellen die Benutzeroberfläche in XAML-Markup und den Code-Behind in systemeigenem C++. Sie können auch Komponenten (DLLs) für UWP-Apps erstellen, die in anderen Sprachen geschrieben sind. Die API-Oberfläche für uwp-apps ist der Windows-Runtime, eine gut ausgearbeitete Bibliothek, die eine Vielzahl von Betriebssystemdiensten bereitstellt.  

> [!TIP]  
> Für Windows 10 können Sie Desktop-App-Konverter verwenden, um Ihre vorhandenen desktop-Anwendung für die Bereitstellung über den Microsoft Store verpacken. Weitere Informationen finden Sie im Blogbeitrag [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) und unter [Überführen Ihrer Desktop-App auf die universelle Windows-Plattform (UWP) mit Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).
  
  
## <a name="uwp-apps-that-use-ccx"></a>UWP-Apps, die C++/CX verwenden  
  
|||  
|-|-|  
|[Sprachreferenz zu Visual C++ (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Beschreibt den Satz von Erweiterungen, die C++-Verbrauch von Windows-Runtime-APIs zu vereinfachen, und aktivieren die Fehlerbehandlung, die auf Grundlage von Ausnahmen ist.|  
|[Erstellen von Apps und Bibliotheken (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|Beschreibt das Erstellen von DLLs und statischen Bibliotheken, auf die von einer C++/CX-App oder Komponente zugegriffen werden kann.|  
|[Lernprogramm: Erstellen Sie Ihrer ersten uwp-app mit C++](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|Eine exemplarische Vorgehensweise, die die grundlegenden Konzepte der Entwicklung von UWP-Apps in C++ eingeführt werden. (Noch nicht für die UWP-Entwicklung unter Windows 10 aktualisiert.)|  
|[Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Beschreibt, wie zum Erstellen von DLLs, die andere uwp-apps und Komponenten genutzt werden können.|  
|[Entwickeln von Spielen](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|Beschreibt die Verwendung von DirectX und C++ zum Erstellen von Spielen.|  
  
## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Uwp-Apps, die die Windows Runtime C++-Vorlagenbibliothek (WRL) 
 Der Windows Runtime C++ Template Library stellt die Low-Level COM-Schnittstellen, die mit denen ISO C++-Code der Windows-Runtime in einer ausnahmefreien Umgebung zugreifen kann. In den meisten Fällen empfiehlt es sich, dass Sie C++ verwenden c++ / CX anstatt Windows Runtime C++ Template Library für uwp-app-Entwicklung. Informationen über die Windows Runtime C++ Template Library finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++](../visual-cpp-in-visual-studio.md)

