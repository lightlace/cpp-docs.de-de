---
title: "Exportieren aus einer DLL | Microsoft Docs"
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
  - "DLL-Exporte [C++]"
  - "DLLs [C++], Exportieren aus"
  - "Exportieren von DLLs [C++]"
  - "Exportieren von DLLs [C++], Informationen über das Exportieren aus DLLs"
  - "Exportieren von Funktionen [C++], DLLs (Exportieren aus)"
  - "Exporttabelle [C++]"
  - "Funktionen [C++], Exportieren"
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Exportieren aus einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Layout einer DLL\-Datei ähnelt dem einer EXE\-Datei. Ein wichtiger Unterschied besteht jedoch darin, dass eine DLL\-Datei über eine Exporttabelle verfügt.  Die Exporttabelle umfasst die Namen aller Funktionen, die von der DLL in andere ausführbare Dateien exportiert werden.  Die Funktionen sind Einstiegspunkte in die DLL. Andere ausführbare Dateien können nur auf die in der Exporttabelle genannten Funktionen zugreifen.  Alle weiteren Funktionen in der DLL sind privat, d. h. ausschließlich auf die DLL bezogen.  Die Exporttabelle einer DLL kann angezeigt werden, indem das [DUMPBIN](../build/reference/dumpbin-reference.md)\-Tool mit der **\/EXPORTS**\-Option verwendet wird.  
  
 Es gibt zwei Methoden zum Exportieren von Funktionen aus einer DLL:  
  
-   Erzeugen Sie eine Moduldefinitionsdatei \(.def\), und verwenden Sie beim Erstellen der DLL diese DEF\-Datei.  Verwenden Sie diese Methode, wenn Sie [Funktionen aus einer DLL über die Ordnungszahl statt über den Namen exportieren](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) möchten.  
  
-   Verwendung des **\_\_declspec\(dllexport\)**\-Schlüsselwortes in der Funktionsdefinition.  
  
 Wenn Sie Funktionen mit einer dieser beiden Methoden exportieren, sollten Sie darauf achten, die [\_\_stdcall](../cpp/stdcall.md)\-Aufrufkonvention zu verwenden.  
  
## Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Exportieren von Funktionen aus einer DLL über die Ordinalzahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Importieren in eine Anwendung](../build/importing-into-an-application.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## Siehe auch  
 [Importieren und Exportieren](../build/importing-and-exporting.md)