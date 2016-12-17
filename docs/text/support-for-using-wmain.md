---
title: "Unterst&#252;tzung f&#252;r die Verwendung von wmain"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "wWinMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Breitzeichen [C++], wmain-Funktion"
  - "wmain-Funktion"
  - "wWinMain-Funktion"
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "ghogen"
manager: "ghogen"
---
# Unterst&#252;tzung f&#252;r die Verwendung von wmain
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Von Visual C\+\+ werden das Definieren einer **wmain**\-Funktion sowie die Übergabe von Breitzeichen\-Argumenten an eine Unicode\-Anwendung unterstützt.  Sie deklarieren die formalen Parameter für **wmain** unter Verwendung eines ähnlichen Formats wie für **main**.  Sie können anschließend Breitzeichen\-Argumente und optional einen Breitzeichen\-Umgebungszeiger übergeben, der auf das Programm verweist.  Der `argv`\-Parameter und der `envp`\-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`.  Beispiel:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  In Unicode\-Anwendungen von MFC wird **wWinMain** als Einstiegspunkt verwendet.  In diesem Fall ist `CWinApp::m_lpCmdLine` eine Unicode\-Zeichenfolge.  Stellen Sie sicher, dass **wWinMainCRTStartup** mit der [\/ENTRY](../build/reference/entry-entry-point-symbol.md)\-Linkeroption gesetzt ist.  
  
 Wenn in einem Programm eine **main**\-Funktion verwendet wird, wird die Mehrbyte\-Zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt.  Eine Breitzeichen\-Kopie der Umgebung wird nur bei Bedarf erstellt \(z. B. durch Aufruf der `_wgetenv`\-Funktion bzw. der `_wputenv`\-Funktion\).  Beim ersten Aufruf von `_wputenv` \(bzw. dem ersten Aufruf von `_wgetenv`, wenn bereits eine MBCS\-Umgebung vorhanden ist\) wird eine entsprechende Breitzeichen\-Umgebung erstellt.  Auf diese Umgebung wird anschließend durch die globale Variable `_wenviron` verwiesen, einer Breitzeichen\-Version der globalen Variable `_environ`.  Zu diesem Zeitpunkt sind zwei Kopien der Umgebung \(MBCS und Unicode\) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Laufzeitsystem verwaltet.  
  
 Wenn ein Programm eine **wmain**\-Funktion verwendet, wird beim Programmstart eine Breitzeichen\-Umgebung erstellt, auf die die globale Variable `_wenviron` verweist.  Eine MBCS\-Umgebung \(ASCII\) wird beim ersten Aufruf von `_putenv` oder `getenv` erstellt. Auf diese Umgebung verweist anschließend die globale Variable `_environ`.  
  
## Siehe auch  
 [Unterstützung für Unicode](../text/support-for-unicode.md)   
 [Zusammenfassung der Unicode\-Programmierung](../text/unicode-programming-summary.md)   
 [WinMain\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms633559)