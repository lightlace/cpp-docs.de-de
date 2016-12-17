---
title: "Importieren und Exportieren"
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
  - "__declspec(dllimport)-Schlüsselwort [C++]"
  - "DLLs [C++], Exportieren aus"
  - "DLLs [C++], Importieren"
  - "Exportieren von DLLs [C++]"
  - "Importieren von DLLs [C++]"
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Importieren und Exportieren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Methoden zum Importieren von öffentlichen Symbolen in eine Anwendung bzw. zum Exportieren von Funktionen aus einer DLL:  
  
-   Verwenden einer Moduldefinitionsdatei \(.def\) beim Erstellen der DLL  
  
-   Verwenden der Schlüsselwörter **\_\_declspec\(dllimport\)** oder **\_\_declspec\(dllexport\)** in einer Funktionsdefinition der Hauptanwendung  
  
## Verwenden einer DEF\-Datei  
 Eine Moduldefinitionsdatei \(.def\) ist eine Textdatei mit einer oder mehreren Modulanweisungen, die verschiedene Attribute einer DLL beschreiben.  Wenn Sie zum Exportieren von DLL\-Funktionen nicht **\_\_declspec\(dllimport\)** oder **\_\_declspec\(dllexport\)** verwenden, ist eine DEF\-Datei für die DLL erforderlich.  
  
 DEF\-Dateien ermöglichen das [Importieren in eine Anwendung](../build/importing-using-def-files.md) bzw. das [Exportieren aus einer DLL](../build/exporting-from-a-dll-using-def-files.md).  
  
## Verwenden von "\_\_declspec"  
 In Visual C\+\+ ersetzen **\_\_declspec\(dllimport\)** und **\_\_declspec\(dllexport\)** das **\_\_export**\-Schlüsselwort, das zuvor in den 16\-Bit\-Versionen von Visual C\+\+ verwendet wurde.  
  
 **\_\_declspec\(dllimport\)** muss nicht unbedingt eingesetzt werden, um einen einwandfreien Code zu kompilieren, es bietet jedoch die Möglichkeit, die Codegenerierung durch den Compiler zu optimieren.  Der Compiler kann besseren Code generieren, da er feststellen kann, ob eine Funktion in einer DLL vorhanden ist oder nicht. Beim vom Compiler generierten Code kann daher eine Ebene von Dereferenzierungen übersprungen werden, die normalerweise in einem Funktionsaufruf über die Grenze einer DLL hinaus vorhanden wäre.  Um die in einer DLL verwendeten Variablen zu importieren, muss allerdings **\_\_declspec\(dllimport\)** verwendet werden.  
  
 Mit dem geeigneten EXPORTS\-Abschnitt in der DEF\-Datei ist **\_\_declspec\(dllexport\)** nicht erforderlich.  **\_\_declspec\(dllexport\)** wurde als einfache Möglichkeit zum Exportieren von Funktionen aus einer EXE\- oder DLL\-Datei ohne Verwendung einer DEF\-Datei hinzugefügt.  
  
 Das Win32\-Format für übertragbare, ausführbare Dateien wurde entworfen, um die Anzahl der für die Korrektur von Importen verarbeiteten Seiten zu minimieren.  Zu diesem Zweck werden alle Importadressen für Programme an einem Ort zusammengefasst, der als Importadressentabelle bezeichnet wird.  Dadurch muss das Ladeprogramm lediglich eine oder zwei Seiten ändern, wenn es auf diese Importe zugreift.  
  
## Was möchten Sie tun?  
  
-   [In eine Anwendung importieren](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Aus einer DLL exportieren](../build/exporting-from-a-dll.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)