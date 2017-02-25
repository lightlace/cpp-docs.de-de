---
title: "Importieren und Exportieren von Inlinefunktionen | Microsoft Docs"
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
  - "DLLs [C++], Exportieren aus"
  - "DLLs [C++], Importieren"
  - "Exportieren von Funktionen [C++], Inlinefunktionen"
  - "Funktionen [C++], Exportieren"
  - "Funktionen [C++], Importieren"
  - "Importieren von Funktionen [C++]"
  - "Importieren von Inlinefunktionen [C++]"
  - "Inlinefunktionen [C++], Exportieren"
  - "Inlinefunktionen [C++], Importieren"
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Importieren und Exportieren von Inlinefunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Importierte Funktionen können als Inlinefunktionen definiert werden.  Der Effekt ist ungefähr derselbe wie bei der Definition einer Standardfunktion als Inlinefunktion. Aufrufe der Funktion werden, ähnlich wie bei einem Makro, als Inlinecode erweitert.  Diese Methode stellt eine hilfreiche Möglichkeit dar, C\+\+\-Klassen in einer DLL zu unterstützen, die einige ihrer Memberfunktionen zur Effizienzsteigerung inline umsetzen.  
  
 Ein Feature einer importierten Inlinefunktion besteht darin, dass ihre Adresse in C\+\+ verwendet werden kann.  Der Compiler gibt die Adresse der Kopie der Inlinefunktion zurück, die sich innerhalb der DLL befindet.  Ein weiteres Feature importierter Inlinefunktionen besteht darin, dass Sie, anders als bei globalen importierten Daten, statische lokale Daten der importierten Funktion initialisieren können.  
  
> [!CAUTION]
>  Beim Bereitstellen importierter Inlinefunktionen sollten Sie Sorgfalt walten lassen, da u. U. Versionskonflikte entstehen können.  Eine Inlinefunktion wird als Anwendungscode erweitert. Wenn Sie die Funktion später neu schreiben, wird sie daher nur aktualisiert, wenn die Anwendung selbst neu kompiliert wird. \(Normalerweise können DLL\-Funktionen aktualisiert werden, ohne dass die Anwendungen, von denen sie verwendet werden, neu erstellt werden müssen.\)  
  
## Was möchten Sie tun?  
  
-   [Aus einer DLL exportieren](../build/exporting-from-a-dll.md)  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## Siehe auch  
 [Importieren und Exportieren](../build/importing-and-exporting.md)