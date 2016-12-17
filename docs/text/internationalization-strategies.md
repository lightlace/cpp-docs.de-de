---
title: "Strategien f&#252;r die Internationalisierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichensätze [C++], Internationale Programmierkonzepte"
  - "Globalisierung [C++], Zeichensätze"
  - "Sprachenübertragbarer Code [C++]"
  - "Lokalisierung [C++], Zeichensätze"
  - "MBCS [C++], Internationalisierungskonzepte"
  - "Unicode [C++], Globalisieren von Anwendungen"
  - "Win32 [C++], Internationale Programmierkonzepte"
  - "Windows-API [C++], Internationale Programmierkonzepte"
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "ghogen"
manager: "ghogen"
---
# Strategien f&#252;r die Internationalisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Abhängig von den Zielbetriebssystemen und Zielmärkten verfügen Sie über unterschiedliche Strategien für die Internationalisierung:  
  
-   Eine Anwendung verwendet Unicode und wird folglich unter Windows 2000 und Windows NT ausgeführt, nicht jedoch unter Windows 95 oder Windows 98.  
  
     Sie verwenden die Unicode\-spezifischen Funktionen und alle Zeichen sind 16 Bits breit. \(Für Sonderfälle können Sie in einigen Programmteilen jedoch ANSI\-Zeichen verwenden.\)  Die C\-Laufzeitbibliothek stellt Funktionen, Makros und Datentypen ausschließlich für die Unicode\-Programmierung bereit.  MFC ist vollständig Unicode\-aktiviert.  
  
-   Eine Anwendung verwendet MBCS und kann auf jeder Win32\-Plattform ausgeführt werden.  
  
     Sie verwenden die MBCS\-spezifische Funktionen.  Zeichenfolgen können Einzelbytezeichen, Doppelbytezeichen oder beides enthalten.  Die C\-Laufzeitbibliothek stellt Funktionen, Makros und Datentypen ausschließlich für die MBCS\-Programmierung bereit.  MFC ist vollständig MBCS\-aktiviert.  
  
-   Der Quellcode einer Anwendung wurde auf vollständige Portabilität hin geschrieben. Sie können Versionen für Unicode oder MBCS erstellen, indem Sie mit dem Symbol **\_UNICODE** bzw. **\_MBCS** neu kompilieren.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Ihrer Anwendung kommt eine Wrapperbibliothek für fehlende Unicode\-Funktionen unter Windows 95, Windows 98 und Windows ME wie das, in [Entwerfen Sie eine einzelne Unicode\-App, die unter Windows 98 und Windows 2000 ausgeführt wird](http://go.microsoft.com/fwlink/p/?LinkId=250770) dem beschrieben wird.  Wrapperbibliotheken sind auch im Handel erhältlich.  
  
     Sie verwenden vollständig portable C\-Laufzeitfunktionen, \-makros und \-datentypen.  Dank der Flexibilität von MFC werden all diese Strategien unterstützt.  
  
 Bei den restlichen Themen dieser Themen liegt der Schwerpunkt auf dem Schreiben von vollständig portablem Code, den Sie wahlweise als Unicode\- oder MBCS\-Code erstellen können.  
  
## Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Gebietsschemas und Codepages](../text/locales-and-code-pages.md)