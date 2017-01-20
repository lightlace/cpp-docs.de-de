---
title: "Universelle Windows-Apps (C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# Universelle Windows-Apps (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Apps der universellen Windows\-Plattform \(UWP\) stellen einen Satz von Entwurfsprinzipien dar, die ein Hauptaugenmerk auf einfache Benutzeroberflächen legen. Diese Benutzeroberflächen konzentrieren sich auf Inhalt, der sich unterschiedlichen Bildschirmgrößen auf verschiedenen Geräten anpassen kann. Sie erstellen die Benutzeroberfläche in XAML\-Markup und den Code\-Behind in systemeigenem C\+\+. Sie können auch Komponenten \(DLLs\) für UWP\-Apps erstellen, die in anderen Sprachen geschrieben sind. Die API\-Schnittstelle für UWÜ\-Apps ist [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]. Dies ist eine gut ausgearbeitete Bibliothek, die eine Vielzahl von Betriebssystemdiensten bereitstellt.  
  
> [!NOTE]
>  Einen Großteil der Dokumentation zur UWP\-App\-Entwicklung in C\+\+ finden Sie auf der Website vom [Windows Developer Center](http://go.microsoft.com/fwlink/p/?LinkId=255563). Einige der Links in diesem Artikel wechseln zu dieser Website.  
  
## UWP\-Apps, die C\+\+\/CX verwenden  
  
|||  
|-|-|  
|[Sprachreferenz zu Visual C\+\+ \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=255561)|Beschreibt den Satz von Erweiterungen, mit denen der C\+\+\-Verbrauch von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] APIs vereinfacht und Fehlerbehandlung auf Grundlage von Ausnahmen aktiviert wird.|  
|[Erstellen von Apps und Bibliotheken \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=264858)|Beschreibt das Erstellen von DLLs und statischen Bibliotheken, auf die von einer C\+\+\/CX\-App oder Komponente zugegriffen werden kann.|  
|[Tutorial: Erstellen Ihrer ersten Windows Store\-App mit C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255556)|Eine exemplarische Vorgehensweise, mit der die grundlegenden Konzepte der Entwicklung von [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps in C\+\+ eingeführt werden. \(Noch nicht für die UWP\-Entwicklung unter Windows 10 aktualisiert.\)|  
|[Roadmap für Windows Store\-Apps mit C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255553)|Enthält Links zu Artikeln über die Entwicklung von [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps und Spielen in C\+\+.|  
|[Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255559)|Beschreibt das Erstellen von DLLs, die von anderen [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps und Komponenten genutzt werden können.|  
|[Entwickeln von Spielen](http://go.microsoft.com/fwlink/p/?LinkId=255554)|Beschreibt die Verwendung von DirectX und C\+\+ zum Erstellen von Spielen.|  
  
## [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps, die [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) verwenden  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] stellt die COM\-Schnittstellen auf niedriger Ebene bereit, mit deren Hilfe ISO C\+\+\-Code in einer ausnahmefreien Umgebung auf [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] zugreifen kann. In den meisten Fällen wird empfohlen, C\+\+\/CX anstatt von [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] für die Entwicklung von [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]\-Apps zu verwenden. Weitere Informationen zu den [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] finden Sie unter [Windows Runtime C\+\+ Template Library \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## Siehe auch  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)