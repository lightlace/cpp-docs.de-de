---
title: "Anforderungen f&#252;r die Erstellung von Windows Vista-Standardsteuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeine Steuerelemente (MFC)"
  - "Allgemeine Steuerelemente (MFC), Build-Anforderungen"
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Anforderungen f&#252;r die Erstellung von Windows Vista-Standardsteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) unterstützt Version 6.1 der allgemeinen Windows\-Steuerelemente.  Die allgemeinen Steuerelemente sind in [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] enthalten und die Bibliothek ist in [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] enthalten.  Die Bibliothek stellt neue Methoden, die vorhandenen Klassen erweitern, und neue Klassen und Methoden, die [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] allgemeine Steuerelemente unterstützen.  Wenn Sie die Anwendung erstellen, sollten Sie den Migrationsanforderungen Kompilierungs\- und befolgen, die in den folgenden Abschnitten beschrieben werden.  
  
## Kompilierungs\-Anforderungen  
  
### Unterstützte Versionen  
 Einige neue Klassen und Methoden unterstützen nur [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] und höher, während andere Methoden auch ältere Betriebssysteme unterstützen.  Ein Hinweis im Abschnitt `Requirements` jedes Methodenthemas gibt an, wann die minimale erforderliche Betriebssystem [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ist.  
  
 Auch wenn Ihr Computer [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] nicht ausgeführt wird, können Sie eine MFC\-Anwendung erstellen, die auf [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] ausgeführt wird, wenn Sie die Headerdateien der MFC Version 6.1 auf dem Computer.  Allerdings funktionieren allgemeine Steuerelemente, die speziell für [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] entwickelt wurden, auf diesem System und in älteren Betriebssystemen werden ignoriert.  
  
### Unterstützte Zeichensätze  
 Die neuen allgemeinen Windows\-Steuerelemente unterstützen nur der Unicode\-Zeichensatz und nicht den ANSI\-Zeichensatz.  Wenn Sie die Anwendung in der Befehlszeile erstellen, verwenden Sie folgende definieren \(\/D\) Compileroptionen, Unicode als zugrunde liegenden Zeichensatz anzugeben:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Wenn Sie die Anwendung in der integrierten Entwicklungsumgebung \(IDE\) von Visual Studio erstellen, geben Sie die Option **Unicode\-Zeichensatz** der Eigenschaft **Zeichensatz** im Knoten **Allgemein** Projekteigenschaften an.  
  
 Die ANSI\-Version mehrerer MFC\-Methoden sind veraltet Starten mit Version 6.1 der allgemeinen Windows\-Steuerelemente erwiesen.  Weitere Informationen finden Sie unter [Veraltete ANSI\-APIs](../mfc/deprecated-ansi-apis.md).  
  
## Migrations\-Anforderungen  
 Wenn Sie die Visual Studio\-IDE verwenden, um eine neue MFC\-Anwendung zu erstellen, die Version 6.1 der allgemeinen Windows\-Steuerelemente verwendet, deklariert die IDE automatisch ein entsprechendes Manifest.  Wenn Sie eine vorhandene MFC\-Anwendung von einer früheren Version von Visual Studio migrieren und die neuen allgemeinen Steuerelemente verwenden möchten, stellt die IDE nicht automatisch Manifest Informationen, um die Anwendung zu aktualisieren.  Stattdessen müssen Sie den folgenden Quellcode in die stdafx.h\-Datei manuell einfügen:  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [Hierarchiediagramm](../mfc/hierarchy-chart.md)   
 [Veraltete ANSI\-APIs](../mfc/deprecated-ansi-apis.md)